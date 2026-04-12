# 🎵 Suno v5.5 创作平台使用指南

> 专为本知识库用户设计，说明如何在 Suno.ai 上实现高效的音乐创作工作流

---

## 📌 版本对比：v4.5_all（免费）vs v5.5（付费）

### 歌词支持对比表

| 功能特性 | v4.5_all（Free） | v5.5（Pro/Premier） |
|---|---|---|
| **基础自写歌词** | ✅ 支持 | ✅ 支持 |
| **标签支持** `[Verse]` `[Chorus]` 等 | ✅ 基础支持 | ✅ **完整支持**（更敏感） |
| **ReMi 歌词生成** | ❌ 无 | ✅ 可用（Beta 功能） |
| **括号标注** `(soft)` `(rap)` | 🟡 部分识别 | ✅ **完全支持** |
| **标点符号敏感度** | 🟡 一般 | ✅ **高敏感**（感叹号、省略号等有明显效果） |
| **Replace Section** | ❌ 无 | ✅ 可用 |
| **Extend 功能** | ❌ 无 | ✅ 可用 |
| **Crop 功能** | ❌ 无 | ✅ 可用 |
| **音乐-歌词匹配精度** | 一般 | **非常高**（v5.5 能更好理解歌词意图） |
| **编辑工具** | 基础 | **专业级**（Song Editor） |
| **节奏感敏感性** | 基础 | **高度敏感**（短/长歌词节奏差异更明显） |

### 核心差异说明

#### 🆓 v4.5_all（免费版）的能力
- **能做什么**：
  - 输入自写歌词生成完整歌曲
  - 使用基础标签（`[Verse]`, `[Chorus]` 等）
  - 简单的格式化

- **局限性**：
  - 无法使用 ReMi 生成歌词
  - 无法编辑已生成的歌曲（只能重新生成）
  - 对标点、大小写、括号等的敏感度低
  - 不能微调歌词和音乐的关系

#### 💎 v5.5（付费版）的进阶能力
- **新增功能**：
  - ReMi AI 歌词生成模型（创意、可控）
  - Song Editor 完整编辑工具（Replace Section、Extend、Crop）
  - **高度敏感的歌词解析**（能理解括号标注、大写强调、标点节奏）
  - 更精准的音乐-歌词匹配（AI 真的听得懂你的歌词风格）

---

## 📌 Suno v5.5 核心更新（2026年3月）

### 三大创新功能

| 功能 | 说明 | 适用场景 |
|---|---|---|
| **Voices**（人声模型） | 融合你的声音特征，生成带有个人风格的演唱版本 | Pro/Premier | 需要统一声线的系列创作 |
| **Custom Models**（自定义模型） | 上传自己的音乐作品，让 v5.5 学习你的创作风格 | Pro/Premier (限3个) | 保持个人风格的延续性创作 |
| **My Taste**（个性化学习） | AI 根据你的偏好自动优化生成结果 | 所有用户 | 越用越懂你的创意喜好 |

---

## 🎤 歌词运用完全指南

### 一、歌词输入方式

#### 方式 1：自写歌词（Custom Mode）
**流程：**
1. 进入 Suno 创作页，选择 **Custom** 模式
2. 在 **Lyrics** 字段直接粘贴你的歌词
3. 支持标注歌词结构（见下表）

**歌词格式标准：**
```
[Verse]
写你的第一段歌词
每行一句或一小节

[Chorus]
副歌内容
这部分会重复

[Verse 2]
第二段歌词

[Bridge]
过渡部分（可选）

[Outro]
结尾部分（可选）
```

**关键点：**
- 标签（`[Verse]`, `[Chorus]` 等）会影响 AI 的生成风格
- 每个标签内的歌词长度决定该段落的时长
- 标签数量和顺序直接影响最终成曲

#### 方式 2：ReMi 歌词生成（AI 辅助生成）【仅 v5.5 可用】

**ReMi 是什么？**
- Suno 最新的歌词生成模型（2024年起提供）
- 名字来自音乐理论中的"Do Re Mi Fa Sol"
- 比经典模型更有创意、更"锋芒"

