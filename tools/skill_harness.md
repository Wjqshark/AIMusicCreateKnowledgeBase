# 🧩 Skill Harness — Agent 技能调用入口

> **面向 AI Agent 的结构化技能清单。** 本文件定义本知识库对外暴露的所有可调用技能（Skill），遵循 Harness 模式，便于 Agent 框架（LangChain、AutoGen、GitHub Copilot Extensions 等）直接解析和调用。

---

## 📌 使用说明

1. Agent 启动时读取本文件，获取所有可用技能列表。
2. 根据用户意图，匹配 `trigger_keywords`，选择对应技能。
3. 按技能定义的 `steps` 顺序，读取指定知识库路径，整合内容后输出。
4. 输出格式遵循各技能的 `output_schema`。

---

## 🗂️ 技能索引（Skill Manifest）

| 技能 ID | 技能名称 | 核心用途 |
|---|---|---|
| `skill_generate_music_plan` | 生成完整音乐创作方案 | 根据风格+情绪输出完整创作方案 |
| `skill_lookup_genre` | 检索风格知识 | 查询指定音乐风格的核心参数与编曲规则 |
| `skill_lookup_mood` | 检索情绪映射 | 查询情绪对应的编曲风格与关键词 |
| `skill_generate_style_prompt` | 生成 StylePrompt | 输出可直接用于 Suno / Udio 的英文 Prompt |
| `skill_generate_lyrics_template` | 生成歌词结构模版 | 输出带段落标注的歌词框架 |
| `skill_lookup_theory` | 查询音乐理论 | 查询和弦进行、音阶、歌曲结构等理论知识 |
| `skill_suno_workflow` | Suno 创作工作流 | 指导用户在 Suno v5.5 上完成创作全流程 |

---

## 📘 技能详情（Skill Definitions）

---

### skill_generate_music_plan

```yaml
id: skill_generate_music_plan
name: 生成完整音乐创作方案
description: >
  根据用户提供的风格、情绪、场景、语言等参数，综合知识库中的风格规则、
  情绪映射和模版，生成一份结构完整的音乐创作方案。
  这是最常用的顶层技能，涵盖其他所有子技能。

trigger_keywords:
  - 帮我创作一首歌
  - 生成音乐方案
  - 作曲
  - 写一首关于…的歌
  - 制作一首…风格的曲子
  - create a song
  - generate music plan

inputs:
  - name: genre
    type: string
    required: false
    description: 音乐风格（如 Pop、Rock、Jazz、EDM、Hip-Hop、R&B、Choral、Folk、Country、Latin）
  - name: mood
    type: string
    required: false
    description: 情绪/场景（如 happy / sad / energetic / calm / romantic，也可用中文：开心 / 悲伤 / 激昂 / 平静 / 浪漫）
  - name: theme
    type: string
    required: false
    description: 歌曲主题或故事（如 失恋、奋斗、思乡）
  - name: language
    type: string
    required: false
    default: 中文
    description: 歌词语言（中文 / English / 双语）
  - name: bpm
    type: string
    required: false
    description: 期望 BPM 范围（如 100–120）或描述（快/慢）
  - name: duration
    type: string
    required: false
    description: 歌曲时长（如 3分钟、4分钟）
  - name: vocal_type
    type: string
    required: false
    description: 人声类型（如 男声、女声、混声、无人声）

steps:
  - step: 1
    action: read_index
    path: INDEX.md
    purpose: 获取全局路由表，定位风格和情绪对应路径
  - step: 2
    action: read_genre
    path: "genres/<genre>/README.md"
    purpose: 获取风格核心参数（BPM、调式、乐器、和弦进行、歌曲结构）
    fallback: genres/INDEX.md
  - step: 3
    action: read_mood
    path: "moods/<mood>.md"
    purpose: 获取情绪化编曲建议与推荐关键词
    fallback: moods/INDEX.md
  - step: 4
    action: read_template
    path: templates/style_prompts/INDEX.md
    purpose: 选取最匹配的 StylePrompt 模版
  - step: 5
    action: read_template
    path: templates/lyrics/INDEX.md
    purpose: 选取歌词结构模版
  - step: 6
    action: synthesize
    purpose: 整合以上内容，生成符合 output_schema 的完整创作方案

output_schema:
  format: markdown
  sections:
    - 基本信息（风格、情绪、BPM、调式、时长）
    - StylePrompt（英文，逗号分隔标签，可直接用于 Suno/Udio）
    - 歌词结构（段落说明）
    - 歌词示例（含 [Verse] [Chorus] 等标注）
    - 编曲建议（主奏乐器、节奏、和弦进行、音效）
    - 可调整方向（3条建议）
```

