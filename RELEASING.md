# Releasing

这份说明是给维护者的发布清单。

## 发布前

1. 确认 `SKILL.md` 已更新
2. 确认固定测试题仍然贴合当前 skill 目标
3. 跑一次结构校验
4. 至少做一轮人工内容检查

结构校验命令：

```powershell
python <path-to-skill-creator>\scripts\quick_validate.py `
  <path-to-skills>\arch-guide
```

## 打包

从 `<path-to-skill-creator>` 目录运行：

```powershell
python -m scripts.package_skill `
  <path-to-skills>\arch-guide `
  <output-dir>
```

输出示例：

```text
<output-dir>\arch-guide.skill
```

## 分发建议

推荐分成两层：

### 1. 源码仓库

保留：

- `SKILL.md`
- `references/`
- `evals/`
- `README.md`
- `CONTRIBUTING.md`
- `RELEASING.md`

适合继续协作和迭代。

### 2. 发布产物

优先发布 `.skill` 包。

注意：

- 当前打包脚本默认不会把 `evals/` 打进 `.skill`
- 当前打包脚本也不会把 `README.md`、`CONTRIBUTING.md`、`RELEASING.md`、`.gitignore` 打进 `.skill`
- 这符合“分发包轻量、维护资产留在源码仓库”的思路

## 建议的发布说明

每次发布时，最好写清楚：

- 这次主要改善了什么
- 有没有新增输出约束
- 有没有新增固定测试题
- 有没有行为变化，可能影响旧用法
