# novel-skills 深研报告

> 仓库：leemain88/novel-skills（英文 AI 小说写作技能库，MIT 协议）
> 研究日期：2026-10-08 ｜ 研究方式：clone 后精读 15 个技能 + 4 个工作流全部原文
> 目标读者：为《The Luna Who Said No》（英文狼人言情、日更 2000 词）挑选可用方法

---

## 一、项目概览

这不是一个"一键生成小说"的工具，而是一套**给 AI 写作 agent 用的专家角色库**。核心理念："One skill = one specialised capability"——不搞 50 个微规则（"删副词""show don't tell"全塞一起只会让 AI 写出 sterile prose），而是 15 个专家角色，每个负责一种思维模式。

15 个技能分 4 组：

| 阶段 | 技能 | 作用一句话 |
|---|---|---|
| 创作 | story-architect | 大纲架构 |
| 创作 | world-canon-manager | 世界观/设定锁死 |
| 创作 | character-designer | 人物心理档案 |
| 创作 | voice-style-analyser | 文风量化档案 |
| 写作 | scene-architect | 单场景蓝图 |
| 写作 | fiction-writer | 初稿引擎 |
| 编辑 | developmental-editor | 宏观结构诊断 |
| 编辑 | prose-editor | 逐行润色 |
| 编辑 | dialogue-editor | 对话 subtext |
| 编辑 | narrative-humanizer | 去 AI 味 |
| 编辑 | continuity-reviewer | 一致性审计 |
| 读者 | beta-reader | 模拟读者 |
| 读者 | manuscript-evaluator | 10 分制打分卡 |
| 出版 | publishing-assistant | 查询信/梗概/书名 |
| 出版 | publishing-formatter | PDF/EPUB 排版 |

（另有第 16 个 ns-novel-orchestrator，是总调度员，不在本次 15 个范围内。）

---

## 二、15 个技能核心技术点

### 创作组

**1. ns-story-architect（故事架构师）**
倒推法埋伏笔：先定反转点，再往前倒排至少 2 处 subtle setup + 红鲱鱼；每幕必须有一个改变主角方向/认知的转折点。质量门：每章细纲写清"入场状态→核心节拍→出场钩子"。

**2. ns-world-canon-manager（世界观锁死）**
所有魔法/科技/社会规则必须写明代价、限制、失效条件，建成可查询的 canon_index.json；写稿时任何新情节先过"规则冲突检查"。防的是"中途改规则救主角"（soft lore）。

**3. ns-character-designer（人物设计师）**
每个人物四件套：Wound（创伤/幽灵）→ Lie（信奉的谎言）→ Want（外部目标）→ Need（内部需求，且必须与 Want 冲突）。弧光 = 情节压力如何逼人物在三幕中直面自己的 Lie。反派必须有自洽的内在逻辑，不许脸谱化。

**4. ns-voice-style-analyser（文风分析仪）**
把文风变成可量化的 voice_profile.yaml：平均句长、从句复杂度、隐喻频率、幽默/黑暗/抒情/正式度/亲密感五维 tone 刻度、POV 心理距离（紧贴 vs 抽离）。每个人物 ≥3 个语言标记（句式偏好、禁用词、感官偏好）。

### 写作组

**5. ns-scene-architect（场景架构师）**
每场景一张 scene_card：Goal（人物进场目标）→ Conflict（主动对抗，非被动拖延）→ Turning Point（精确到哪一刻被迫变招）→ Emotional Value Turn（量化，如 Hopeful +2 → Devastated -3）→ Outcome（目标达成+并发症 / 失败+灾难）。铁律：入场状态必须 ≠ 出场状态，否则这场戏不许写。

**6. ns-fiction-writer（初稿引擎）**
初稿只管往前冲，不许中途改句子；按 scene_card 的节拍顺序写，强制执行 voice_profile 的句长变化和词汇表。质量门：转折点不许漏写，POV 心理距离不许漂移。

### 编辑组

**7. ns-developmental-editor（结构编辑）**
只做宏观：act 长度比、张力曲线（逐章画 tension map 找拖沓点）、人物信念位移追踪、找 plot hole。铁律：结构没验证通过之前，不许碰逐行修改；每个问题必须给根因分析 + ≥2 个可行解。