**使用 ReMi 生成歌词：**
1. **Custom Mode** → 在 Lyrics 字段找到 **"Write with Suno"** 按钮
2. 在弹出窗口中描述你想要的歌词主题，如：
   - `A sad love song about letting go（关于放手的伤感情歌）`
   - `Upbeat rap about chasing dreams（关于追梦的欢快说唱）`
   - `Tender acoustic love confession（温柔的原声情诗）`
3. 右侧下拉菜单选择模型：**ReMi** 或 **Classic**
4. 点击 **"Write Lyrics"**，AI 为你生成初稿

**优化 ReMi 生成的歌词：**
- 生成后不是最终版本，编辑空间很大
- 可以调整个别词汇、交换段落、删除或添加行
- 示例：原文"Love is a fire burning cold" → 改为"Love is a fire burning bright"
- **小技巧**：多次生成，对比选择最好的版本

#### 方式 3：混合式创作（部分自写 + 部分 AI 生成）
**最灵活的方法：**
1. 自己写好重要的段落（副歌、关键金句）
2. 用 ReMi 生成其他段落
3. 逐行精调整，形成统一的文风

---

### 二、歌词编辑工具（Song Editor）【仅 v5.5 Pro/Premier 可用】

Suno Song Editor 提供多种强大的编辑工具，用于精细化调整已生成的歌曲。

#### 工具 1：Replace Section（替换段落）
**用途：** 修改歌词或重新生成某个部分

**操作步骤：**
1. 已生成的歌曲 → 点击 **"..."** 菜单 → 选 **"Edit"**
2. 找到 **"Replace Section"** 选项
3. 在音乐编辑区点击拖拽选中要替换的段落
   - 原歌词会自动显示在左侧
   - 可在左侧直接修改歌词
4. 点击 **"Recreate Section"** 重新生成该部分
5. AI 会生成两个版本供对比，选择更喜欢的
6. 最后生成"整首歌曲"（Full Song）

**典型用法：**
- 改歌词但保留原旋律风格
- 改某个副歌的歌词
- 替换某段不满意的演唱

#### 工具 2：Extend（延长歌曲）
**用途：** 为歌曲添加新段落或改变结尾

**操作步骤：**
1. 歌曲菜单 → **"Remix/Edit"** → 选 **"Extend"**
2. 白色箭头控制截断点（从哪里开始延长）
3. 在文本框输入新歌词或风格描述
   - 可以写 `[Outro]` 加结尾
   - 可以写 `[Verse 3]` 加新段落
   - 或只写风格描述如 "make it fade out softly"
4. 点 **"Create"** 生成延长部分
5. 满意后选 **"Get Whole Song"** 将新旧部分自动接合成完整歌曲

**常见场景：**
- 歌曲太短，需要加到 2 分钟以上
- 想加一个新的过渡乐段（Bridge）
- 需要一个淡出结尾（Outro）

#### 工具 3：Crop（裁剪歌曲）
**用途：** 移除开头或结尾不需要的部分

**特点：**
- Pro / Premier 用户可用
- 简单直接地移除前或后的片段
- 同时保留完整的音乐质量

---

## 📝 WorkFlow：从创意到成品

### 典型创作流程（推荐方案）

```
第1步：创意阶段
├─ 确定歌曲风格/情绪
├─ 选择目标受众
└─ 准备歌词框架或主题描述

第2步：初稿生成
├─ 选 Custom Mode（允许更多控制）
├─ 输入歌词（自写 OR ReMi 生成 OR 混合）
├─ 填入其他参数（BPM、风格标签等）
└─ 点 Create 生成初版本

第3步：试听 & 评估
├─ 听生成的歌曲
├─ 记录需要调整的部分
│  ├─ 段落选择（如副歌不够亮眼）
│  ├─ 歌词表达（某句措辞不当）
│  └─ 总长度或结尾（需要加长/改结尾）
└─ 决定调整策略

第4步：精细编辑（可能多次）
├─ 用 Replace Section 改歌词或重生成段落
├─ 用 Extend 加新段落或改结尾
├─ 不满意就重新生成该部分
└─ 直到满意为止

第5步：生成完整版
├─ 所有段落都满意后
├─ 选 "Get Whole Song" 或 "Whole Song" 合成
└─ 导出 MP3/WAV

第6步：后期处理（可选）
├─ 如果是 Premier 用户，在 Studio 中
│  ├─ Remove FX 移除效果再自己加
│  ├─ 分离 Stems（12 条轨道）
│  └─ 混音/母带处理
└─ 或直接导出用于内容平台
```