---

### skill_lookup_genre

```yaml
id: skill_lookup_genre
name: 检索风格知识
description: >
  查询指定音乐风格的核心参数、编曲规则、常用和弦进行和 StylePrompt 标签。
  适用于用户仅询问某种风格特征，而非需要完整创作方案的场景。

trigger_keywords:
  - …风格的特点是什么
  - …风格怎么编曲
  - Pop / Rock / Jazz / EDM / 嘻哈 / R&B / 合唱 / 民谣 / 乡村 / 拉丁 的参数
  - 介绍一下…风格

inputs:
  - name: genre
    type: string
    required: true
    description: 目标风格名称
    enum:
      - Pop
      - Rock
      - Classical
      - Jazz
      - EDM
      - Hip-Hop
      - R&B
      - Choral
      - Folk
      - Country
      - Latin

steps:
  - step: 1
    action: read_index
    path: genres/INDEX.md
    purpose: 获取风格路径映射
  - step: 2
    action: read_genre
    path: "genres/<genre>/README.md"
    purpose: 读取完整风格知识

output_schema:
  format: markdown
  sections:
    - 核心特征
    - 基础参数（BPM、调式、常用调性）
    - 典型乐器配置
    - 常用和弦进行
    - StylePrompt 推荐标签
    - 子风格列表（如有）
```

---

### skill_lookup_mood

```yaml
id: skill_lookup_mood
name: 检索情绪映射
description: >
  根据情绪关键词，查询适合该情绪的音乐风格、编曲建议和 StylePrompt 关键词。

trigger_keywords:
  - 我想要一首…情绪的歌
  - 什么风格适合…感觉
  - 开心/悲伤/激昂/平静/浪漫 的音乐怎么做
  - mood: happy / sad / energetic / calm / romantic

inputs:
  - name: mood
    type: string
    required: true
    description: 目标情绪
    enum:
      - happy
      - sad
      - energetic
      - calm
      - romantic

steps:
  - step: 1
    action: read_index
    path: moods/INDEX.md
    purpose: 获取情绪→风格推荐
  - step: 2
    action: read_mood
    path: "moods/<mood>.md"
    purpose: 获取详细情绪编曲建议

output_schema:
  format: markdown
  sections:
    - 情绪特征描述
    - 推荐音乐风格（首选 + 备选）
    - 编曲建议（速度、调性、音色、氛围）
    - StylePrompt 关键词
    - 歌词创作建议
```

---

### skill_generate_style_prompt