**8. ns-prose-editor（文字编辑）**
四步：① 删 filter words（she saw / he felt / it seemed，目标降低 80%）；② 情绪标签转生理+感官（he was furious → 身体反应）；③ 句长 3–8 词短句与 15–25 词长句交替，破单调节奏；④ 弱动词+副词换强动词（walked slowly → trudged）。

**9. ns-dialogue-editor（对话编辑）**
见第四节深挖。

**10. ns-narrative-humanizer（去 AI 味）**
见第四节深挖。

**11. ns-continuity-reviewer（一致性审计）**
每场景提取"谁在场、带什么、身体状态、几点钟"，三查：空间逻辑（进出房间、武器在哪只手）、时间线对齐（行程时长、天气）、伤势/物品审计（上一章伤的左臂，10 分钟后不许抡大剑）。输出按 Critical/Moderate/Minor 分级的审计报告。

### 读者组

**12. ns-beta-reader（模拟读者）**
见第四节深挖。

**13. ns-manuscript-evaluator（终审打分）**
6 大支柱各 1–10 分：Story Structure、Character Depth、Pacing Dynamics、Emotional Impact、Voice Distinction、Originality，每项 2 段论证 + 文本证据，最后给 A+ 到 F 的出版就绪等级。铁律：打分必须对标同类型已出版作品，不许 9/10 通胀。

### 出版组

**14. ns-publishing-assistant（出版助理）**
一句话 hook 公式（主角+困境+赌注）→ query letter（250–350 词上限）→ 500–800 词全透梗概（必须写结局，不许 teaser）→ 书封文案 → 10–15 个书名。comp titles 必须是近 3–5 年同类型作品，不许拿 Harry Potter 凑数。

**15. ns-publishing-formatter（排版）**
Pandoc/WeasyPrint 出印刷 PDF + EPUB3：orphans/widows 控制、章节首页不许首行缩进、页眉页脚章节首页隐藏、EPUB 必须过 epubcheck 零错误。对我们当前连载阶段暂无用。

---

## 三、4 个工作流完整步骤链

### Workflow 1: create-novel（立项 → 世界观锁定）

```
1. ns-novel-orchestrator      初始化项目状态，确认 premise 目标
2. ns-story-architect         premise → 三幕/四幕结构 → 主题线 → 反转+伏笔矩阵
3. ns-world-canon-manager     世界观圣经：地理、派系、规则、时间线、canon 索引
4. ns-character-designer      人物档案：Wound/Lie/Want/Need、弧光、关系矩阵
5. ns-voice-style-analyser    文风档案：voice_profile.yaml + 人物语言表
6. ns-story-architect（回炉） 生成带入场/出场状态的逐章路线图
```

交付：project_charter.md / master_outline.md / world_bible.md / character_dossiers.md / voice_profile.yaml

### Workflow 2: write-chapter（单章写作）

```
1. ns-novel-orchestrator      核对本章目标 vs 总纲
2. ns-scene-architect         scene_card：Goal → Conflict → Turning Point → Emotional Turn → Outcome
3. ns-fiction-writer          按 scene_card + voice_profile 写初稿（只管冲，不改句）
4. ns-world-canon-manager     初稿过 lore/地理/canon 一致性审计
```

交付：scene_card.md / draft_chapter.md

### Workflow 3: revise-chapter（四遍修订）★ 核心

```
1. ns-narrative-humanizer     审计并剥离 AI 痕迹、公式化句式、机械过渡
2. ns-dialogue-editor         subtext、人物声音区分度、潜台词、未说出口的张力
3. ns-prose-editor            逐行：show don't tell、感官叠加、句长节奏
4. ns-continuity-reviewer     物理移动、物品、伤势、时间线审计
```

交付：humanized_prose.md / edited_prose.md / continuity_audit_report.md
质量门：AI 指纹词零残留 / 对话标签以 said+动作节拍为主 / filter words 降低 80% / 物理矛盾零未处理

### Workflow 4: final-edit（终审 → 出版包）

```
1. ns-developmental-editor    全书结构、act 平衡、人物弧光、节奏诊断
2. ns-beta-reader             模拟多类读者：找困惑点、无聊点、高光点
3. ns-manuscript-evaluator    6 支柱 10 分制打分卡 + A+~F 就绪等级
4. ns-publishing-assistant    query letter + 全透梗概 + 书封文案 + 书名
5. ns-publishing-formatter    印刷 PDF + EPUB3 排版
```

