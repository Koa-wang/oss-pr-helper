# oss-pr-helper

An agent skill that helps you prepare pull requests for open-source projects. It writes the code and instructions you need — but never touches a single file on its own.

[![skills.sh](https://skills.sh/b/koa-wang/oss-pr-helper)](https://skills.sh/koa-wang/oss-pr-helper)

## What it does

Give it a target repo (and an issue if you have one), and it hands you a complete, copy-paste-ready PR kit:

- a branch name
- a conventional commit message
- the exact file changes, marked up as a `+/-` diff
- a ready-to-paste PR title and description

It's deliberately read-only: no branch juggling, no commits, no surprise edits. You stay in control and run everything yourself.

## Install

Via the open skills CLI:

```bash
npx skills add koa-wang/oss-pr-helper
```

Or drop the skill file straight into your skills directory:

```bash
mkdir -p ~/.agents/skills/oss-pr-helper
cp skills/oss-pr-helper/SKILL.md ~/.agents/skills/oss-pr-helper/SKILL.md
```

## When it kicks in

It triggers on phrases like "提 PR", "pull request", "给开源项目贡献代码", or "prepare a PR".

## Repo layout

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