```yaml
id: skill_generate_style_prompt
name: 生成 StylePrompt
description: >
  根据用户需求，生成可直接粘贴到 Suno / Udio 等 AI 作曲平台的英文 StylePrompt。
  StylePrompt 应包含风格标签、情绪标签、乐器、人声类型、BPM、音效描述等。

trigger_keywords:
  - 生成 Suno Prompt
  - 帮我写 StylePrompt
  - 给我一个 Prompt 用于 Suno
  - Udio prompt
  - generate style prompt

inputs:
  - name: genre
    type: string
    required: true
    description: 音乐风格
  - name: mood
    type: string
    required: false
    description: 情绪
  - name: vocal_type
    type: string
    required: false
    description: 人声类型（male vocal / female vocal / choir / instrumental）
  - name: bpm
    type: string
    required: false
    description: 目标 BPM（可为数值如 120，也可为范围如 100–130 或描述如 fast / slow）
  - name: extra_tags
    type: string
    required: false
    description: 用户补充的自定义标签（逗号分隔）

steps:
  - step: 1
    action: read_template
    path: templates/style_prompts/INDEX.md
    purpose: 选取最匹配的基础 StylePrompt 模版
  - step: 2
    action: read_genre
    path: "genres/<genre>/README.md"
    purpose: 获取该风格推荐的 StylePrompt 标签列表
  - step: 3
    action: read_mood
    path: "moods/<mood>.md"
    purpose: 获取情绪化 StylePrompt 关键词（如适用）
  - step: 4
    action: synthesize
    purpose: 组合所有标签，生成最终 StylePrompt 字符串

output_schema:
  format: plain_text
  language: English
  description: >
    一行英文逗号分隔的标签字符串，可直接粘贴到 Suno Custom Mode 的 Style 输入框。
  example: >
    pop, female vocal, piano, soft drums, 110 BPM, emotional, heartbreak,
    melodic, polished production, radio-friendly
```

---

### skill_generate_lyrics_template

```yaml
id: skill_generate_lyrics_template
name: 生成歌词结构模版
description: >
  根据风格、情绪和主题，生成带 [Verse] [Pre-Chorus] [Chorus] [Bridge] 等段落
  标注的歌词框架或完整歌词示例。

trigger_keywords:
  - 帮我写歌词
  - 生成歌词框架
  - 歌词模版
  - 写一段副歌
  - lyrics template
  - write lyrics

inputs:
  - name: genre
    type: string
    required: false
    description: 音乐风格
  - name: mood
    type: string
    required: false
    description: 情绪
  - name: theme
    type: string
    required: true
    description: 歌曲主题（如 失恋、励志、思乡）
  - name: language
    type: string
    required: false
    default: 中文
    description: 歌词语言（中文 / English / 双语）
  - name: structure
    type: string
    required: false
    description: 指定歌曲结构（如 Verse-Chorus、ABABCB、带 Bridge）

steps:
  - step: 1
    action: read_template
    path: templates/lyrics/INDEX.md
    purpose: 选取匹配的歌词结构模版
  - step: 2
    action: read_genre
    path: "genres/<genre>/README.md"
    purpose: 参考该风格的标准歌曲结构（如有）
  - step: 3
    action: synthesize
    purpose: 生成带段落标注的完整歌词

output_schema:
  format: markdown
  requirements:
    - 每段开头使用 [Verse 1] / [Pre-Chorus] / [Chorus] / [Bridge] / [Outro] 等标注
    - 歌词需与主题、情绪一致
    - 副歌需具有记忆点，便于传唱
    - Suno v5.5 兼容格式（括号内可补充演唱指示，如 (soft) (powerful)）
```

---

### skill_lookup_theory

```yaml
id: skill_lookup_theory
name: 查询音乐理论
description: >
  查询和弦进行、音阶调式、歌曲结构等音乐理论知识，适用于用户有具体理论问题
  或需要深度理论支撑的场景。

trigger_keywords:
  - 什么是…和弦进行
  - 推荐几个和弦
  - I-V-vi-IV 是什么
  - 大调/小调/五声音阶
  - 歌曲结构怎么安排
  - 什么是 Bridge
  - chord progression / scale / song structure

inputs:
  - name: topic
    type: string
    required: true
    description: 查询主题
    enum:
      - chord_progressions
      - scales
      - song_structure

steps:
  - step: 1
    action: read_theory
    path: "theory/<topic>.md"
    purpose: 读取对应理论知识文件
  - step: 2
    action: read_index
    path: theory/INDEX.md
    purpose: 若未命中，获取理论模块全局索引

output_schema:
  format: markdown
  sections:
    - 理论概念说明
    - 常用示例（和弦进行 / 音阶 / 结构图示）
    - 适用风格场景
    - 相关资源链接（知识库内部）
```

