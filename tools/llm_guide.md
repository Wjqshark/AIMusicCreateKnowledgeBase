# 🤖 LLM 调用本知识库的详细说明 (llm_guide.md)

> 本文件面向 AI 开发者和高级用户，说明如何将本知识库集成到 AI 对话工作流中。

---

## 一、知识库设计原则

本库遵循以下设计原则，使 LLM 能高效读取：

1. **一文件一知识点** — 每个 `.md` 文件专注单一主题，避免信息混杂
2. **多层索引设计** — `INDEX.md` 文件提供各层级导航，LLM 只需读取索引即可定位资源
3. **结构化内容** — 大量使用 Markdown 表格、代码块，便于 LLM 解析提取
4. **内部交叉引用** — 每个文件末尾有"关联资源"，引导 LLM 进行扩展检索
5. **可扩展架构** — 新增内容只需新建文件并更新对应 `INDEX.md`

---

## 二、推荐的 LLM System Prompt

将以下内容添加到 System Prompt（或用户首次消息）中：

```
你是一位专业的 AI 音乐创作助手，拥有以下知识库访问权限：
[知识库 GitHub 链接]

当用户提出音乐创作需求时，你应该：
1. 首先阅读知识库的 QUICK_START.md 了解操作流程
2. 根据 INDEX.md 的路由表，定位相关的风格、情绪、模版文件
3. 综合所读内容，按 QUICK_START.md 中定义的"创作方案"格式输出

输出格式必须包含：
- 基本信息（风格、BPM、调式）
- StylePrompt（英文，可直接粘贴到 Suno/Udio）
- 歌词（中文或用户指定语言，含段落标注）
- 编曲建议
- 可调整方向（给用户后续修改的提示）
```

---

## 三、知识库文件读取优先级

当 LLM 面临不确定性时，按以下优先级读取文件：

```
第1优先级: INDEX.md（根目录）— 全局路由
第2优先级: QUICK_START.md — 操作流程
第3优先级: genres/<风格>/README.md — 风格知识
第4优先级: moods/<情绪>.md — 情绪修饰
第5优先级: templates/style_prompts/<模版>.md — StylePrompt
第6优先级: templates/lyrics/<模版>.md — 歌词结构
第7优先级: theory/*.md — 深度理论（必要时）
```

---

## 四、不同 AI 平台的集成方式

### ChatGPT (GPT-4/o)
- 使用 Code Interpreter 插件，让 ChatGPT 直接读取 GitHub raw 链接
- 或将关键文件内容粘贴到对话中

### Claude (Anthropic)
- Claude 支持长上下文，可以一次性提供多个知识库文件内容
- 建议提供 INDEX.md + 相关风格/情绪文件

### DeepSeek
- 在系统提示中提供知识库的 GitHub 链接
- 要求 DeepSeek 在回答前先读取对应文件

### 豆包 (Doubao)
- 使用豆包的文件上传功能，上传对应 `.md` 文件
- 或通过 API 将文件内容注入对话

### 自建 RAG 系统
- 将所有 `.md` 文件切片并向量化
- 在 `INDEX.md` 中的路由表可作为元数据过滤条件
- 建议切片粒度：每个二级标题（`##`）为一个切片

---

## 五、知识库扩展指南

### 添加新音乐风格
```
1. 在 genres/ 下新建文件夹（如 genres/bossa_nova/）
2. 创建 README.md，遵循已有风格文件的结构：
   - 核心特征
   - 基础参数（BPM、调式、时长）
   - 歌曲结构
   - 常用和弦进行
   - 典型乐器配置
   - 子风格
   - StylePrompt 推荐标签
   - 关联资源
3. 在 genres/INDEX.md 的表格中追加一行
4. 在根目录 INDEX.md 的路由表中追加条目
```

### 添加新 StylePrompt 模版
```
1. 在 templates/style_prompts/ 下新建 <名称>.md
2. 包含：适用场景、基础模版、变体模版、调整指南
3. 在 templates/style_prompts/INDEX.md 的表格追加一行
```

### 添加新歌词模版
```
1. 在 templates/lyrics/ 下新建 <名称>.md
2. 包含：适用风格、结构说明、中文示例、英文示例、使用说明
3. 在 templates/lyrics/INDEX.md 的表格追加一行
```

### 添加新情绪类型
```
1. 在 moods/ 下新建 <情绪>.md
2. 包含：情绪特征、编曲建议、推荐风格、歌词建议、StylePrompt 关键词
3. 在 moods/INDEX.md 的两个表格追加对应行
```

---

## 六、常见 LLM 误用纠正

| 误用行为 | 正确做法 |
|---|---|
| 直接生成创作方案，不查知识库 | 先读取对应风格/情绪文件 |
| StylePrompt 使用中文 | StylePrompt 必须为英文 |
| 歌词没有段落标注 | 必须标注 [Verse] [Chorus] 等 |
| 忽略用户的 BPM 需求 | 在 StylePrompt 中明确写 BPM |
| 不提供可调整方向 | 方案末尾必须给 3 个调整建议 |

---

## 七、版本与维护

- 本知识库采用 Git 版本管理
- 新增内容提交 Pull Request，更新对应 INDEX.md
- 废弃内容移至 `archive/` 文件夹（待建立），不直接删除
