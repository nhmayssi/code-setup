# code-setup — agy branch

Personal agentic coding setup for **Antigravity (agy)** — Google's Gemini-based terminal agent.

## Structure

```
AGENTS.md              ← project instructions (agy reads this automatically)
.agents/
  agents/              ← subagent definitions
  skills/ecc/*/        ← SKILL.md skills (auto-loaded via progressive disclosure)
  rules/               ← coding rules and standards
  hooks/               ← hook scripts
  config.toml          ← project-scoped agy config
  claude-commands-reference/  ← Claude Code slash commands (reference only, not native agy)
```

## Quick install for a new project

Run `/get-setup` inside agy, or manually:

```bash
git clone --branch agy --depth 1 https://github.com/nhmayssi/code-setup .agents-setup
cp -r .agents-setup/.agents ./
cp .agents-setup/AGENTS.md ./
rm -rf .agents-setup
```

## Branches

| Branch | Tool | Config dir | Root file |
|--------|------|------------|-----------|
| `claude` | Claude Code | `.claude/` | `CLAUDE.md` |
| `codex` | OpenAI Codex CLI | `.codex/` | `AGENTS.md` |
| `agy` | Antigravity (agy) | `.agents/` | `AGENTS.md` |
