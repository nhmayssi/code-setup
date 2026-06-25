# code-setup — claude branch

Personal agentic coding setup for **Claude Code** (Anthropic's CLI).

## Structure

```
CLAUDE.md              ← project instructions (Claude Code reads this automatically)
.claude/
  agents/              ← subagent definitions (*.md)
  commands/            ← slash commands (/command-name)
  skills/ecc/*/        ← SKILL.md skills (progressive disclosure)
  rules/ecc/*/         ← path-scoped coding rules
  hooks/               ← PreToolUse / PostToolUse / Stop hooks
  AGENTS.md            ← cross-tool instructions file
  settings.json        ← Claude Code settings
```

## Quick install for a new project

Run `/get-setup` inside Claude Code, or manually:

```bash
git clone --branch claude --depth 1 https://github.com/nhmayssi/code-setup .claude-setup
cp -r .claude-setup/.claude ./
cp .claude-setup/CLAUDE.md ./
rm -rf .claude-setup
```

## Key concepts

- **Agents** (`.claude/agents/*.md`): subagents Claude spawns automatically for specialized tasks
- **Commands** (`.claude/commands/*.md`): slash commands you invoke as `/command-name`
- **Skills** (`.claude/skills/*/SKILL.md`): loaded on demand via progressive disclosure
- **Rules** (`.claude/rules/**/*.md`): scoped to specific file paths or languages
- **Hooks**: shell commands that run on tool events (PostToolUse, PreToolUse, Stop)

## Branches

| Branch | Tool | Config dir | Root file |
|--------|------|------------|-----------|
| `claude` | Claude Code | `.claude/` | `CLAUDE.md` |
| `codex` | OpenAI Codex CLI | `.codex/` | `AGENTS.md` |
| `agy` | Antigravity (agy) | `.agents/` | `AGENTS.md` |
