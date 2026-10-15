# oss-pr-helper

给开源框架提 PR 的助手 skill。只输出代码和指令，不自动修改任何文件。

[![skills.sh](https://skills.sh/b/koa-wang/oss-pr-helper)](https://skills.sh/koa-wang/oss-pr-helper)

## 安装

使用 open skills CLI：

```bash
npx skills add koa-wang/oss-pr-helper
```

或直接安装单个 skill 文件：

```bash
mkdir -p ~/.agents/skills/oss-pr-helper
cp skills/oss-pr-helper/SKILL.md ~/.agents/skills/oss-pr-helper/SKILL.md
```

## 触发词

提 PR、pull request、给开源项目贡献代码、准备 PR 内容

## 输出内容

- 分支名
- commit message
- 具体文件修改（+/- diff）
- PR 标题和描述

## 目录结构

```
oss-pr-helper/
├── LICENSE
├── README.md
└── skills/
    └── oss-pr-helper/
        └── SKILL.md
```

## License

[MIT](./LICENSE)
