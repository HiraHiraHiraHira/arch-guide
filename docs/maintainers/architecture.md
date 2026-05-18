# 维护者分层说明

这个仓库刻意把“运行时指导”和“维护时指导”分开，避免所有规则重新堆回 `SKILL.md`。

## 分层目标

维护时优先守住下面这条边界：

- `SKILL.md`：运行时路由、边界、交付规则
- `references/`：按需读取的模板、写作细则、证据模型
- `evals/`：固定测试题与行为回归样本
- `README.md`：仓库入口与使用概览
- `CONTRIBUTING.md` / `RELEASING.md`：维护与发布流程
- `docs/maintainers/`：只给维护者看的项目结构与检查说明

## 为什么这样拆

### 1. `SKILL.md` 保持轻

`SKILL.md` 的主要职责是让模型快速判断：

1. 这是不是它该接的任务
2. 该产出主报告、followup、appendix，还是只更新既有主报告
3. 交付时要不要落盘、落到哪里、最终怎么汇报

它不应该重新承载完整模板，也不应该变成维护者手册。

### 2. 模板细节放进 `references/`

主报告、followup、appendix 的章节骨架和写作细则更适合放在 `references/`：

- 避免 `SKILL.md` 膨胀
- 让模型只在需要时读取对应模板
- 让维护者可以单独迭代模板，而不改动主路由逻辑

### 3. `evals/` 独立承载回归样本

固定测试题不属于运行时指令。它们的职责是：

- 证明某次修改没有把既有行为弄坏
- 覆盖高风险边界
- 帮维护者判断“变好”还是“变差”

当前约定：

- `trigger-evals.json`：测该不该触发
- `routing-evals.json` / `style-evals.json` / `boundary-evals.json` / `delivery-evals.json`：按主题维护
- `evals.json`：兼容聚合视图，方便继续喂给旧流程

## 修改时的优先顺序

当你想加规则时，先问自己：

1. 这是运行时必须立即知道的路由或边界吗  
   如果是，考虑改 `SKILL.md`
2. 这是某类产物的章节结构或写作细节吗  
   如果是，优先改 `references/`
3. 这是为了防止行为回归的样本吗  
   如果是，改 `evals/`
4. 这是给维护者看的流程说明吗  
   如果是，改 `docs/maintainers/`、`README`、`CONTRIBUTING`、`RELEASING`

## 常见退化信号

出现下面这些情况，通常说明仓库分层开始变坏：

- `SKILL.md` 重新长出完整模板章节清单
- `README.md` 开始复述大量运行时规则
- `CONTRIBUTING.md` 和 `RELEASING.md` 粘贴同一套检查清单
- 为了修一个例子，把项目上下文写死进通用规则
- `references/` 里出现只对维护者有用、对模型运行时无帮助的说明
