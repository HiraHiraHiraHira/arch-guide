# Contributing

这个 skill 更像一份“方法与表达风格的运行时约束”，而不是一个单纯模板。

所以在改它时，请重点看三件事：

1. 这次改动有没有让输出更像给人看的技术讲解
2. 这次改动有没有破坏证据分层
3. 这次改动有没有把运行时说明和维护者说明混在一起

## 改动原则

- 优先保持新人可读性
- 优先保持 `what / how / why`
- 优先保持图文并茂，而不是纯段落堆砌
- 优先保持术语首现解释
- 不要把写作元说明写进最终产物
- 不要让 `references/` 塞满只对维护者有用的材料

## 提交前检查

先看：

- [docs/maintainers/architecture.md](./docs/maintainers/architecture.md)
- [docs/maintainers/checklist.md](./docs/maintainers/checklist.md)

## 什么时候应该加新 eval

按 [docs/maintainers/checklist.md](./docs/maintainers/checklist.md) 的规则判断。

## 不建议的改法

- 只为了单个例子好看而塞进过拟合规则
- 把某次项目上下文写死成通用要求
- 为了好解释而加入大量空话
- 用维护者口吻污染最终输出
