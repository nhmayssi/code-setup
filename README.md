# code-setup — codex branch

Personal agentic coding setup for **OpenAI Codex CLI**.

## Structure

```
AGENTS.md              ← project instructions (Codex reads this automatically)
.codex/
  skills/ecc/*/        ← SKILL.md skills (auto-loaded via progressive disclosure)
  agents/              ← subagent definitions
  rules/               ← coding rules and standards
  hooks/               ← hook scripts
  config.toml          ← project-scoped Codex config (schema-validated)
  claude-commands-reference/  ← Claude Code slash commands (reference only, not native Codex)
```

## Quick install for a new project

Run the `get-setup` skill inside Codex, or manually:

```bash
git clone --branch codex --depth 1 https://github.com/nhmayssi/code-setup .codex-setup
cp -r .codex-setup/.codex ./
cp .codex-setup/AGENTS.md ./
rm -rf .codex-setup
```

Then trust the project in Codex so it loads `.codex/` config:

```bash
codex trust .
```

## Skills

Skills live in `.codex/skills/*/SKILL.md`. Codex loads them via progressive disclosure — only name and description on startup, full content when triggered.

Disable a skill without deleting it by adding to `~/.codex/config.toml`:

```toml
[[skills.config]]
path = ".codex/skills/ecc/some-skill/SKILL.md"
enabled = false
```

## Branches

| Branch | Tool | Config dir | Root file |
|--------|------|------------|-----------|
| `claude` | Claude Code | `.claude/` | `CLAUDE.md` |
| `codex` | OpenAI Codex CLI | `.codex/` | `AGENTS.md` |
| `agy` | Antigravity (agy) | `.agents/` | `AGENTS.md` |