---

## 🎯 歌词最佳实践

### 一、标签的力量与AI行为

#### 基础标签与其对音乐的影响

```
[Verse] — 讲述、故事、背景         → AI 用相对温和、清晰的旋律
[Chorus] — 重复、记忆点、核心情感  → AI 用更高的音调、更强的节奏
[Bridge] — 转折、高潮、情感爆发   → AI 用不同的乐器、节奏变化
[Outro] — 结束、淡出、反思         → AI 用渐弱、降速、和弦回归
[Pre-Chorus] — 铺垫、期待感        → AI 渐进上升的动态感
[Interlude] — 器乐段、过场         → 可放 "(instrumental section)"
```

**关键发现（v5.5 特性）：**
- `[Chorus]` 标签会让 AI 自动识别这是"重复段"，会在整首歌中保留一致性
- `[Verse 2]` / `[Verse 3]` 的编号让 AI 理解"进展"和"变化"
- 标签数量和长度比例会影响整曲节奏感

#### 标签顺序对成曲结构的影响

| 结构 | AI 理解 | 效果 |
|---|---|---|
| V-C-V-C-B-C | 标准流行 | 对称、容易记忆 |
| V-V-C-V-B-C-C | 缓慢上升 | 前半部分铺垫，后期高潮 |
| C-V-C-V-B-C | 副歌开场 | 立刻吸引、强记忆点 |
| V-C-V-C-C-C | 重复轰炸 | 中式洗脑流行 |

**进阶技巧：** 标签数量越多越"碎片化"，会让AI觉得这是"编织型"歌曲；标签越少越"流畅"。

---

### 二、歌词密度与音乐节奏的对话（核心机制）

这是 v5.5 的**关键机制**：歌词本身的物理特性会影响音乐节奏感。

#### 歌词长度对节奏的影响

**短歌词（每行 2-4 个单词）**
```
[Verse]
I lost you
In the rain
Can't find way
Back to pain
```
**AI 理解:** 快速、断裂感、摇滚/个性化
**结果:** BPM 感觉快，音符密集，容易产生 Rap/Punk 效果

**长歌词（每行 8-12 个单词）**
```
[Verse]
Looking back at all the memories we shared together
Every moment wrapped in golden warmth and endless laughter
Now the silence echoes where your voice once lived within me
```
**AI 理解:** 缓慢、流畅、抒情
**结果:** 同样 BPM 下，听起来更"宽松"，旋律更宽敞，适合弹唱歌

> **技巧：** 想要歌曲感觉快，用短歌词；想要优雅，用长句子

#### 重复结构的作用

v5.5 特别敏感于**行与行之间的重复**：

**无重复（完全不同的句子）**
```
The morning sun touches my face
Birds are singing in the trees
Shadows dance on the old brick wall
```
→ 音乐变化快，每句都有新乐句

**有重复（咒语式）**
```
I want you back
I want you back
I need you now
I need you now
```
→ AI 会生成"循环乐句"，形成洗脑感、说唱感、电子音乐感

**关键词重复**
```
Love, love, burning like fire
Love, love, taking me higher
```
→ 会生成"钩子"（hook），易于传播

> **实用技巧：** 副歌中故意重复某个短句，AI 会自动在伴奏中强调这个"咒语"

---

### 三、特殊标记与高级语法

#### 1. 使用括号标注发音/情感【v5.5 完全支持，v4.5 部分识别】

