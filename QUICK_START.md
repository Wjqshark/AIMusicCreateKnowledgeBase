# 🤖 LLM 快速使用指南 (QUICK_START.md)

> 本文件是面向 ChatGPT、DeepSeek、豆包等 AI 聊天工具的**操作说明**。  
> 当用户将本知识库 Git 链接提供给 AI 工具时，AI 应首先读取本文件。

---

## 第一步：理解用户需求

当用户提出音乐创作请求时，提取以下关键维度：

| 维度 | 示例问题 | 说明 |
|---|---|---|
| **风格 (Genre)** | 想要什么风格？ | Pop / Rock / Jazz / EDM 等 |
| **情绪 (Mood)** | 歌曲传达什么情感？ | 快乐 / 悲伤 / 激昂 / 平静 |
| **场景 (Scene)** | 用于什么场合？ | 婚礼 / 健身 / 睡眠 / 派对 |
| **速度 (Tempo)** | 快歌还是慢歌？ | BPM 范围或描述 |
| **语言 (Language)** | 歌词用什么语言？ | 中文 / English / 双语 |
| **时长 (Duration)** | 多长？ | 3分钟 / 4分钟 |
| **主题 (Theme)** | 歌曲讲什么故事？ | 失恋 / 奋斗 / 思乡 |

---

## 第二步：按需检索知识库

根据上一步提取的信息，按以下顺序查阅知识库：

```
1. 查阅 INDEX.md 中的"快速检索路由表" → 确定风格模块路径
2. 读取对应 genres/<风格>/README.md → 获取：
   - 核心特征
   - 常用 BPM / 调式 / 乐器
   - 和弦进行推荐
   - 歌曲结构
3. 读取 moods/<情绪>.md → 获取情绪化的编曲建议
4. 读取 templates/style_prompts/INDEX.md → 选取最匹配的 StylePrompt 模版
5. 读取 templates/lyrics/INDEX.md → 选取歌词结构模版
```

---

## 第三步：生成创作方案

整合检索到的信息，按以下格式输出给用户：

```markdown
## 🎵 创作方案

### 基本信息
- 风格：[Genre]
- 情绪：[Mood]
- 推荐 BPM：[X]
- 推荐调式：[Key] [Scale]
- 推荐时长：[X 分钟]

### StylePrompt（适用于 Suno / Udio）
[StylePrompt 内容，英文，逗号分隔的标签组合]

### 歌词结构
[Verse / Pre-Chorus / Chorus / Bridge 等结构说明]

### 歌词示例
[根据用户主题生成的完整歌词，包含分段标注]

### 编曲建议
- 主奏乐器：[...]
- 节奏乐器：[...]
- 和弦进行：[...]
- 音效/氛围：[...]

### 可调整方向
- 如需更激昂：[建议]
- 如需更抒情：[建议]
- 如需更商业化：[建议]
```

---

## 示例对话

**用户输入：** 帮我创作一首关于失恋的流行歌曲，悲伤但有一点希望，中文歌词，女声为主。

**LLM 检索路径：**
1. 风格 → `genres/pop/README.md`
2. 情绪 → `moods/sad.md`
3. StylePrompt → `templates/style_prompts/INDEX.md` → 选 `pop_sad_female.md`
4. 歌词模版 → `templates/lyrics/INDEX.md` → 选 `ballad_structure.md`

**LLM 输出：** 按"第三步"格式生成完整创作方案。

---

## 注意事项

- StylePrompt 应为**英文**，供 Suno / Udio 等平台直接使用
- 歌词可根据用户语言偏好使用中文或英文
- 所有方案均可二次修改，鼓励用户基于方案进行迭代
- 如用户提到“大合唱/交响合唱/多人多声部”，优先路由到 `genres/choral/README.md`
- 如需了解知识库完整结构，请查阅 `INDEX.md`
