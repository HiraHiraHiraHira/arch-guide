# arch-guide

一个面向技术研究、架构导览和可行性判断的 Codex skill。

它适合下面这类需求：

- 重建项目的 `what / how / why`
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
- 关键术语第一次出现时，优先补一句人话解释

## 安装

### 方式 1：本地目录安装

把整个目录放进：

```text
~/.codex/skills/
```

然后重启 Codex。

### 方式 2：使用 `.skill` 包

如果你拿到的是 `.skill` 文件，可以把它作为分发产物使用。这个包默认只保留运行时真正需要的文件；源码仓库仍然保留完整目录，方便继续维护和验证。

## 仓库内容

```text
arch-guide/
├── SKILL.md
├── README.md
├── CONTRIBUTING.md
├── RELEASING.md
├── evals/
│   └── evals.json
└── references/
    ├── evidence-model.md
    ├── feasibility-checklist.md
    ├── report-template.md
    └── senera-loop-example.md
```

## 一个典型用途

用户可能会这样说：

> 帮我看懂这个项目的 what、how、why，写成给新人看的架构导览，再判断它的可行性和边界。

这个 skill 的目标，就是把这类任务收成更稳定的输出结构，避免结果飘成随手研究笔记。

## 开发与维护

### 最小结构校验

```powershell
python <path-to-skill-creator>\scripts\quick_validate.py `
  <path-to-skills>\arch-guide
```

### 打包

从 `<path-to-skill-creator>` 目录运行：

```powershell
python -m scripts.package_skill `
  <path-to-skills>\arch-guide `
  <output-dir>
```

## 质量基线

当前仓库把固定测试提示保留在：

- [evals/evals.json](./evals/evals.json)

这些测试不是最终用户安装时必须携带的内容。它们是维护者用来观察输出稳定性的基线。

建议至少固定观察这些问题：

1. 有没有先给整体，再讲细节
2. 有没有总览图、表格或流程图
3. 有没有 `what / how / why`
4. 有没有区分“直接证据 / 工程推断 / 外部支持”
5. 关键术语第一次出现时有没有解释
6. 代码块后面有没有解释它在系统里负责什么
7. 有没有出现 AI 套话或写作元说明

## 贡献

提交改动前，建议先看：

- [CONTRIBUTING.md](./CONTRIBUTING.md)
- [RELEASING.md](./RELEASING.md)

如果只是想理解当前 skill 的风格目标，优先看：

- [SKILL.md](./SKILL.md)
- [references/report-template.md](./references/report-template.md)