```
[Verse]
I saw you there (whisper voice)
Looking so fair (breathy)
Then you turned (dramatic pause)
And I just stared (soft)
```

**v5.5 对括号的理解：**
- `(soft)` / `(whisper)` — 降低音量和强度
- `(dramatic)` / `(powerful)` — 增加力度
- `(breathy)` / `(emotional)` — 增加表现力
- `(rap)` / `(spoken)` — 改变演唱方式

#### 2. 虚线/省略号的作用

```
[Chorus]
I'm falling... falling...
Into your eyes
Can't... can't...
Tell you goodbye
```

AI 会理解虚线为**"拉长音"的标记**，自动在这些位置加入颤音或延音。

#### 3. 大写字母与强调

```
[Chorus]
I LOVE YOU
More than words can say
I NEED YOU HERE
Every single day
```

大写字母会让 AI 在这些词上增加**音量、力度、或音高跳跃**。这是制造"高潮"的简单办法。

#### 4. 标点符号的细微影响【v5.5 高敏感，v4.5 基础】

在 **v5.5** 中，标点符号对音乐生成的影响明显提升：
|---|---|
| 句号 `.` | 普通结束，让 AI 稍微停顿 |
| 感叹号 `!` | 强调、能量爆发 |
| 问号 `?` | 疑问、音调上升 |
| 省略号 `...` | 拉长、音乐延伸 |
| 破折号 `--` | 戏剧性停顿 |
| 逗号 `,` | 短暂呼吸（小停顿） |

---

### 四、不同部分的歌词策略

#### [Verse]（叙事部分）
**最佳实践：**
- 用**具体意象**而非抽象概念
- 长句子（8-12词）营造"讲故事"感
- 避免过多重复（保留新鲜感）
- 理想长度：8-12 行（约 90-120 秒内容如果按标准 BPM）

**例子（中文）：**
```
在雨夜的街角 等待你出现
灯光模糊了 我想要的答案
你的身影渐行渐远 消失在夜色里
只留我一个人 感受这份冷
```

#### [Chorus]（记忆点）
**最佳实践：**
- 用**简短有力的句子**（3-6 词/行）
- 故意**重复关键词**（咒语模式）
- 全部大写或使用感叹号，制造"高能"
- 理想长度：4-8 行

**例子（英文）：**
```
[Chorus]
YOU AND ME!
MEANT TO BE!
In this dream
Together we are free
YOU AND ME!
MEANT TO BE!
```

#### [Bridge]（转折/高潮）
**最佳实践：**
- **完全改变风格**（从长句→短句，或反之）
- 可以**突然加入对白、吟诵或新的观点**
- 常用的技巧：从叙述改成"直接对话"
- 理想长度：4-6 行

**例子（转变风格）：**
```
[Verse - 长句子]
Looking at the world through different eyes now

[Bridge - 短句爆发]
STOP!
LOOK!
FEEL!
THIS IS REAL!
```

#### [Outro]（结尾）
**最佳实践：**
- 可以**重复副歌关键词**（循环感）
- 或用**新的、思考性的语句**（升华）
- 用 `(fade out)` / `(whisper)` 标记音量变化
- 理想长度：2-4 行

---

### 五、与 ReMi 合作的 Prompt 技巧

#### 好的 Prompt（足够具体）
- ✅ "Melancholic love song in English about memories fading away, piano-driven"
- ✅ "Upbeat hip-hop in Chinese about self-confidence and overcoming doubts"
- ✅ "Acoustic folk love ballad with Nature imagery and metaphors about seasons"
- ✅ "EDM anthem with repetitive chorus, female vocal, high energy"

#### 不好的 Prompt（太宽泛或模糊）
- ❌ "写一首歌" （完全没有方向）
- ❌ "Random song" （无法指导）
- ❌ "歌词很好听" （描述音乐而非歌词内容）
- ❌ "Love song" （太通用，ReMi 可能给你俗套结果）

#### ReMi 加强技巧
在描述前**加入特定要求**：
- `"...with wordplay and puns"` — 要求双关/文字游戏
- `"...dark and cynical tone"` — 要求黑暗/讽刺风格
- `"...include chorus repetition"` — 要求重复的副歌
- `"...poetic and metaphorical"` — 要求诗意/比喻

