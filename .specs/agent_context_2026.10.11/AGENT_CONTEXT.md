# Agent context rewrite (2026-10-11)

Base: `0c3a136`. Rubric: `~/.agents/skills/agent-context-style/references/rewrite-rubric.md`. No improvement plan exists, so this ledger lives in its own `.specs/` folder.

## Baseline

| File | Lines | Chars |
|------|-------|-------|
| `AGENTS.md` | 27 | 1772 |
| `.agents/README.md` | 8 | 454 |
| Total in scope | 35 | 2226 |

- Skills: 0 (`.agents/skills/`, `.agents/shared-references/` hold only `.gitkeep`)
- Dangling symlinks: none. `CLAUDE.md`, `GEMINI.md` -> `AGENTS.md`; `.claude/skills`, `.codex/skills` -> `.agents/skills`
- Gates: none (no `.pre-commit-config.yaml`, no validator, no workflow)
- Verified 2026-10-11: top-languages card host, layout and themes in `README.md`; `github-readme-stats.vercel.app` absent from `README.md`; `qedpi.com` serves the host default page (`/cgi-sys/defaultwebpage.cgi`); `qedpi.com/cv` 404; `github.com/sponsors/qedpi` 302 to `github.com/qedpi`; `.claude/settings.local.json` gitignored

## Ledger

| File | Item | Action | Reason | Evidence |
|------|------|--------|--------|----------|
| `AGENTS.md` | "Leave `github-readme-stats.vercel.app` unused. That host returns HTTP 503 `DEPLOYMENT_PAUSED`, and anuraghazra/github-readme-stats is unmaintained." | flag | both reasons look stale; the rule is an owner decision, so the text stays | `curl https://github-readme-stats.vercel.app/api?username=qedpi` returns 200 with a rendered SVG; `gh api repos/anuraghazra/github-readme-stats`: `archived=false`, last push 2026-10-01 |

No edits: `AGENTS.md` and `.agents/README.md` pass the rubric.

## Result

| Repo | AGENTS.md lines | Skills touched/total | Description chars median/max | In-scope chars | Commits | Pushed | Validators |
|------|-----------------|----------------------|------------------------------|----------------|---------|--------|------------|
| qedpi | 27->27 | 0/0 | n/a | 2226->2226 | 1 | pending | none configured |

Lost-fact check: no removed lines.
