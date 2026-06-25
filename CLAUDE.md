# code-setup

Personal agentic engineering setup for Claude Code. This is the starting point — install it into any project and customize down from here.

## What this is

A local `.claude/` configuration built on the full [ECC (Everything Claude Code)](https://github.com/affaan-m/ECC) install. It ships at maximum coverage so you can remove what you don't need rather than hunt for what to add.

## What's included

| Component | Count | What it does |
|-----------|-------|-------------|
| Skills | 271 | Workflow patterns Claude can follow — TDD, code review, security scans, research, orchestration, and more |
| Agents | 67 | Specialized subagents for language-specific review, build error resolution, planning, and domain tasks |
| Commands | 92 | Slash commands that trigger skills from the chat input |
| Hooks | 28 | Automations that run before/after tool calls — quality gates, format checks, session persistence, desktop notifications |

## How to use

Clone this repo into a project's `.claude/` directory, or use it as-is as your global `~/.claude/` base.

```bash
git clone https://github.com/nhmayssi/code-setup .claude
```

Then open Claude Code from that project — the skills, agents, and hooks activate automatically.

## Customizing

This is the max load-out. Start by removing what doesn't apply to your stack:

- **Skills** live in `.claude/skills/ecc/` — delete folders you don't need
- **Agents** live in `.claude/agents/` — delete YAML files for languages/frameworks you don't use
- **Hooks** are configured in `.claude/hooks/hooks.json` — comment out or remove individual hook entries
- **Rules** live in `.claude/rules/ecc/` — remove language rule sets that don't apply

## Source

Built from ECC v2.0.0 using `--target claude-project --profile full` plus all opt-in skills.