---

### 六、编辑生成歌词的黄金法则

#### 保留什么
- ✅ **核心意象**（好的比喻、独特的表达）
- ✅ **押韵结构**（如果原歌词的韵脚很好）
- ✅ **节奏模式**（行长的一致性）

#### 改进什么
- 🔄 **陈词滥调** — "You are my everything" → "You are my last breath before the ocean swallows me"
- 🔄 **节奏不匀** — 避免某行特别长或特别短
- 🔄 **文风不统一** — 如果混了古文和现代汉语
- 🔄 **歌词与音乐不搭** — 快歌用短句，慢歌用长句

#### 验证三步法
1. **朗读检查** — 大声读出歌词，检查"可唱性"
2. **韵脚检查** — 确保相邻行或对应行有合理的韵脚
3. **意象检查** — 确保每句都有清晰的视觉或情感意象

---

### 七、从 v4.5_all 升级到 v5.5 的歌词调整指南

如果你之前用 v4.5 写歌词，升级到 v5.5 时需要做以下调整：

#### ✅ 升级后应该充分利用的新能力

| v4.5 做法 | v5.5 改进做法 | 效果 |
|---|---|---|
| 简单的标签 `[Verse]` | 加上括号标注 `(whisper)` `(powerful)` | 更精准的表演风格 |
| 全小写歌词 | 用大写字母强调关键词 | 音量/音高更有对比 |
| 标准标点 | 多用感叹号、省略号、问号 | 能量、延音、疑问感更明显 |
| 需要重新生成整首 | 用 Replace Section 精调单个段落 | 节省 Credits，更快迭代 |
| 自己找灵感写歌词 | 用 ReMi 快速生成初稿 | 输入更清晰的 Prompt，节省时间 |

#### ❌ v4.5 的"万能法"在 v5.5 可能不适用

**v4.5 用法：** 通用标签 + 一般化描述
```
[Verse]
I love you so much
You are my everything

[Chorus]
Take me back to you
```
→ v4.5 能生成一个可用的歌曲

**v5.5 的挑剔：** 相同的输入可能因为**歌词的细节特性**而改变音乐
- 如果你不用大写强调，v5.5 可能生成的音乐比较"平"
- 括号标注被忽视，可能丧失表现力
- 标点不明确，节奏感受影响

**建议：** 升级到 v5.5 后，花时间学会用**括号、大小写、标点**这些工具

#### 💡 迁移最佳实践

**第一步：使用 ReMi 重新生成歌词**
```
用 ReMi 生成一个初稿（利用 v5.5 的新模型）
对比原歌词，挑选更喜欢的版本或混合两个
```

**第二步：精化标签和标注**
```
如果是感情段落 → 加 (soft) / (emotional)
如果是高潮段 → 加大写 + 感叹号
如果是过渡 → 加 [Pre-Chorus] 标签
```

**第三步：充分利用编辑工具**
```
第一稿不满意 → 用 Replace Section 改某个段落
觉得太短 → 用 Extend 加新部分
不满意的开头/结尾 → 用 Crop 移除
```

---

### 八、v4.5 vs v5.5 实际对比例子

#### 同一个歌词，两个版本的不同表现

**原歌词（简单写法）：**
```
[Verse]
Looking at the stars
Thinking of you here
Missing your embrace
Wishing you were near

[Chorus]
Come back to me
I need you so
Come back to me
Don't let go
```

**v4.5 生成结果：**
- 旋律相对"平静"、"标准化"
- 节奏均匀，缺少起伏
- 音乐和歌词的情感匹配度一般
- 所有 Credits 消耗，无法局部编辑

**v5.5 使用优化写法：**
```
[Verse]
Looking at the stars... (breathy)
THINKING OF YOU!
Missing your embrace (soft, emotional)
WISHING YOU WERE HERE! (powerful)

[Chorus]
COME BACK TO ME!
I NEED YOU SO!
Come back... (fade)
Don't let go...
```

