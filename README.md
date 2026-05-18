# arch-guide

一个面向技术研究、架构导览和可行性判断的通用 skill。

## 适用场景

它适合下面这类需求：

- 剖析项目的 `设计动机`
- 给新人写可读的架构导览
- 区分直接证据、工程推断、外部支持
- 评估系统设计的可行性、边界和风险
- 把散乱研究结果整理成结构化输出

默认目标是把结果收成更清楚的技术讲解材料：先给全局，再拆模块，再讲主链路，最后进入判断。

## 不适用场景

下面这些情况通常不该优先用它：

- 简单函数解释
- 一次性轻量问答
- 纯 bug 修复
- 纯实现建议或纯编码任务

## 使用方式

这个仓库不绑定特定平台。你可以按所用 agent、CLI 或 skill 系统的约定引入它；如果当前环境没有原生的 skill 机制，也可以直接把 [SKILL.md](./SKILL.md) 和 `references/` 里的材料作为提示与参考使用。

## 仓库结构

```text
arch-guide/
├── SKILL.md
├── README.md
├── CONTRIBUTING.md
├── RELEASING.md
├── docs/
│   └── maintainers/
│       ├── architecture.md
│       └── checklist.md
├── evals/
│   ├── boundary-evals.json
│   ├── delivery-evals.json
│   ├── evals.json
│   ├── routing-evals.json
│   ├── style-evals.json
│   └── trigger-evals.json
└── references/
    ├── appendix-template.md
    ├── evidence-model.md
    ├── feasibility-checklist.md
    ├── followup-template.md
    ├── report-sections.md
    ├── report-template.md
    └── senera-loop-example.md
```

分层约定：

- `SKILL.md`：运行时路由、边界、交付规则
- `references/`：模板、写作细则、证据模型
- `docs/maintainers/`：维护者专用说明
- `evals/`：固定测试题，其中 `evals.json` 保留兼容聚合视图，分类文件更适合维护
- `README / CONTRIBUTING / RELEASING`：维护与协作说明

## 一个典型用途

用户可能会这样说：

> 帮我看懂这个项目，写成给新人看的架构导览，再判断它的可行性和边界。

对应地，它通常会产出：

1. 主报告
2. 独立 followup
3. 材料型 appendix

具体路由规则看 [SKILL.md](./SKILL.md)。

## 继续阅读

- [SKILL.md](./SKILL.md)
- [docs/maintainers/architecture.md](./docs/maintainers/architecture.md)
- [docs/maintainers/checklist.md](./docs/maintainers/checklist.md)
- [evals/trigger-evals.json](./evals/trigger-evals.json)
- [references/report-template.md](./references/report-template.md)
- [references/report-sections.md](./references/report-sections.md)
- [references/followup-template.md](./references/followup-template.md)
- [references/appendix-template.md](./references/appendix-template.md)
