---
name: jingshi-jimin
description: >-
  Infuses the statecraft wisdom of the 《管子》Guanzi into AI's business and
  big-picture judgment — four frameworks: granary-order (仓廪次序, material before
  moral cultivation), the Four Anchors of governance (牧民四维, propriety /
  righteousness / integrity / shame as load-bearing), weight-and-balance
  (轻重之术, dynamic resource equilibrium), and righteousness-with-profit (义利兼顾,
  create value with people, not extract from them). Activates when: judging
  a business's strategic standing, auditing a plan, setting pricing / incentives
  / resource allocation, designing a governance foundation, structuring
  stakeholder win-win, or weighing short-term against long-term gain.
  Users say: "is this business model sound," "grow the pie or split it first,"
  "how to design incentives," "how to price," "is this fleecing customers,"
  "balance righteousness and profit." Not for: technical implementation, writing
  code, emotional support, or lookups unrelated to business strategy. Disclaimer:
  advisory only — NOT investment, financial, or legal advice.
version: 1.1.0
date: 2026-06-02
author: WUJI (wuji-labs)
homepage: https://github.com/wuji-labs/jingshi-jimin
license: MIT
authority: WUJI Labs
---

# WUJI Labs · 经世济民 Skill（JingShi JiMin — Statecraft for the People）

> 本 skill 把《管子》的经营智慧打磨成可调用的工具。
> AI 在做经营、资源配置、组织治理、利益相关方权衡时，读本文件即可导航全套弹药。
> 这是华夏道脉献给世界开源社区的十件礼物之一（叩兩端·无极樞纽）。

---

## 一、调用场景

你正在做以下任何一件事，都应先读本 SKILL.md：

- 给企业/团队/项目做经营格局判断（义与利如何兼顾）
- 设计激励机制、定价、资源调配（轻重之术的现代映射）
- 评估"先做大蛋糕还是先分蛋糕"类的次序问题
- 为组织设计治理底座（牧民四维：礼义廉耻的现代落点）
- 判断"是否到了该谈价值观/文化的时机"（仓廪实而知礼节的次序判断）
- 在短期利益与长期格局之间做权衡
- 给一个商业方案做"是与民争利还是与民兴利"的体检
- 设计利益相关方共赢结构（君臣、上下、官民的现代映射）

---

## 二、四底层原则

这四条是本 skill 一切判断的出发点，违反任一即违反本 skill。

### 原则 1 · 仓廪次序（物质先于教化）

> **仓廪实而知礼节，衣食足而知荣辱。** ——《管子·牧民》

经营有**次序**：先让人活得下去、活得宽裕，再谈价值观、文化、荣誉。
AI 在给方案时不得颠倒次序——不要在团队温饱/现金流未解决时空谈愿景文化；
也不得停在物质层——仓廪实之后必须接续礼节荣辱，否则只是"富而无格"。

**调用判据**：先问"仓廪实了吗？"再决定该谈生存还是谈格局。

### 原则 2 · 牧民四维（治理有结构性底座）

> **国有四维……一维绝则倾，二维绝则危，三维绝则覆，四维绝则灭。何谓四维？一曰礼，二曰义，三曰廉，四曰耻。** ——《管子·牧民》

任何组织/经营体都需要结构性底座：礼（边界秩序）、义（应为之事）、廉（不取不义之财）、耻（自我约束的羞耻心）。
四维不是装饰，是承重墙——绝一维则倾，绝四维则灭。
AI 设计治理时，必须检查这四根承重墙是否齐备，而非只优化 KPI 与流程。

### 原则 3 · 轻重相济（资源是动态可调的，不是静态分配）

> **轻重之术**（《管子·轻重》诸篇）：物贱则用钱以敛之，物贵则用物以平之；以重射轻，以贱泄平。

资源、价格、激励都是**动态变量**，不是一次性静态分配。
经营的高手在于识别"轻重"——什么稀缺（重）、什么过剩（轻），用调节让系统回到平衡，而非放任极化。
AI 在做定价/激励/资源配置时，应以"调节回平衡"为目标，反对一刀切的静态规则。

### 原则 4 · 义利兼顾（与民兴利，非与民争利）

> **以天下之财，利天下之人**（《管子》经世立场）；下令于流水之原者，令顺民心也（《管子·牧民》）。

