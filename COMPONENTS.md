# Profile components

This file describes what README.md renders on the qedpi GitHub profile. Update it in the same change as README.md.

## Top languages card

The card is the byte-weighted language share of public non-fork repositories owned by qedpi. The host is GitHub Stats Extended at https://github-stats-extended.vercel.app, the maintained successor of anuraghazra/github-readme-stats. The previous host https://github-readme-stats.vercel.app returns HTTP 503 with x-vercel-error DEPLOYMENT_PAUSED. anuraghazra/github-readme-stats says the project is unmaintained.

The layout parameter is `donut-vertical`. `theme=dark` is shown with `#gh-dark-mode-only`, and `theme=default` is shown with `#gh-light-mode-only`, so the card follows the viewer's GitHub theme.

On 2026-09-26 the byte-weighted card was about 95% Jupyter Notebook because notebook files are large. File-count weighting (size_weight=0&count_weight=1) produces a different ranking. Keep byte weighting unless the profile owner changes it.

Private repositories are excluded. Including them needs a self-hosted instance and a GitHub token stored outside this repository.

```markdown
## Top languages

[![Top languages](https://github-stats-extended.vercel.app/api/top-langs/?username=qedpi&theme=dark&layout=donut-vertical#gh-dark-mode-only)](https://github.com/stats-organization/github-stats-extended#gh-dark-mode-only)
[![Top languages](https://github-stats-extended.vercel.app/api/top-langs/?username=qedpi&theme=default&layout=donut-vertical#gh-light-mode-only)](https://github.com/stats-organization/github-stats-extended#gh-light-mode-only)
```

## Links left off the profile

- https://qedpi.com returns the hosting default page /cgi-sys/defaultwebpage.cgi (HTTP 200 HTML that refreshes there). No website badge.
- https://qedpi.com/cv returns 404. No CV badge.
- https://github.com/sponsors/qedpi redirects to https://github.com/qedpi. No sponsor badge. GitHub Sponsors is not enabled.
- A general stats card that shows a rank grade is omitted on purpose. The grade is a weighted percentile, not a measure of the work.
- Nostr is not on the profile. Do not add a placeholder npub.

## References

- https://github.com/stats-organization/github-stats-extended
- https://github.com/anuraghazra/github-readme-stats
