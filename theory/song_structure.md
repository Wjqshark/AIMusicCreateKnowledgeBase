# 🏗️ 歌曲结构 (Song Structure)

## 常见段落术语

| 英文术语 | 中文 | 功能 |
|---|---|---|
| Intro | 前奏 | 建立氛围，引入主题 |
| Verse | 主歌 | 叙事，每段歌词不同 |
| Pre-Chorus | 预副歌 | 情绪过渡，为副歌铺垫 |
| Chorus | 副歌 | 全曲核心，最强记忆点，歌词重复 |
| Post-Chorus | 后副歌 | 副歌后的短暂延伸或强化 |
| Bridge | 桥段/中八 | 情绪转折，打破重复感 |
| Outro | 尾奏 | 收尾，淡出或强收 |
| Instrumental Break | 器乐间奏 | 独奏或过渡段 |
| Solo | 独奏 | 器乐炫技段（吉他独奏等）|
| Hook | 钩子/记忆点 | 最抓耳的旋律或句子 |

---

## 标准流行结构（主流）

```
Intro (4–8 小节)
→ Verse 1 (8–16 小节)
→ Pre-Chorus (4–8 小节)
→ Chorus (8–16 小节)
→ Verse 2 (8–16 小节)
→ Pre-Chorus (4–8 小节)
→ Chorus (8–16 小节)
→ Bridge (8–16 小节)
→ Chorus x2 (最终高潮)
→ Outro (4–8 小节)
```
**总时长约：** 3:30 – 4:00

---

## 简化版（适合 Suno / Udio 生成）

```
[Verse]
[Chorus]
[Verse]
[Chorus]
[Bridge]
[Chorus]
```

---

## 各段落写作指南

### Verse（主歌）
- 每段歌词内容不同（Verse 1 ≠ Verse 2）
- 叙事性：建立故事、场景、人物
- 情绪上比副歌低一级
- 旋律相对平稳，为副歌留空间

### Pre-Chorus（预副歌）
- 可选但有效
- 歌词通常有"上升/过渡"感
- 和弦进行制造悬念
- 例：副歌和弦的反转或属和弦停留

### Chorus（副歌）
- 歌曲标题/主旨句通常在此
- 每次出现歌词基本相同
- 旋律最高点或最抓耳处
- 编曲最厚、情感最强
- 长度：通常 8 小节（4 个乐句）

### Bridge（桥段）
- 只出现一次（通常在两遍副歌之后）
- 歌词提供新视角或情绪反转
- 调性可借用（平行小调/大调）
- 编曲可以减薄再放大（Drop & Build）

### Intro & Outro
- **Intro**：通常用器乐，建立情绪，不要太长（4–8小节）
- **Outro**：可以是副歌循环淡出，也可以是返回 Intro 主题收尾

---

## 特殊结构类型

### 民谣/故事结构
```
Verse – Verse – Chorus – Verse – Chorus – Verse – Chorus
（无 Bridge，Verse 更重要，故事连贯性强）
```

### 爵士头尾结构
```
Head（主题）– Solo 1 – Solo 2 – Head Out
（AABA 或 12小节蓝调循环）
```

### EDM Drop 结构
```
Intro – Build-Up – Drop – Break – Build-Up – Drop – Outro
（无传统 Verse/Chorus 概念）
```

### Hip-Hop 结构
```
Intro – Hook – Verse – Hook – Verse – Hook – [Bridge] – Hook – Outro
（Hook = 副歌概念，Verse = 说唱）
```

---

## StylePrompt 结构标签

在 Suno/Udio 中，可用如下标签控制结构：
```
[Intro], [Verse], [Pre-Chorus], [Chorus], [Bridge], [Outro],
[Guitar Solo], [Instrumental Break], [Hook]
```

---

## 关联资源

- 歌词模版 → `../templates/lyrics/INDEX.md`
- 各风格结构 → `../genres/`
