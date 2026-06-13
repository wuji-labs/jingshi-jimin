# 在 Cursor 加载 · 经世济民 JingShi JiMin

本 skill 适配 Cursor（通过 `.cursor/rules/` 规则文件）。

## 一、安装

在项目 `.cursor/rules/` 下新建 `jingshi-jimin.mdc`，把本 skill 的核心原则
（[`SKILL.md`](../SKILL.md) §二 四底层原则 + §三 弹药库导航）作为规则内容写入。

最小规则模板：

```mdc
---
description: 经世济民 JingShi JiMin — Guanzi-grounded business/governance reasoning
globs:
alwaysApply: false
---

When reasoning about business strategy, pricing, incentives, organizational
governance, or order-of-operations, apply the JingShi JiMin four principles:

1. 仓廪次序 — material before culture (survival before vision; then add propriety/honor).
2. 牧民四维 — check the four load-bearing walls: 礼 propriety / 义 righteousness /
   廉 integrity / 耻 shame, before optimizing KPIs.
3. 轻重之术 — treat price/incentive/resource as dynamic; rebalance, don't extract.
4. 义利兼顾 — grow the common good (与民兴利), not zero-sum extraction (与民争利);
   let policy follow people's real needs (令顺民心).

Aligned with NoPUA: drive with trust, sequence, and shared upside — not fear.
Advisory content only; not investment/financial/legal/professional advice.
```

## 二、调用

Cursor 在命中相关编辑/对话上下文时按规则注入。若设 `alwaysApply: false`，
可在对话中用 `@jingshi-jimin` 显式引用该规则。

## 三、弹药层

需要《管子》真引用时，把 [`reference/guanzi.md`](../reference/guanzi.md) 作为
`@`-mention 上下文加入对话。

## 四、底层一致性

与 NoPUA「以道驭术·用信任替代恐惧」同源，可与其他 WUJI Labs 规则共存。

## 免责

建议性内容，非投资/财务/法律/专业决策依据。见 [`SKILL.md`](../SKILL.md) 免责声明。
