# 🎨 StylePrompt 模版库 — 总索引

> StylePrompt 是用于 Suno、Udio 等 AI 作曲平台的**风格描述提示词**，为英文，逗号分隔的标签组合。  
> LLM 根据用户需求选取最匹配的模版，并在此基础上做个性化调整。

---

## 模版速查表

| 文件名 | 风格 | 情绪 | 人声 |
|---|---|---|---|
| `pop_upbeat.md` | Pop | 欢快/积极 | 任意 |
| `pop_sad_female.md` | Pop Ballad | 悲伤 | 女声 |
| `pop_romantic.md` | Pop | 浪漫 | 任意 |
| `rock_energetic.md` | Rock | 激昂 | 男声 |
| `edm_drop.md` | EDM | 激昂/派对 | 可选 |
| `hiphop_trap.md` | Hip-Hop Trap | 暗沉/力量 | 男声说唱 |
| `lofi_chill.md` | Lo-fi Hip-Hop | 平静/学习 | 无人声 |
| `rnb_soulful.md` | R&B | 浪漫/深情 | 女声 |
| `folk_acoustic.md` | Folk | 平静/治愈 | 任意 |
| `classical_neo.md` | Neo-Classical | 平静/电影感 | 无人声 |
| `jazz_smooth.md` | Smooth Jazz | 浪漫/放松 | 可选 |
| `chinese_pop.md` | 华语流行 | 通用 | 中文人声 |
| `epic_orchestral.md` | 史诗交响 | 激昂/电影感 | 无人声 |
| `choral_symphonic.md` | 交响大合唱 | 庄严/史诗/号召 | 混声合唱 |

---

## StylePrompt 通用构成规则

```
[核心风格] + [子风格/时代] + [BPM] BPM + [人声描述] + [主要乐器] + 
[情绪标签] + [制作风格] + [参考艺人（可选）]
```

---

## 通用修饰词汇表

**情绪类：**
```
upbeat, melancholic, romantic, aggressive, peaceful, nostalgic,
dreamy, dark, bright, emotional, epic, euphoric, intimate
```

**制作质感：**
```
lo-fi, hi-fi, polished, raw, organic, cinematic, vintage, modern,
minimalist, layered, atmospheric, lush, sparse
```

**人声类：**
```
male vocals, female vocals, duet, choir, no lyrics, instrumental,
rap vocals, soulful vocals, whispered vocals, falsetto
```

**乐器类：**
```
piano, acoustic guitar, electric guitar, violin, synthesizer,
drums, bass guitar, saxophone, trumpet, strings, orchestra
```

---

> 如需添加新模版：创建新 `.md` 文件，遵循已有格式，并在本文件的表格中追加一行。
