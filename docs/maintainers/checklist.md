# 维护检查清单

这份清单供维护者在修改或发布前复用，避免 `CONTRIBUTING.md` 和 `RELEASING.md` 各自维护一套重复流程。

## 1. 结构检查

运行结构校验：

```powershell
python <path-to-skill-creator>\scripts\quick_validate.py `
  <path-to-skills>\arch-guide
```

## 2. 内容检查

至少用下面两类样本各抽 1 到 3 条做一次回放：

- [../../evals/trigger-evals.json](../../evals/trigger-evals.json)
- `routing / style / boundary / delivery` 分类文件中的相关条目

重点观察：

- 有没有选对主报告 / followup / appendix / 直接更新
- 有没有总览图或清晰的流程降级形式
- 有没有主链路讲解
- 有没有证据分层
- 有没有重新冒出“本文遵守……”这类元说明
- 有没有把 README 口径误写成实现事实

## 3. 分层检查

确认下面这条边界仍然成立：

- `SKILL.md`：偏运行时路由与交付规则
- `references/`：偏模板、写作细则、证据模型
- `docs/maintainers/`：偏维护者专用说明
- `README / CONTRIBUTING / RELEASING / evals/`：偏维护与协作

## 4. 什么时候应该加新 eval

下面几种情况，应该新增或修改固定测试题：

- 你新增了一类明确能力
- 你修掉了一个反复出现的问题
- 你改变了输出风格的主约束
- 你发现旧测试已经不能区分“变好”和“变差”
- 你新增了一个高风险边界条件