**v5.5 生成结果：**
- 括号标注影响音质和表现力
- 大写字母创造**峰值**（高能的 "COME BACK TO ME"）
- 省略号产生拉长音效果
- Call-and-response 的对比更明显
- 可以局部编辑，而不是全部重做

**成本对比：**
- v4.5: 1 次 Credits 消耗（全部重生）
- v5.5: 也许 0.5 次 Credits（用 Replace Section 改某个段落）

---

### 九、实战案例：同样歌词，不同写法的效果对比

#### 案例 1：如何让一个 Ballad 变成 Anthem

**原始歌词（柔和版）：**
```
[Verse]
I'm looking at the stars tonight
Wondering if you're thinking of me
The silence feels so cold and long
But your memory keeps me strong

[Chorus]
You live inside my heart
Even when we're far apart
Distance cannot break this bond
You're everything I long
```

**改成 Anthem（强势版）的改法：**
```
[Verse]
NOW I'M LOOKING AT THE STARS!
WONDERING IF YOU HEAR ME!
THE SILENCE SCREAMS SO LOUD!
YOUR MEMORY BURNS INSIDE!

[Chorus]
YOU LIVE IN MY HEART!
WE'RE NEVER FAR APART!
NOTHING BREAKS THIS BOND!
YOU'RE EVERYTHING I FOUGHT!
```

**v5.5 的反应：**
- 大写字母 → 更高的音量、更强的音高
- 感叹号 `!` → 每句都加能量爆发
- 短句简洁 → 音符更清晰、更有力
- 结果：从慢速情歌变成"高燃"摇滚

#### 案例 2：用歌词长度控制节奏感

**短句版（适合快歌、说唱）：**
```
[Verse]
Lost it all
Can't hold on
Breaking down
Moving on
Pain so real
Time will heal
Can't look back
Only forward
```
**AI 生成的感觉：** 快速、断裂、说唱型、高能

**长句版（适合抒情、民谣）：**
```
[Verse]
I've lost everything that mattered to me in this world
But I'm learning how to let go and find peace within myself
Time is a river that carries away the pain
And slowly I'm beginning to feel alive again
```
**AI 生成的感觉：** 缓慢、流畅、诗意、温暖

**同样的 BPM 标记，听觉效果完全不同！**

#### 案例 3：如何制造"洗脑感"（中国风格常见）

**重复咒语法：**
```
[Chorus]
Love love love you baby
Can't can't can't without you
Feel feel feel this energy
Love love love eternally
```

**v5.5 的特殊处理：**
- 连续的 `love love love` → AI 识别为"模式"，会在伴奏中也制造某种重复
- 会生成易记的 Hook（钩子），适合传播

---

### 十、v5.5 陷阱与优化

#### ❌ 常见错误与解决方案

| 错误 | 表现 | 解决办法 |
|---|---|---|
| 副歌太长（超过 12 行） | 拖沓、容易被遗忘 | 截短到 4-8 行，提高重复度 |
| 所有段落长度一样 | 单调、缺乏对比 | Verse 长，Chorus 短，Bridge 改风格 |
| 歌词全是抽象概念 | AI 没有参考，生成含糊 | 加入具体意象："tears" 而非 "sadness" |
| 混用中英文不当 | 音律不搭，生成错位 | 单独用中文或单独用英文区块 |
| 忽视标点 | 感情表达不清 | 多用感叹号、问号、省略号来指导 |

#### ✅ 优化技巧

**技巧 1：预留 Rap Section**
```
[Verse - 混合型]
I'm breaking free tonight (sung)
Rap rap flow so tight (rap)
Can't hold back the feeling (sung)
This beat is so real (rap)
```

**技巧 2：在 Chorus 前加 Pre-Chorus（v5.5 友好）**
```
[Pre-Chorus]
Ready now
Here we go
Build it up

[Chorus]
EXPLOSION OF LOVE!
```

**技巧 3：Outro 制造循环感**
```
[Outro]
Love love love (fade)
You and me (fade)
Love love love... (whisper)
```

