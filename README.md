# arch-guide

一个面向技术研究、架构导览和可行性判断的通用 skill。

它适合下面这类需求：

- 剖析项目的 `设计动机`
- 给新人写可读的架构导览
- 区分直接证据、工程推断、外部支持
- 评估系统设计的可行性、边界和风险
- 把散乱研究结果整理成结构化输出

这个 skill 的目标是把结果收成更清楚的技术讲解材料：先给全局，再拆模块，再讲主链路，最后进入判断。

## 它强调什么

- 使用者语言优先，但不把“写作原则”直接写进成稿
- 新人可读性优先，先建立全局，再进入细节
- 图文并茂，代码片段后面紧跟中文解释
- 把事实、推断、外部支持分开，不混写

## 使用方式

这个仓库不绑定特定平台。你可以按所用 agent、CLI 或 skill 系统的约定引入它；如果当前环境没有原生的 skill 机制，也可以直接把 [SKILL.md](./SKILL.md) 和 `references/` 里的材料作为提示与参考使用。

## 核心内容

```text
arch-guide/
├── SKILL.md
├── README.md
└── references/
    ├── evidence-model.md
    ├── feasibility-checklist.md
    ├── report-template.md
    └── senera-loop-example.md
```

## 一个典型用途

用户可能会这样说：

> 帮我看懂这个项目，写成给新人看的架构导览，再判断它的可行性和边界。

这个 skill 的目标，就是把这类任务收成更稳定的输出结构，避免结果飘成随手研究笔记。

## 继续阅读

- [SKILL.md](./SKILL.md)
- [references/report-template.md](./references/report-template.md)
