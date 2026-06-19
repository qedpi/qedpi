# Agent Context

This directory is the canonical home for durable agent-facing context in this repository.

- `skills/` — reusable workflows with `SKILL.md` files.
- `shared-references/` — stable project facts and reference material used by skills or agents.

Tool-specific views should symlink here instead of duplicating content. `.claude/skills` and `.codex/skills` point to `.agents/skills` so Claude Code and Codex read the same project skills.
