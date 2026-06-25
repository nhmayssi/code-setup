---
name: get-setup
description: Clone the personal coding setup from https://github.com/nhmayssi/code-setup (agy branch) into the current project. Use when the user says "get setup", "install setup", "clone my setup", or when .agents/ config is missing from a new project.
---

# get-setup

Clone the Antigravity (agy) configuration from the personal setup repo into the current project.

## Steps

1. Check if `.agents/` already exists in the current project root. If it does, ask the user before overwriting.

2. Run:
```bash
git clone --branch agy --depth 1 https://github.com/nhmayssi/code-setup /tmp/code-setup-agy
```

3. Copy config into the project:
```bash
cp -r /tmp/code-setup-agy/.agents ./
cp /tmp/code-setup-agy/AGENTS.md ./ 2>/dev/null || true
```

4. Clean up:
```bash
rm -rf /tmp/code-setup-agy
```

5. Report what was installed: skills count, rules count, hooks count.

## Notes

- This installs the **agy** branch — Antigravity CLI specific setup.
- For Claude Code: use `/get-setup` in Claude Code (installs `claude` branch → `.claude/`).
- For Codex: use the `get-setup` skill in Codex (installs `codex` branch → `.codex/`).
- Source repo: https://github.com/nhmayssi/code-setup
