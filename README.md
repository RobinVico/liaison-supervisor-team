# liaison-supervisor-team

A Claude Code skill for running a project as a small AI team: you talk to one window, and a team of Claude sessions and subagents does the work.

一个 Claude Code 技能：人只跟一个窗口说话，背后是一个 AI 团队在干活。

## Roles / 角色

| Role | 角色 | What it does |
|---|---|---|
| Human | 人 | Gives requirements, makes decisions, provides keys, runs commands that must be run in person |
| Liaison | 对接员 | A Claude session that only talks to you: relays instructions, translates replies into plain language, verifies facts, records decisions. Never writes code or touches keys. |
| Supervisor | 主管 | A Claude session that writes code, makes technical decisions, splits work, spawns subagents, integrates and verifies |
| Manager | 经理 | Optional subagent that owns a large area (for example, a full redesign) and directs its own workers |
| Workers | 员工 | Subagents that each change only their assigned files. Model chosen by difficulty: small model for small tasks, strongest model only for hard ones |

## Install / 安装

```bash
git clone https://github.com/RobinVico/liaison-supervisor-team.git ~/.claude/skills/liaison-supervisor-team
```

Restart Claude Code. The skill triggers when you mention a liaison, supervisor, manager, workers, or running several agents.

## Use / 使用

1. In your project folder, open Claude Code and say: "Set up this project with the liaison and supervisor workflow." / 「用对接员主管的方式搭这个项目」。It creates `LIAISON.md`, a supervisor section for `CLAUDE.md`, `HUMAN_TODO.md`, `PROGRESS.md` and an `inbox/` folder from the templates in `references/`.
2. Terminal 1 is the supervisor. Tell it what to build.
3. Terminal 2 is the liaison. Its first message: "You are the liaison. Read LIAISON.md and follow it." / 「你是对接员，读 LIAISON.md，按里面的规则工作。」
4. From then on, talk only to the liaison.

Both terminals should use the same permission mode, so cross-session messages are not held for approval.

## Files / 文件

| File | Purpose |
|---|---|
| `SKILL.md` | The skill: roles, how each role works, model routing, common pitfalls |
| `references/liaison-md.md` | Template for `LIAISON.md` |
| `references/supervisor-claude-md.md` | Template for the supervisor section of `CLAUDE.md` |
| `references/human-todo.md` | Template for `HUMAN_TODO.md` |
| `references/progress.md` | Template for `PROGRESS.md` |

The skill text is in Chinese.

## License / 许可证

MIT. Anyone can use, modify and share this skill, as long as the copyright notice is kept. See [LICENSE](LICENSE).

MIT 许可证：任何人都可以免费使用、修改和转发，只要保留版权声明。
