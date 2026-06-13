# 经世济民 Benchmark Suite — 评测设计（本文件为设计，非结果）

> ⚠️ **结果待真实运行。本仓未跑出任何数字。**
> 本文件只交付：评测目的、对照设计、场景集、评分 rubric、CLI 与统计方法、复现步骤。
> 任何 before/after 得分、命中率、p 值、效应量都**尚未产生**——见下方"诚信声明"。

## 1. 评测目的

衡量：加载 **经世济民 skill（SKILL.md）** 是否让 AI 在经营/格局类任务上，
比 **baseline（无 skill）** 更可靠地做出"次序正确、查承重墙、动态调节、兴利非争利"的判断，
且**不过度触发**（纯技术任务上不强加《管子》框架）。

## 2. 对照设计（两条件 + 一控制场景）

| 条件 | System Prompt | 目的 |
|------|--------------|------|
| **Baseline** | 通用助手提示（无本 skill） | 测原生经营推理倾向（多偏纯优化/零和） |
| **Skill** | 加载完整 `../SKILL.md` + `../reference/guanzi.md` | 测加载后是否触发四支柱框架 |

- 场景 1–6 为**正向场景**：skill 应改变判断（次序/四维/轻重/义利）。
- 场景 7 为**反触发控制场景**：纯技术任务，skill **不应**激活，用于测精确率（防 over-trigger）。

## 3. 场景集

见 [`scenarios.json`](scenarios.json)，共 **7 个场景**，每条含：

| 字段 | 含义 |
|------|------|
| `id` / `category` / `name` | 标识与分类 |
| `description` | **ground truth**（标准答案，不给 agent 看） |
| `task` | 给 agent 的用户 prompt |
| `expected_actions` | 一个到位的回答应命中的动作清单 |
| `difficulty` | easy / medium / hard |

类别覆盖：仓廪次序、义利兼顾、牧民四维、轻重之术、利益相关方共赢、四支柱合参、反触发控制。

## 4. 评分 rubric

每个 (条件 × 场景 × run) 的回答按两类打分：

### 4.1 expected_actions 命中率（客观）
- 对照该场景 `expected_actions` 逐条判"命中/未命中"（可由人工或裁判模型判）。
- 命中率 = 命中条数 / 总条数。
- **反触发场景（id=7）反向计分**：出现《管子》框架/状态行 = 扣分；直接答对技术题 = 满分。

### 4.2 维度评分（1–5 分，李克特）

| 维度 | 问题 |
|------|------|
| 次序意识 | 是否先判"仓廪实了吗"再谈格局？ |
| 治理结构 | 是否查四维承重墙而非只叠 KPI？ |
| 动态调节 | 是否把价格/激励当动态变量调节回平衡？ |
| 兴利取向 | 是否识别争利、改造为兴利？ |
| 引用诚信 | 引《管子》是否注明书·篇、未杜撰原文？ |
| 触发精确 | 该触发时触发、不该触发时克制？ |

> 维度评分主观，须 ≥2 名评分者独立打分并报 inter-rater agreement（如 Cohen's κ）。
> 评分者可为人工或裁判 LLM；用裁判 LLM 须固定裁判 prompt 并在报告披露。

## 5. CLI 用法（执行器待接入）

参考金标准 nopua 的 `run_benchmark.py` 接口约定（本 skill 可复用同构脚本）：

```bash
# 全量：两条件各 N 次
python run_benchmark.py --model claude-opus-4 --condition all --runs 5

# 单条件
python run_benchmark.py --model gpt-4o --condition skill --runs 5

# 单场景调试
python run_benchmark.py --model gemini-2.5-pro --scenario 3 --condition baseline --runs 1

# 干跑（只打印计划，不调用 API）
python run_benchmark.py --model claude-opus-4 --condition all --dry-run
```

| Flag | 说明 | 默认 |
|------|------|------|
| `--model` | 被测模型 | 必填 |
| `--condition` | `baseline` / `skill` / `all` | `all` |
| `--runs` | 每场景每条件重复次数 | `5` |
| `--scenario` | 指定场景 id（1–7）或全部 | 全部 |
| `--output-dir` | 结果 JSON 输出目录 | `results/` |
| `--dry-run` | 只打印计划不执行 | off |

> 注：`run_benchmark.py` / `analyze_results.py` 为加分项，可照 nopua 同构移植；
> 本 skill 当前先交付**场景集 + 评测设计 + rubric**（硬门槛），脚本接入后即可真跑。

## 6. 统计方法（待数据后应用）

- **配对比较**（同 scenario × run 跨条件）：Wilcoxon signed-rank（非参数，小样本稳健）。
- **非配对回退**：Mann-Whitney U。
- **效应量**：Cohen's d（|d|<0.2 可忽略，0.2–0.5 小，0.5–0.8 中，>0.8 大）。
- **显著性**：`*` p<0.05，`**` p<0.01，`***` p<0.001，`n.s.` 不显著。
- **评分者一致性**：维度评分报 Cohen's κ / ICC。

> 上述方法**仅在产生真实 results 后**应用。本文件不预填任何统计量。

## 7. 输出结构（运行后）

```
benchmark/
├── scenarios.json            # 7 场景（已交付）
├── README_BENCHMARK.md       # 本文件（评测设计，已交付）
├── run_benchmark.py          # 执行器（加分项，待接入）
├── analyze_results.py        # 统计分析（加分项，待接入）
└── results/                  # 运行后自动生成；当前为空
    ├── <model>_baseline.json
    └── <model>_skill.json
```

## 8. 成本估算（粗略，未含真实计费）

每全量 run ≈ 7 场景 × 2 条件 × 5 次 = 70 次主调用（+ 可选裁判调用）。
具体 token / 费用随模型与回答长度变化，运行前以 `--dry-run` 核计划。
**此处不填具体金额，避免与未运行的事实不符。**

## 9. 如何加场景

编辑 `scenarios.json` 追加：

```json
{
  "id": 8,
  "category": "<pillar>",
  "name": "Short name",
  "description": "ground truth, NOT shown to agent",
  "task": "user prompt shown to agent",
  "expected_actions": ["what a thorough answer should do"],
  "difficulty": "easy|medium|hard"
}
```

正向场景须能区分"开/不开 skill"；建议每批保留至少一个反触发控制场景测精确率。

## 10. 诚信声明（research-integrity 铁律）

- 本目录**不含任何编造的 p 值、百分比、胜率、效应量**。
- 所有"结果"字段在真实运行前保持空缺。
- 引用《管子》一律注明书·篇，逐字精确以中华书局/通行校注本为准（见 `../reference/guanzi.md`）。
- 本领域属**建议性内容**，评测衡量的是格局推理质量，非投资/财务/法律正确性。

---

*WUJI Labs · 经世济民 Benchmark 设计 · 结果待真实运行 · 2026-06-02*
