# qedpi profile repository

This repository is the GitHub profile README for qedpi. `README.md` is the profile page.

*`CLAUDE.md` and `GEMINI.md` are symlinks to this file.*

## Profile content

- Keep `README.md` to cards and links whose destinations return the intended page.
- The top-languages card uses `github-stats-extended.vercel.app` with layout `donut-vertical`, `theme=dark` for `#gh-dark-mode-only`, and `theme=default` for `#gh-light-mode-only`.
- Leave `github-readme-stats.vercel.app` unused. Its README says the project is no longer maintained and names GitHub Stats Extended as the successor. The host served cards again on 2026-10-12 (HTTP 200) after a 503 `DEPLOYMENT_PAUSED` period, so uptime is not the reason.
- Add a website or CV badge only after `qedpi.com` serves a real site and `qedpi.com/cv` returns that CV. Today the domain serves the host default page, and `/cv` returns 404.
- Add a sponsor badge only after `https://github.com/sponsors/qedpi` stays on GitHub Sponsors. Today it redirects to the profile.
- Leave out the GitHub profile template comment that begins "I'm currently working on".
- **Default:** Leave the language card byte-weighted. Notebook files make Jupyter Notebook about 95% of the bytes. Change `size_weight` or `count_weight` only when the profile owner asks.

## Repository layout

- Agent-facing files live in `.agents/`. Read `.agents/README.md` before adding a skill or reference.
- Update `COMPONENTS.md` in the same change as `README.md`.
- Hooks: `.pre-commit-config.yaml` (run `pre-commit install` once per clone) checks whitespace and JSON at commit, `README.md` links with lychee at push, and Conventional Commits at commit-msg.
- There is no package manifest and no workflow. Add Renovate `packageRules` for npm, React, Next.js, TypeScript, ESLint, Prettier, or GitHub Actions only after those files exist.
- `.claude/settings.local.json` is local permissions and stays untracked.

## Collaboration

- The profile owner decides which links are real and which stats metric is shown.
- Edit only the files the request names.