交付：developmental_report.md / beta_reader_simulation_report.md / manuscript_evaluation_report.md / submission_package.md / PDF+EPUB

---

## 四、专项深挖

### 4.1 ns-narrative-humanizer：AI 痕迹词库（仓库原文完整列表）

仓库中明确列出的词分两类，**这就是它的全部词库**（已全文 grep 确认，无隐藏扩展表）：

**A. Signature AI vocabulary（6 个，指纹词，零容忍）：**
testament、tapestry、beacon、delve、pivotal、nestled

**B. Clinical transitions（4 个，机械过渡词）：**
Moreover、Furthermore、In conclusion、Crucially

**C. 结构级痕迹（非词汇，是模式）：**
- 对称句式配对（symmetrical sentence pairings）
- 整齐段落收尾：Topic sentence → 2 个支撑句 → 道德总结句（tidy paragraph resolutions）
- 情感疏离：抽象情绪总结代替身体感知

**五步工作法：**
1. AI Pattern Audit——扫指纹词、对称句式、整齐收尾
2. Transition De-Mechanization——机械过渡换成有机叙事流
3. Asymmetry & Imperfection Injection——段落长度剧烈变化；突然的观察、碎片句、自然的思维跑偏
4. Emotional Grounding——抽象情绪总结换成内脏级身体感知 + 落地的物理互动
5. Humanity Verification——终极拷问：*"Does this sound like an actual person wrote it from lived experience?"*（听起来像真人亲身经历写出来的吗？）

**三个明示的失败模式（反面教材）：**
- Superficial Synonym Swapping：只换同义词不改句式节奏（治标不治本）
- Over-Correction to Slang：硬塞俚语，和设定/文风打架
- Loss of Coherence：为碎而碎，牺牲清晰度

**诚实评估**：它的词库很短（10 个词），真正值钱的是第 3 步的不对称注入和第 5 步的人性拷问。对我们而言，词库需要按言情题材扩展（见第六节建议）。

### 4.2 ns-dialogue-editor：对话 subtext 技巧

**五步工作法：**
1. **Exposition Scrub**——删 "As you know, Bob" 式对话：两个角色都知道的事，不许借对话讲给读者听
2. **Subtext Layering**——重写台词，让角色绕着真实情感需求说话、藏秘密
3. **Voice Differentiation**——每人用符合其背景/心态的句式、句长、词汇
4. **Dialogue Tag Streamlining**——"she said angrily" 式副词标签 → 换成落地的物理动作节拍
5. **Rhythm & Interruption Tuning**——加自然停顿、话没说完、抢话打断

**输出物**：polished_dialogue.md + **Subtext 分析矩阵**（Spoken Line vs. Unspoken Intent，每句台词对照"说了什么 / 没说什么"）

**盲读测试（质量门）**：把说话人名字遮掉，只凭声音还分得清谁在说话，分不清就不合格。

**三个失败模式**：On-the-Nose（把最深感受直说出来，毫无犹豫）、Talking Heads（真空对话，无环境互动无动作节拍）、Over-Written Dialect（硬拼口音，拖慢阅读）。

### 4.3 ns-voice-style-analyser：voice profile 包含哪些维度

输出 `voice_profile.yaml`，仓库定义的维度：

| 维度 | 内容 |
|---|---|
| 句长指标 | 平均句长、句长变化方差、从句复杂度目标 |
| 词汇表 | 词汇密度、隐喻频率上限、禁用词表 |
| Tone 五维刻度 | 幽默 / 黑暗 / 抒情 / 正式度 / 情感亲密感，各自校准 |
| POV 心理距离 | 紧贴（tight psychic distance）vs 抽离俯瞰，选定后全书锁定 |
| 标点习惯 | 破折号/分号/碎片句的使用频率 |
| 感官偏好 | 主导感官通道（视觉/嗅觉/听觉…） |
| 人物语言表 | 每人 ≥3 个语言标记：句式偏好、禁用词、感官偏好 |

质量门：profile 里必须有明确的句长变化目标和 tone 控制参数；否则就是"通用 AI 默认腔"（Generic Voice 失败模式）。

### 4.4 ns-beta-reader：模拟哪几类读者

仓库原文定义 4 类 persona（workflow 里要求挂 3–4 个）：

