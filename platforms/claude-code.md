# 在 Claude Code 加载 · 经世济民 JingShi JiMin

本 skill 适配 Claude Code（Anthropic 官方 CLI）。

## 一、安装

把本 skill 目录复制到 Claude Code 的 skills 目录：

```bash
cp -r labs/skills/jingshi-jimin ~/.claude/skills/
```

或在 monorepo 内通过 workspace 引用（已含 `package.json` + `@wuji/libs` 依赖），无需额外构建。

## 二、调用

Claude Code 通过读取 `SKILL.md` 的 frontmatter（`name: jingshi-jimin` + `description`）
来识别本 skill。命中以下场景时，Claude 应先读 [`SKILL.md`](../SKILL.md)：

- 经营格局判断（义利兼顾）
- 定价 / 激励 / 资源调配（轻重之术）
- 组织治理底座设计（牧民四维）
- "先生存还是先谈格局"的次序判断（仓廪次序）
- 商业方案的"争利 vs 兴利"体检

显式触发示例：

```
读 jingshi-jimin skill，给这个定价方案做一次"争利还是兴利"的体检。
```

## 三、弹药层

需要《管子》真引用与概念体系时，加载弹药库：

- [`reference/guanzi.md`](../reference/guanzi.md) — 四支柱（仓廪次序 / 牧民四维 / 轻重之术 / 义利兼顾）+ 注明书·篇的真引用

## 四、底层一致性

本 skill 与 NoPUA「以道驭术·用信任替代恐惧」同源，可与 `nopua`、`tiangong` 等
WUJI Labs skill 并行加载，不冲突。

## 免责

建议性内容，非投资/财务/法律/专业决策依据。见 [`SKILL.md`](../SKILL.md) 免责声明。
