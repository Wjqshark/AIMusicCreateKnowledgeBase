# 🎵 AI音乐创作知识库 — 主索引 (LLM Navigation Index)

> **面向大模型的导航入口。所有 AI 工具请从本文件开始读取，根据用户需求按索引跳转对应模块。**

---

## 📌 知识库用途

本知识库帮助 LLM（如 ChatGPT、DeepSeek、豆包等）：
1. 根据用户的**音乐风格/情绪/场景**需求，检索匹配的作曲规则
2. 生成符合库内规范的 **StylePrompt**（用于 Suno / Udio 等 AI 作曲平台）
3. 生成结构完整的**歌词模版（Lyrics Template）**
4. 输出可二次修改的完整创作方案

---

## 🗺️ 目录结构总览

```
AIMusicCreateKnowledgeBase/
├── INDEX.md                     ← 你在这里（LLM 主入口）
├── README.md                    ← 项目说明（人类阅读）
├── QUICK_START.md               ← LLM 快速使用指南
│
├── genres/                      ← 音乐风格知识库
│   ├── INDEX.md                 ← 风格索引
│   ├── pop/                     ← 流行
│   ├── rock/                    ← 摇滚
│   ├── classical/               ← 古典
│   ├── jazz/                    ← 爵士
│   ├── edm/                     ← 电子舞曲
│   ├── hiphop/                  ← 嘻哈/Rap（Hip-Hop & Rap）
│   ├── rnb/                     ← R&B/灵魂乐
│   ├── choral/                  ← 合唱（交响大合唱/多声部）
│   ├── folk/                    ← 民谣
│   ├── country/                 ← 乡村
│   └── latin/                   ← 拉丁
│
├── templates/                   ← 模版库
│   ├── style_prompts/           ← StylePrompt 模版（供 Suno/Udio 使用）
│   │   └── INDEX.md
│   └── lyrics/                  ← 歌词结构模版
│       └── INDEX.md
│
├── theory/                      ← 音乐理论知识
│   ├── INDEX.md
│   ├── chord_progressions.md    ← 常用和弦进行
│   ├── scales.md                ← 音阶与调式
│   └── song_structure.md        ← 歌曲结构
│
├── moods/                       ← 情绪/场景映射
│   ├── INDEX.md
│   ├── happy.md
│   ├── sad.md
│   ├── energetic.md
│   ├── calm.md
│   └── romantic.md
│
└── tools/
    ├── llm_guide.md             ← LLM 调用本库的详细说明
    ├── skill_harness.md         ← Agent 技能调用入口（Harness 模式）⭐
    └── suno_v5.5_guide.md       ← Suno v5.5 平台创作指南
```

---

## 🔍 快速检索路由表（LLM 按需跳转）

| 用户需求关键词 | 跳转路径 |
|---|---|
| 流行、pop、情歌、榜单 | `genres/pop/README.md` |
| 摇滚、rock、电吉他、朋克 | `genres/rock/README.md` |
| 古典、钢琴曲、弦乐、交响 | `genres/classical/README.md` |
| 爵士、jazz、即兴、蓝调 | `genres/jazz/README.md` |
| 电音、EDM、舞曲、House、Trance | `genres/edm/README.md` |
| 嘻哈、hiphop、hip-hop、rap、说唱、trap、drill | `genres/hiphop/README.md` |
| R&B、灵魂乐、Soul、Neo-Soul | `genres/rnb/README.md` |
| 合唱、choral、大合唱、交响合唱、多人合唱、多声部 | `genres/choral/README.md` |
| 民谣、folk、吉他弹唱、治愈 | `genres/folk/README.md` |
| 乡村、country、Nashville | `genres/country/README.md` |
| 拉丁、Latin、Reggaeton、Bossa Nova | `genres/latin/README.md` |
| 和弦、chord、和声、进行 | `theory/chord_progressions.md` |
| 音阶、调式、scale、key | `theory/scales.md` |
| 歌曲结构、verse、chorus、bridge | `theory/song_structure.md` |
| 开心、快乐、欢快、energetic | `moods/happy.md` 或 `moods/energetic.md` |
| 悲伤、忧郁、失落 | `moods/sad.md` |
| 平静、治愈、放松 | `moods/calm.md` |
| 浪漫、爱情、温柔 | `moods/romantic.md` |
| StylePrompt 模版、Suno prompt | `templates/style_prompts/INDEX.md` |
| 歌词模版、Lyrics 结构 | `templates/lyrics/INDEX.md` |
| 如何使用本库（LLM 操作手册） | `tools/llm_guide.md` |
| Agent 技能调用入口（Harness 模式） | `tools/skill_harness.md` |

---

## 🧩 扩展说明

- **添加新风格**：在 `genres/` 下新建文件夹，并遵循已有 `README.md` 格式
- **添加新模版**：在 `templates/style_prompts/` 或 `templates/lyrics/` 下添加 `.md` 文件，并更新对应 `INDEX.md`
- **添加新情绪**：在 `moods/` 下新建文件，并更新 `moods/INDEX.md`

> 本库遵循「一文件一知识点」原则，每个 Markdown 文件均包含 LLM 可直接读取的结构化内容。