---

### skill_suno_workflow

```yaml
id: skill_suno_workflow
name: Suno 创作工作流
description: >
  指导用户在 Suno.ai（v5.5）平台上完成从 StylePrompt 输入到歌曲精调的完整创作流程。
  包含 Custom Mode、ReMi 歌词生成、Song Editor 工具（Replace Section / Extend / Crop）的使用。

trigger_keywords:
  - 怎么在 Suno 上用
  - Suno 怎么操作
  - Suno v5.5 功能
  - Custom Mode 怎么填
  - ReMi 是什么
  - Replace Section / Extend / Crop 怎么用

inputs:
  - name: task
    type: string
    required: false
    description: 具体操作任务（如 生成歌曲 / 编辑已有歌曲 / 使用 ReMi 生成歌词）

steps:
  - step: 1
    action: read_guide
    path: tools/suno_v5.5_guide.md
    purpose: 读取 Suno v5.5 完整操作指南

output_schema:
  format: markdown
  sections:
    - 推荐操作步骤（分阶段说明）
    - 涉及功能的使用要点
    - 常见问题与注意事项
```

---

## 🔗 技能依赖关系图

```
skill_generate_music_plan（顶层综合技能）
├── skill_lookup_genre        → genres/<genre>/README.md
├── skill_lookup_mood         → moods/<mood>.md
├── skill_generate_style_prompt → templates/style_prompts/
├── skill_generate_lyrics_template → templates/lyrics/
└── skill_lookup_theory       → theory/（按需）

skill_suno_workflow（独立平台操作技能）
└── tools/suno_v5.5_guide.md
```

---

## 🚀 Agent 快速集成示例

### LangChain / AutoGen 集成思路

```python
# 伪代码：Agent 读取本文件后的技能注册逻辑
skills = parse_skill_harness("tools/skill_harness.md")

for skill in skills:
    agent.register_tool(
        name=skill.id,
        description=skill.description,
        trigger_keywords=skill.trigger_keywords,
        handler=lambda inputs, steps=skill.steps: execute_steps(steps, inputs)
    )
```

### GitHub Copilot Extensions 集成思路

```json
{
  "skills": [
    {
      "id": "skill_generate_music_plan",
      "description": "根据风格+情绪生成完整音乐创作方案",
      "parameters": {
        "genre": { "type": "string", "required": false },
        "mood":  { "type": "string", "required": false },
        "theme": { "type": "string", "required": false }
      }
    }
  ]
}
```

### System Prompt 直接引用（无代码集成）

在 System Prompt 中加入以下内容，Agent 即可自主使用本 Harness：

```
你是一位 AI 音乐创作助手。可用技能和调用规则定义在：
[知识库链接]/tools/skill_harness.md

处理用户请求时：
1. 读取 skill_harness.md 中的 trigger_keywords，匹配最相关的技能
2. 按该技能的 steps 顺序读取对应知识库文件
3. 按该技能的 output_schema 格式化输出
```

---

## 📎 关联资源

| 文件 | 说明 |
|---|---|
| `INDEX.md` | 知识库全局路由索引（LLM 主入口） |
| `QUICK_START.md` | LLM 快速使用指南（人工检索流程） |
| `tools/llm_guide.md` | LLM 调用本库的详细说明 |
| `tools/suno_v5.5_guide.md` | Suno v5.5 平台创作指南 |
| `genres/INDEX.md` | 音乐风格总索引 |
| `moods/INDEX.md` | 情绪/场景映射总索引 |
| `templates/style_prompts/INDEX.md` | StylePrompt 模版索引 |
| `templates/lyrics/INDEX.md` | 歌词结构模版索引 |
| `theory/INDEX.md` | 音乐理论知识索引 |