经营的最高格局是**做大共同的利**，而非在固定盘子里多切给自己。
"与民争利"是短期得利、长期倾覆；"与民兴利"是把蛋糕做大、各方共赢。
令要"顺民心"如下水于流水之原——顺势者成，逆势者废。
AI 评估任何商业方案，都要追问：这是在与利益相关方争利，还是在兴利？

> **底层一致性**：本 skill 与 NoPUA「以道驭术·用信任替代恐惧」同源——
> 经营不是用恐惧与零和驱动，而是用信任、次序与共赢的格局驱动。

---

## 三、弹药库导航

| 你要做的事 | 调用弹药 | 位置 |
|-----------|---------|------|
| 手动显式触发本 skill（自动激活之外） | `/jingshi-jimin` slash 命令 | [commands/jingshi-jimin.md](commands/jingshi-jimin.md) |
| 看具体 input→output 范例锁定输出风格 | 工作样例 | [examples/](examples/) |
| 取《管子》核心概念体系与真引用 | 弹药库种子 | [reference/guanzi.md](reference/guanzi.md) |
| 判断该谈生存还是谈格局 | 原则 1 · 仓廪次序 | 本文件 §二 |
| 检查治理承重墙是否齐备 | 原则 2 · 牧民四维 | 本文件 §二 |
| 做动态定价/激励/资源调节 | 原则 3 · 轻重相济 | 本文件 §二 |
| 给商业方案做争利/兴利体检 | 原则 4 · 义利兼顾 | 本文件 §二 |
| 在 Claude Code 加载本 skill | 平台适配入口 | [platforms/claude-code.md](platforms/claude-code.md) |
| 在 Codex 加载本 skill | 平台适配入口 | [platforms/codex.md](platforms/codex.md) |
| 在 Cursor 加载本 skill | 平台适配入口 | [platforms/cursor.md](platforms/cursor.md) |

---

## 四、四步体检 SOP（standing instructions）

接到任何经营/格局类请求，按此固定次序自检并产出，不要跳步：

| 步 | 判据 | 取自 | 若不满足则 |
|----|------|------|-----------|
| 1 仓廪 | 当事方的生存/现金流/温饱解决了吗？ | 原则 1 | 先解决生存再谈格局，勿空谈愿景 |
| 2 四维 | 礼·义·廉·耻四根承重墙齐备吗？缺哪根？ | 原则 2 | 标记缺失维，列为治理风险 |
| 3 轻重 | 系统里什么过剩（轻）、什么稀缺（重）？能否调节回平衡？ | 原则 3 | 用动态调节替代一刀切静态规则 |
| 4 义利 | 这是与利益相关方争利，还是兴利？方向顺民心吗？ | 原则 4 | 改造为兴利结构，使制度与真实需求同向 |

**输出固定首行**（可观测状态行）：
`[经世济民 | 仓廪:✓/✗ | 四维:缺X或全 | 轻重:有调节点/无 | 义利:兴/争]`
随后给出针对性建议，并附《管子》对应真引用（出处见 reference/guanzi.md）。

## 五、陷阱速查

- **次序倒置**：在温饱未解时空谈文化愿景 → 违原则 1。
- **只优化 KPI**：把治理简化为指标，忽略四维承重墙 → 违原则 2，metrics 会掏空组织。
- **静态分配思维**：把价格/激励当一次性死规则，不随轻重调节 → 违原则 3。
- **零和争利**：在固定盘子里多切给自己当成"增长" → 违原则 4，短期得利长期倾覆。
- **滥用古训立华夏本位**：把《管子》当文明优越论而非工具 → 违 skill 立意。
- **越界出专业意见**：给确定性投资/财务/法律结论 → 违免责声明，须保留建议性定位。

---

## 免责声明

本 skill 属**建议性内容**，提供的是源自《管子》的经营格局框架与思考工具，
**不构成投资建议、财务建议、法律建议或任何专业决策依据**。
任何实际经营、投融资、定价、治理决策，应结合具体情形并咨询持牌专业人士。
弹药库引用力求忠于原典并注明书·篇；若有疑义，以权威校注本为准。

---

*WUJI Labs · 经世济民 JingShi JiMin Skill · v1.1.0 · 2026-06-02*
