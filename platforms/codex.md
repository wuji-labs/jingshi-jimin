# 在 Codex 加载 · 经世济民 JingShi JiMin

本 skill 适配 OpenAI Codex（CLI / app-server）。

## 一、安装

把本 skill 目录复制到 Codex 的 skills 目录：

```bash
cp -r labs/skills/jingshi-jimin ~/.codex/skills/
```

或在 monorepo 内直接引用（无构建步骤；`scripts.build` 为 `echo no build`）。

## 二、调用

Codex 无统一 skill frontmatter 协议时，可把 [`SKILL.md`](../SKILL.md) 作为系统提示/上下文
注入，或在 prompt 中显式引用本 skill 路径，让模型在以下场景先读 SKILL.md：

- 经营格局判断（义利兼顾）
- 定价 / 激励 / 资源调配（轻重之术）
- 组织治理底座设计（牧民四维）
- "先生存还是先谈格局"的次序判断（仓廪次序）
- 商业方案的"争利 vs 兴利"体检

注入示例（system / developer 段）：

```
You have access to the JingShi JiMin (经世济民) skill at labs/skills/jingshi-jimin/SKILL.md.
When reasoning about business strategy, pricing, incentives, governance, or
order-of-operations, consult its four principles and the Guanzi ammunition library first.
```

## 三、弹药层

- [`reference/guanzi.md`](../reference/guanzi.md) — 《管子》四支柱 + 注明书·篇的真引用，供检索/引用时加载。

## 四、底层一致性

与 NoPUA「以道驭术·用信任替代恐惧」同源；可与其他 WUJI Labs skill 并行使用，不冲突。

## 免责

建议性内容，非投资/财务/法律/专业决策依据。见 [`SKILL.md`](../SKILL.md) 免责声明。
