# StylePrompt 模版：交响大合唱 (Symphonic Choral)

## 适用场景

- 风格：交响大合唱、史诗舞台合唱、仪式感段落
- 情绪：庄严、悲壮、号召、史诗
- 人声：混声合唱主导（弱化独唱）
- 平台：Suno v5/v5.5、Udio

---

## 基础模版

```text
grand symphonic choral anthem, massive mixed choir, choir itself is the lead, no dominant solo lead, layered harmonies, polyphonic choral texture, deep bass choir foundation, soaring soprano layer, symphonic strings, brass and timpani, pipe organ, large hall reverb, solemn and heroic, [BPM] BPM
```

---

## 变体模版

### 中国史诗向（民族交响感）

```text
Grand Chinese symphonic choral anthem, massive mixed choir, no dominant solo lead, full male choir and female upper harmonies, layered choral texture, polyphonic inner voices, dense block harmony, octave doubling, deep bass choir foundation, soaring soprano layer, cathedral-scale reverb, pipe organ, symphonic strings, brass, timpani, bass drum, solemn and heroic, monumental finale
```

### 宗教/圣咏向（庄严空间）

```text
sacred symphonic choir, mixed choir in cathedral, no featured soloist, antiphonal responses, upper voices sustain, low bass pedal tone, organ and strings, slow ceremonial pulse, huge reverberant hall, solemn, transcendent, 72 BPM
```

### 进攻/战役向（强推进）

```text
epic battle choir, strong mixed chorus, dense layered harmonies, rhythmic lower male choir, upper soprano sustained notes, brass heavy orchestration, aggressive timpani and bass drum, cinematic, monumental, 132 BPM
```

---

## Exclude（建议排除）

```text
solo singer, featured lead vocal, intimate close-mic vocal, whisper vocal, rap, ad-libs, pop melisma, vocal runs, trap hi-hats, EDM drop
```

---

## 使用建议

1. 先用基础模版确定“合唱前置”是否成立。
2. 再按目标切换变体（史诗/圣咏/战役）。
3. 若结果偏独唱，增加：`choir itself is the lead`, `less solo presence`。
4. 若结果层次不够，增加：`soprano alto tenor bass separation`, `middle-voice movement`。

---

## 关联资源

- 合唱风格入口：`../../genres/choral/README.md`
- Suno V5.5 合唱方法：`../../genres/choral/suno_v55_choral_creation_guide.md`
