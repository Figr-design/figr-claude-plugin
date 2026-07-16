# Figr - Claude Code marketplace

Public install source for the Figr Claude Code plugin (MCP + `figr-mcp` skill).

**Live repo:** https://github.com/Figr-design/figr-claude-plugin (public)

Source of truth in the monorepo: `coding-agents/figr-claude-plugin/` inside private `figr-ai`. After editing here, push updates to the public repo (this folder’s contents → repo root).

## Install

In Claude Code:

```text
/plugin marketplace add Figr-design/figr-claude-plugin
/plugin install figr@figr
```

## Layout

```text
.claude-plugin/marketplace.json   # marketplace name: figr
figr/                             # plugin name: figr → install as figr@figr
  .claude-plugin/plugin.json
  .mcp.json
  skills/figr-mcp/
```

## Local test

```bash
claude --plugin-dir ./figr
```

## Validate

```bash
claude plugin validate ./figr --strict
```

## Sync monorepo → public repo

From `coding-agents/figr-claude-plugin/`:

```bash
git init -b main
git add -A && git commit -m "chore: sync marketplace"
git remote add origin git@github.com:Figr-design/figr-claude-plugin.git
git push -u origin main --force
```

(Prefer a dedicated worktree/script over nesting `.git` long-term.)
