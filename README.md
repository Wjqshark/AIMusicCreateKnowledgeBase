# 🎵 AIMusicCreateKnowledgeBase

**面向大模型（LLM）的可扩展 AI 音乐创作知识库**

> 让 ChatGPT、DeepSeek、豆包等 AI 聊天工具，通过本知识库的 Git 链接，直接检索适配的音乐作曲知识，并结合 StylePrompt 和 Lyrics 模版，为用户生成可二次修改的完整创作方案。

---

## 🚀 快速开始

**LLM 请从以下文件开始：**

| 文件 | 用途 |
|---|---|
| [`INDEX.md`](./INDEX.md) | 🗺️ 主导航索引（LLM 入口，路由表）|
| [`QUICK_START.md`](./QUICK_START.md) | ⚡ LLM 快速操作指南 |
| [`tools/llm_guide.md`](./tools/llm_guide.md) | 🔧 集成说明（System Prompt 示例）|
| [`tools/suno_v5.5_guide.md`](./tools/suno_v5.5_guide.md) | 🎤 Suno.ai 平台使用指南（v4.5 vs v5.5 对比、歌词进阶技巧）|

---

## 📁 知识库结构

```
AIMusicCreateKnowledgeBase/
├── INDEX.md              ← LLM 主入口（路由表）
├── QUICK_START.md        ← 操作流程指南
│
├── genres/               ← 11 种音乐风格知识
│   ├── pop/              流行
│   ├── rock/             摇滚
│   ├── classical/        古典
│   ├── jazz/             爵士
│   ├── edm/              电子舞曲
│   ├── hiphop/           嘻哈/Rap（Hip-Hop & Rap）
│   ├── rnb/              R&B
│   ├── choral/           合唱（交响大合唱/多声部）
│   ├── folk/             民谣
│   ├── country/          乡村
│   └── latin/            拉丁
│
├── templates/
│   ├── style_prompts/    ← 13 个 StylePrompt 模版（Suno/Udio 专用）
│   └── lyrics/           ← 5 个歌词结构模版（含中英文示例）
│
├── theory/               ← 音乐理论（和弦进行、音阶、歌曲结构）
├── moods/                ← 5 种情绪/场景映射
└── tools/                ← 集成与平台指南
   ├── llm_guide.md       LLM 集成与扩展指南
   └── suno_v5.5_guide.md Suno.ai 创作平台完全指南
```

---

## 🎯 支持的创作场景

- ✅ 流行情歌、悲伤失恋歌、励志歌曲
- ✅ 电子舞曲、嘻哈说唱、R&B 灵魂乐
- ✅ 交响大合唱、史诗合唱、多声部群体人声
- ✅ 中国民谣、国风古风音乐
- ✅ 器乐配乐（新古典、爵士、史诗交响）
- ✅ 多语言（中文/English）歌词创作
- ✅ 直接输出 Suno / Udio 专用 StylePrompt

---

## 🔧 如何集成到 AI 聊天工具

在 System Prompt 中加入：
```
你是专业 AI 音乐创作助手，知识库地址：[本仓库 GitHub 链接]
创作时请参考 QUICK_START.md 中的流程，输出 StylePrompt + 完整歌词 + 编曲建议。
```

详细集成说明见 [`tools/llm_guide.md`](./tools/llm_guide.md)

---

## 📦 扩展知识库

本库采用**可扩展架构**：

- **新增风格**：在 `genres/` 下新建文件夹，更新 `genres/INDEX.md`
- **新增模版**：在 `templates/` 对应子目录新建文件，更新对应 `INDEX.md`
- **新增情绪**：在 `moods/` 下新建文件，更新 `moods/INDEX.md`

详见 [`tools/llm_guide.md`](./tools/llm_guide.md) 第五节"知识库扩展指南"

---

## 📄 License

[LICENSE](./LICENSE)