---

### 十一、与 Voices 和 Custom Models 结合的歌词策略【v5.5 Pro/Premier 专属】

#### 当使用 Voices 时
你的声音特质会影响歌词的最佳选择：
- **清晰、高音的 Voice** → 适合空灵、诗意的长歌词
- **沙哑、深沉的 Voice** → 适合短歌词、说唱型
- **温暖、中庸的 Voice** → 最通用，任何歌词都能驾驭

#### 当使用 Custom Models 时
AI 已经学会了你的风格，歌词可以大胆创新：
- 尝试**完全不同的题材**（之前从没写过）
- 歌词可以**更简洁或更长**，Custom Model 会自动适应你的节奏感
- 可以尝试**特殊的标记和要求**（`(rap)`, `(whisper)` 等），AI 会结合你的风格来执行

### 如何用本知识库 + Suno 创作

```
用户需求
  ↓
查阅 genres/[风格]/README.md
  ↓ 获取：基础参数（BPM、调式、乐器）
  ↓
查阅 moods/[情绪].md
  ↓ 获取：情绪修饰词汇
  ↓
查阅 templates/style_prompts/[风格].md
  ↓ 获取：英文 Style Prompt 模版
  ↓
查阅 templates/lyrics/[模版].md
  ↓ 获取：歌词结构参考
  ↓
组合信息 → 进入 Suno Custom Mode
  ├─ Style Prompt → 粘贴到"Description"
  ├─ 歌词 → 用 ReMi 生成或自写
  └─ 参数 → 填入 BPM、地区等
  ↓
Create → 生成初稿
  ↓
用 Replace Section / Extend 精调整
  ↓
完成！
```

---

## 🔗 Suno 官方资源链接

- **主站**：https://suno.com
- **帮助中心**：https://help.suno.com
- **ReMi 歌词模型说明**：https://help.suno.com/en/articles/3599681
- **Custom Mode 指南**：https://help.suno.com/en/articles/2415873
- **Replace Section 功能**：https://help.suno.com/en/articles/3271873
- **Extend 功能**：https://help.suno.com/en/articles/2409601
- **Voices 功能**：https://help.suno.com/en/articles/11362369

---

## ❓ 常见问题

### Q: ReMi vs Classic 歌词模型应该选哪个？

**A:**
- **ReMi** — 更有创意、更"个性化"，适合想要惊喜或独特表达的情况
- **Classic** — 更稳妥、更可控，适合明确需求的创作

**建议做法：** 两个都试试，对比效果。

### Q: Replace Section 会改变原音乐吗？

**A:** 会的。Replace Section 会在替换位置重新生成音乐，确保歌词和旋律吻合。有时音乐会略有变化（在保持整体风格的前提下）。这是 Suno 确保音乐-歌词完美匹配的必要过程。

### Q: Voices 功能需要录多长的参考音频？

**A:**  
- 建议 10-30 秒清晰的演唱或说话录音
- 质量越高越好（避免噪音、混响过多）
- Suno 会进行人声验证（要求你唱一句指定的短语以确认身份）

### Q: Custom Models 能用多长的音乐训练？

**A:**  
- 每个模型建议用 3-5 首完整歌曲
- 总时长 5-15 分钟为佳
- 包括节奏、编排、乐器特点相似的作品效果最好

### Q: 生成的歌曲著作权属于谁？

**A:** 
- **Pro / Premier 用户** — 你拥有完整的著作权和商业使用权
- **Free 用户** — 仅个人使用，无商业权
- **自己输入的歌词** — 无论订阅级别，歌词的所有权归你所有

---

## 📚 推荐进阶阅读

- [理论基础：如何用和弦启发歌词](../../theory/chord_progressions.md)
- [歌词模版库](../../templates/lyrics/INDEX.md)
- [情绪修饰词汇](../../moods/INDEX.md)
- [各风格的专业 StylePrompt](../../templates/style_prompts/INDEX.md)

---

**最后更新**：2026年4月12日  
**基于 Suno 官网信息**：v5.5（2026年3月发布）

