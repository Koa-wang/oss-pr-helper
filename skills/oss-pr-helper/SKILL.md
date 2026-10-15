---
name: oss-pr-helper
description: 给开源框架提 PR 的助手。当用户需要向开源项目提交 PR 时触发。只输出代码和指令，不自动修改任何文件。输出内容：分支名、commit message、具体文件修改（用 +/- diff 标清楚）、PR 标题和描述。触发词：提 PR、pull request、给开源项目贡献代码、准备 PR 内容。
metadata:
  version: "1.0.0"
  argument-hint: <目标仓库或 issue 链接>
---

# OSS PR Helper

向开源框架提 PR 时，输出完整操作指南，供用户手动执行。

## 核心原则

- 只输出，不执行。不自动创建分支、不修改文件、不 commit。
- 每个文件修改用 +/- diff 标注增删行。
- 用户复制粘贴即可复现。

## 工作流程

1. 确认目标仓库和关联 issue（如有）。
2. 阅读相关源码，理解上下文。
3. 输出：分支名 → commit message → diff → PR 标题和描述。
4. 如有多个文件，逐个列出，每个标明完整路径。

## 输出结构

按以下顺序输出：

### 1. 分支名

格式：`<type>/<short-description>`

```bash
git checkout -b fix/null-pointer-in-parser
```

type 取值：`fix` / `feat` / `docs` / `refactor` / `test` / `chore`

### 2. Commit Message

Conventional Commits 格式：`<type>(<scope>): <subject>`

- subject：英文，祈使句，≤72 字符，无句号
- body：解释 why，不是 what

### 3. 文件修改

每个文件用 diff 格式输出：

```diff
--- a/src/utils/parser.ts
+++ b/src/utils/parser.ts

@@ -10,7 +10,9 @@

 function parse(input: string) {
-  const result = input.split(',')
+  const result = input
+    .split(',')
+    .map(s => s.trim())
   return result
 }
```

- `+` 新增行
- `-` 删除行
- 无标记行为上下文

### 4. PR 标题和描述

输出一段可直接粘贴到 GitHub 的 PR title + body（Markdown）。
