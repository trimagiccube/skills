# 为 Skills 仓库做贡献

感谢您对 Skills 仓库的关注！本指南将帮助您在本地设置仓库、创建新技能并推送代码。

## 目录
- [快速开始](#快速开始)
- [仓库设置](#仓库设置)
- [创建新技能](#创建新技能)
- [测试您的技能](#测试您的技能)
- [提交您的贡献](#提交您的贡献)
- [Git 工作流程](#git-工作流程)

## 快速开始

### 前置要求
- 在本地机器上安装 Git
- GitHub 账号
- 基本的 Markdown 和 YAML 知识

## 仓库设置

### 1. Fork 仓库（可选）
如果您想为主仓库做贡献，请先 fork：
1. 访问 https://github.com/trimagiccube/skills
2. 点击右上角的 "Fork" 按钮
3. 这将在您的 GitHub 账户下创建一个副本

### 2. 克隆仓库

将仓库克隆到本地机器：

```bash
# 如果您 fork 了仓库
git clone https://github.com/YOUR_USERNAME/skills.git

# 或直接克隆主仓库
git clone https://github.com/trimagiccube/skills.git

# 进入目录
cd skills
```

### 3. 设置远程仓库（如果已 fork）

如果您 fork 了仓库，设置上游远程仓库：

```bash
git remote add upstream https://github.com/trimagiccube/skills.git
```

验证远程仓库：

```bash
git remote -v
```

您应该看到：
```
origin    https://github.com/YOUR_USERNAME/skills.git (fetch)
origin    https://github.com/YOUR_USERNAME/skills.git (push)
upstream  https://github.com/trimagiccube/skills.git (fetch)
upstream  https://github.com/trimagiccube/skills.git (push)
```

## 创建新技能

### 1. 创建分支

始终为您的工作创建新分支：

```bash
git checkout -b my-new-skill
```

### 2. 创建技能文件夹

在 `skills` 目录中创建新文件夹：

```bash
mkdir skills/my-skill-name
```

### 3. 创建 SKILL.md 文件

每个技能都需要一个带有 YAML 前置数据的 `SKILL.md` 文件。使用模板：

```bash
cp template/SKILL.md skills/my-skill-name/SKILL.md
```

### 4. 编辑您的技能

编辑 `skills/my-skill-name/SKILL.md` 文件：

```markdown
---
name: my-skill-name
description: 清晰、完整地描述此技能的作用以及 Claude 应在何时使用它。
---

# 我的技能名称

## 目的
[解释此技能帮助完成什么]

## 说明
[Claude 将遵循的详细分步说明]

## 示例
- 使用示例 1
- 使用示例 2

## 指南
- 重要指南 1
- 重要指南 2

## 最佳实践
- 最佳实践 1
- 最佳实践 2
```

### 5. 添加额外资源（可选）

您可以在技能文件夹中包含其他文件：
- 脚本（Python、JavaScript 等）
- 配置文件
- 示例数据
- 文档

示例结构：
```
skills/my-skill-name/
├── SKILL.md
├── examples/
│   └── example.md
└── scripts/
    └── helper.py
```

## 测试您的技能

### 手动测试

1. **在 Claude Code 中：**
   - 将本地仓库注册为市场
   - 使用各种提示测试您的技能

2. **在 Claude.ai 中：**
   - 上传您的技能文件夹
   - 使用不同场景测试技能

3. **通过 API：**
   - 使用 Skills API 测试您的技能
   - 参见 [Skills API 快速入门](https://docs.claude.com/en/api/skills-guide)

### 验证检查清单

- [ ] YAML 前置数据有效
- [ ] `name` 是小写的，使用连字符
- [ ] `description` 清楚地解释了技能的作用
- [ ] 说明清晰且可操作
- [ ] 示例展示了典型用例
- [ ] 技能遵循[现有技能](./skills)的模式

## 提交您的贡献

### 1. 检查您的更改

查看您更改的内容：

```bash
git status
git diff
```

### 2. 暂存您的更改

将新技能添加到 git：

```bash
# 添加特定文件
git add skills/my-skill-name/

# 或添加所有更改
git add .
```

### 3. 提交您的更改

写一个清晰的提交消息：

```bash
git commit -m "添加 my-skill-name：简要描述其功能"
```

### 4. 推送到 GitHub

将您的分支推送到 GitHub：

```bash
# 如果在 fork 上工作
git push origin my-new-skill

# 如果直接在主仓库上工作
git push origin my-new-skill
```

### 5. 创建 Pull Request

1. 在 GitHub 上访问仓库
2. 点击 "Compare & pull request" 按钮
3. 填写 PR 模板，包括：
   - 描述您技能的清晰标题
   - 技能功能的描述
   - 您执行的任何测试
   - 截图或示例（如果适用）
4. 提交 pull request

## Git 工作流程

### 基本工作流程

```bash
# 1. 创建新分支
git checkout -b feature/my-skill

# 2. 进行更改
# ... 编辑文件 ...

# 3. 暂存更改
git add .

# 4. 提交更改
git commit -m "描述性提交消息"

# 5. 推送到远程
git push origin feature/my-skill

# 6. 在 GitHub 上创建 pull request
```

### 保持 Fork 更新

```bash
# 从上游获取最新更改
git fetch upstream

# 切换到主分支
git checkout main

# 合并上游更改
git merge upstream/main

# 将更新的主分支推送到您的 fork
git push origin main
```

### 在审查后进行更改

如果您收到 PR 反馈：

```bash
# 进行请求的更改
# ... 编辑文件 ...

# 暂存和提交
git add .
git commit -m "处理审查反馈：所做的具体更改"

# 推送到同一分支
git push origin my-new-skill
```

Pull request 将自动更新您的新提交。

## 常用 Git 命令

### 查看状态和历史
```bash
git status              # 查看更改内容
git log                 # 查看提交历史
git log --oneline       # 简化的历史
git diff                # 查看未暂存的更改
git diff --staged       # 查看已暂存的更改
```

### 分支管理
```bash
git branch              # 列出本地分支
git branch -a           # 列出所有分支（包括远程）
git checkout -b name    # 创建并切换到新分支
git checkout name       # 切换到现有分支
git branch -d name      # 删除本地分支
```

### 撤销更改
```bash
git checkout -- file    # 放弃对文件的更改
git reset HEAD file     # 取消暂存文件
git reset --hard        # 放弃所有本地更改（谨慎使用！）
```

## 成功的技巧

1. **阅读现有技能**：浏览 [skills 文件夹](./skills) 以了解模式和最佳实践

2. **从简单开始**：在处理复杂技能之前，先从简单的技能开始

3. **彻底测试**：确保您的技能在不同场景下按预期工作

4. **写清晰的描述**：技能描述对于 Claude 了解何时使用它至关重要

5. **遵循约定**：匹配现有技能的风格和结构

6. **寻求帮助**：如果遇到困难，请开启 issue 或在讨论区提问

## 资源

- [什么是技能？](https://support.claude.com/en/articles/12512176-what-are-skills)
- [在 Claude 中使用技能](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [如何创建自定义技能](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [Agent Skills 规范](./spec)
- [技能模板](./template)

## 许可证

贡献即表示您同意您的贡献将按照与项目相同的许可证（大多数技能为 Apache 2.0，除非另有说明）授权。

## 有问题？

如果您对贡献有疑问，请：
- 查看 [README.md](./README.md)
- 查看[现有技能](./skills)
- 开启 issue 进行讨论
- 参考 [Agent Skills 规范](./spec)

感谢您为让 Skills 变得更好而做出的贡献！🎉
