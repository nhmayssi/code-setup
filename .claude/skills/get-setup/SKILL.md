---
name: get-setup
description: Clone the personal coding setup from https://github.com/nhmayssi/code-setup (claude branch) into the current project. Use when the user says "get setup", "install setup", "clone my setup", or when .claude/ config is missing from a new project.
---

# get-setup

Clone the Claude Code configuration from the personal setup repo into the current project.

## Steps

1. Check if `.claude/` already exists in the current project root. If it does, ask the user before overwriting.

2. Run:
```bash
git clone --branch claude --depth 1 https://github.com/nhmayssi/code-setup /tmp/code-setup-claude
```

3. Copy config into the project:
```bash
cp -r /tmp/code-setup-claude/.claude ./
cp /tmp/code-setup-claude/CLAUDE.md ./ 2>/dev/null || true
```

4. Clean up:
```bash
rm -rf /tmp/code-setup-claude
```

5. Report what was installed: agents count, commands count, skills count, rules count.

## Notes

- This installs the **claude** branch — Claude Code specific setup.
- For Codex: use the `get-setup` skill in Codex (installs `codex` branch → `.codex/`).
- For agy: use the `get-setup` skill in agy (installs `agy` branch → `.agents/`).
- Source repo: https://github.com/nhmayssi/code-setup
