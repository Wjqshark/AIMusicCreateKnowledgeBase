# 🎼 合唱音乐 (Choral)

## 核心定位

合唱音乐以**多人共同发声**为核心，强调声部分层、群体推进和空间规模感。
在 AI 创作场景中，合唱并不只是“背景和声”，而应作为主叙事主体。

---

## 适用场景

- 交响大合唱 / 舞台史诗
- 电影与游戏的仪式感段落
- 群体宣言、史诗抒情、宏大叙事
- 宗教感、圣咏感、纪念性作品

---

## 基础参数（常见区间）

| 参数 | 典型值 |
|---|---|
| BPM | 60–120（庄严） / 120–150（推进） |
| 常见拍号 | 4/4、3/4、6/8 |
| 常见调式 | 小调（史诗/悲壮）、大调（号召/辉煌） |
| 编制 | 混声合唱 + 交响乐（弦乐、铜管、定音鼓、管风琴） |

---

## AI 创作关键原则

1. **合唱本体前置**：避免“独唱 + 背景垫声”的误判。
2. **三层分工明确**：低声部稳重心，中声部做连接，高声部托空间。
3. **段落递进而非全程满铺**：主歌克制，副歌扩张，终副歌全开。
4. **结果导向写法**：优先描述“听感纹理”，少写传统总谱术语。

---

## 推荐关联资源

- Suno V5.5 大合唱实操手册：`suno_v55_choral_creation_guide.md`
- 风格提示词模板库：`../../templates/style_prompts/INDEX.md`
- 建议模板：`../../templates/style_prompts/choral_symphonic.md`
- 歌词结构模板：`../../templates/lyrics/INDEX.md`
- 古典与交响基础：`../classical/README.md`

---

## 快速起步（LLM）

1. 先读取 `suno_v55_choral_creation_guide.md` 获取分层策略。
2. 读取 `../../templates/style_prompts/choral_symphonic.md` 生成 StylePrompt。
3. 从 `../../templates/lyrics/INDEX.md` 选结构（建议 anthem / ballad 变体）。
4. 如目标是 Suno，优先采用：Style + Lyrics 结构标签 + Exclude + Replace Section。
