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
| `AGENTS.md` | `spec-lifecycle` pointer lines | skip | no `.notes/`, no plans; `.specs/` holds only this ledger, so the repo has no spec convention to point at | rg for `specs/archive`, `past_plans`, `current_plan`, `.notes`: no hits |

No edits: `AGENTS.md` and `.agents/README.md` pass the rubric.

## Result

| Repo | AGENTS.md lines | Skills touched/total | Description chars median/max | In-scope chars | Commits | Pushed | Validators |
|------|-----------------|----------------------|------------------------------|----------------|---------|--------|------------|
| qedpi | 27->27 | 0/0 | n/a | 2226->2226 | 1 | yes | none configured |

Lost-fact check: no removed lines.

## Improvement pass 2026-10-12

| Change | Why | Evidence | Commit |
|---|---|---|---|
| `AGENTS.md` and `COMPONENTS.md`: keep `github-readme-stats.vercel.app` unused, but state the true reason (upstream README says it is no longer maintained and names GitHub Stats Extended as the successor) and drop the 503 claim | fleet follow-up A3 (delegated): the 503 reason was stale | 2026-10-12: `curl -sI` on the host returns 200 `image/svg+xml`; `gh api repos/anuraghazra/github-readme-stats`: `archived=false`, pushed 2026-10-01; its README line 36: "This repository is no longer maintained. Please use the successor project GitHub Stats Extended" | `a13a741` |

Live URL check (2026-10-12): both README card URLs (dark, light) 200 `image/svg+xml`; `github.com/stats-organization/github-stats-extended` 200; `qedpi.com/cv` 404 and `github.com/sponsors/qedpi` 302 to the profile, so the AGENTS.md rules on CV and sponsor badges still hold. README content unchanged (nothing broken).

Not done, on purpose: no hooks or CI added (no code to check; Actions billing is open for Tom); empty `.agents/skills/` and `shared-references/` kept as the shared layout.