1. **Casual Reader（快餐读者）**——跳读，只追爽点，节奏一慢就弃
2. **Hardcore Genre Fan（类型死忠）**——狼人言情老读者，专盯题材套路有没有玩出新意、设定有没有崩
3. **Literary Critic（挑剔评论家）**——盯逻辑漏洞、人物 OOC、陈词滥调
4. **Emotional/Character Reader（情感读者）**——为人物关系而来，盯感情线张力、人物选择是否可信

输出按 persona 分组：Confusion（哪里看不懂）、Boredom（哪里无聊）、Favorite Moments（高光）、Weak Sections（疲软段），必须带章节和行号。

铁律：必须同时报负面摩擦点和正面高光点；不许四个 persona 众口一词（Homogenized Feedback 失败模式）；必须用读者体验语言，不许用编辑黑话。

---

## 五、判断：对"英文狼人言情、日更 2000 词、去 AI 味"最有用的 5 个

### Top 1: ns-narrative-humanizer（去 AI 味）
**为什么**：这是用户原话"不能太AI"的直接解法。它的五步法里，第 3 步不对称注入（段落长短剧烈变化、碎片句）和第 5 步人性拷问是当前流程里完全没有的。ChatGPT 评审是抽查，它是每章必走的一道关。注意它的词库只有 10 个词，需要按言情扩展（三件套里已部分做了）。

### Top 2: ns-dialogue-editor（对话 subtext）
**为什么**：言情是对话驱动的题材，Elara 的嘴毒、Kael 的惜字、Selene 的笑里藏刀全靠对话立住。它的 Subtext 矩阵（说了什么 vs 没说什么）和盲读测试是立即可用的检查工具。"As you know, Bob" 式 exposition 正是 AI 言情最常见的毛病。

### Top 3: ns-scene-architect（场景蓝图）
**为什么**：日更 2000 词最怕写水文。它的铁律"入场状态必须 ≠ 出场状态" + Emotional Value Turn 量化（+2 → -3），是每章动笔前 5 分钟就能用的防灌水检查。比写完再审便宜得多。

### Top 4: ns-continuity-reviewer（一致性审计）
**为什么**：70 章连载，伤势/物品/时间线/30 天倒计时是最容易崩的地方。它的"每场景提取四要素（谁在场、带什么、身体状态、几点钟）"是可机械执行的检查清单，适合做成每章发布前的固定动作。

### Top 5: ns-voice-style-analyser（文风档案）
**为什么**：它是 Top 1–4 的地基。没有 voice_profile.yaml，humanizer 和 dialogue-editor 就没有"对的"标准可对齐。一次投入长期受益：三个人物的语言标记定死后，OOC 和声音同质化问题从源头减少。

### 落选说明
- story-architect / character-designer / world-canon-manager：大纲阶段已过，书已在连载，边际收益低（但人物 Wound→Lie→Want→Need 四件套值得回填进台账）。
- fiction-writer：初稿引擎理念（只管冲不改句）可吸收，但我们是直接写英文，不需要它的生成流程。
- developmental-editor / manuscript-evaluator：全书级工具，70 章完本前用不上。
- beta-reader：有用但排第 6，可作为发布前的抽查，不必每章走。
- publishing-assistant / publishing-formatter：传统出版流程，与 GoodNovel/Dreame 连载无关，暂无用。

---

## 六、给现有三件套的升级建议（可选）

1. **anti-ai-checklist.md**：把 humanizer 的 10 词词库并入，并按言情扩展（breath caught / jaw clenched / eyes widened 三件套已在三件套里，humanizer 的 tapestry/delve 类补上）；加上它的三个失败模式作为自查。
2. **chapter-review.md**：已经是 revise-chapter 的四遍结构，可直接对标它的质量门（filter words -80%、盲读测试）。
3. **consistency-ledger.md**：借鉴 canon_index.json 思想，把"世界规则"改成结构化条目（规则/代价/失效条件），方便 continuity-reviewer 式审计。
4. 新增 scene_card 模板（5 分钟版）：Goal / Conflict / Turning Point / Emotional Turn（量化）/ Outcome，放在写章之前。

---
*报告完。仓库 clone 在 /tmp/novel-skills（ephemeral，VM 重启丢失；如需长期保留建议移到 ~/workspace）。*
