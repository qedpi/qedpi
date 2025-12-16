# GitHub Profile Components

This document explains the various components and services used in this GitHub profile repository.

<!--
**qedpi/qedpi** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I'm currently working on ...
- 🌱 I'm currently learning ...
- 👯 I'm looking to collaborate on ...
- 🤔 I'm looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

## Language Statistics Card

### What It Does
Displays a dynamic card showing the most commonly used programming languages across all public repositories.

### Implementation
```markdown
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=qedpi&theme=dark&layout=compact)](https://github.com/anuraghazra/github-readme-stats)
```

### How It Works
1. **GitHub API Integration**: The service uses GitHub's official REST API (not web scraping) to fetch repository data
2. **Language Analysis**: GitHub already calculates language breakdowns for each repository; this service aggregates that data
3. **Dynamic SVG Generation**: On each profile view, the Vercel-hosted service generates an SVG image on-the-fly
4. **Caching**: Results are cached for a few hours to avoid hitting GitHub's API rate limits
5. **Server-Side Rendering**: The image is generated server-side and served as a response to the image request

### Service Details
- **Provider**: [github-readme-stats](https://github.com/anuraghazra/github-readme-stats)
- **Hosting**: Vercel
- **Open Source**: Yes, fully transparent implementation
- **Updates**: Automatically updates based on repository changes (with caching delay)

### Customization Options
The card supports various parameters:
- `username` - Your GitHub username
- `theme` - Color theme (dark, light, radical, merko, gruvbox, etc.)
- `layout` - Display layout (compact, default, donut, donut-vertical)
- `hide` - Comma-separated list of languages to exclude
- `langs_count` - Number of languages to display
- `size_weight` - Weight for byte count (default: 1)
- `count_weight` - Weight for file count (default: 0)

Example with more customization:
```markdown
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=qedpi&theme=radical&layout=compact&langs_count=8&hide=html,css)](https://github.com/anuraghazra/github-readme-stats)
```

### Private Repository Support

**Important Limitation:** The public Vercel instance (github-readme-stats.vercel.app) **only counts public repositories**. It cannot access private repository data.

**Solution - Self-Hosting:**
To include private repositories in language statistics, you need to self-host your own instance:

1. Fork the [github-readme-stats](https://github.com/anuraghazra/github-readme-stats) repository
2. Deploy to Vercel (free tier supported)
3. Create a GitHub Personal Access Token with `repo` and `user` permissions
4. Add the token as environment variable `PAT_1` in your Vercel deployment
5. Update `maxDuration` in `vercel.json` to `10` seconds (required for free Vercel accounts)
6. Use your Vercel instance URL instead of the public one

**References:**
- [Discussion: Does top-langs count private repos?](https://github.com/anuraghazra/github-readme-stats/discussions/1554)
- [Issue: Private repo support for Top Languages](https://github.com/anuraghazra/github-readme-stats/issues/653)
- [Discussion: Top Languages and private count](https://github.com/anuraghazra/github-readme-stats/discussions/814)

## Optional Components

### GitHub Stats Card

The github-readme-stats service also provides a comprehensive stats card showing:
- Total stars earned
- Total commits (last year)
- Total PRs
- Total issues
- Repositories contributed to
- Grade badge (A+, A, B-, etc.)

**Implementation:**
```markdown
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=qedpi&show_icons=true&theme=dark&count_private=true&line_height=40)
```

**Note:** This profile doesn't use this card due to the grading system, which can feel arbitrary and gamify contributions in ways that don't necessarily reflect meaningful work. The language statistics card provides useful information without the judgmental aspect.

**Customization Options:**
- `show_icons` - Display icons for each stat
- `count_private` - Include private repository contributions
- `hide` - Hide specific stats (e.g., `&hide=issues,contribs`)
- `include_all_commits` - Count all commits instead of just current year
- `show` - Show additional stats like reviews or discussions

## Future Improvements

### Self-Hosted Language Statistics with Private Repos

**Current Limitation:** The language card currently only shows public repository statistics.

**Potential Solutions:**

1. **Self-host github-readme-stats** (Existing solution)
   - Fork and deploy to Vercel with GitHub PAT
   - Requires maintaining fork and syncing with upstream
   - Free tier supported with `maxDuration=10` limit

2. **Build Custom Solution** (Future consideration)
   - Simpler implementation focused only on language stats
   - No need to maintain fork of larger project
   - Could integrate with custom activity tracking (see below)
   - Self-hosted with full control over data and metrics

**Pros of Custom Solution:**
- Tailored to specific needs (just language stats, no grading)
- Easier to maintain than keeping fork synced
- Could add custom metrics (e.g., exclude generated code, weight by project importance)
- Integration with private activity tracking service

**Cons:**
- Need to build and maintain from scratch
- github-readme-stats is already well-tested and feature-rich
- Self-hosting their fork is straightforward

**Decision:** Start with self-hosted github-readme-stats fork if private repo stats are needed. Consider custom solution only if additional custom features become necessary.

### Custom Activity Tracking Service
Build a custom alternative to WakaTime that provides meaningful coding activity insights without the surveillance feel:

**Why Build Our Own:**
- WakaTime's free tier only keeps 1 week of history (limited utility)
- Premium tier ($12/month) required for unlimited history
- Privacy concerns with third-party activity monitoring
- Opportunity to create more meaningful, personalized metrics

**Potential Features:**
- Self-hosted solution with full data ownership
- IDE plugin for activity tracking (VS Code, JetBrains, etc.)
- Local-first approach with optional cloud sync
- Custom metrics tailored to personal productivity goals
- Integration with GitHub profile cards
- Open source implementation for transparency
- Focus on insights over surveillance

**Technical Approach:**
- Lightweight IDE extensions for activity capture
- Local database for historical data
- API endpoint for generating SVG stats cards
- Similar architecture to github-readme-stats (Vercel + dynamic SVG generation)
- Privacy-focused: no tracking without explicit consent

## Sponsor Badge

A simple badge linking to GitHub Sponsors using shields.io:

```markdown
[![Sponsor](https://img.shields.io/badge/Sponsor-%E2%9D%A4-red?style=for-the-badge&logo=github)](https://github.com/sponsors/qedpi)
```

### What is shields.io?
[Shields.io](https://shields.io/) is a service that provides customizable badges/shields for GitHub READMEs. You can create badges for:
- Build status
- Coverage
- Version numbers
- Downloads
- Custom messages (like the sponsor badge)

## Nostr Integration

**What is Nostr?**

[Nostr](https://nostr.com/) (Notes and Other Stuff Transmitted by Relays) is an open, decentralized protocol for message transmission designed to resist internet censorship while maintaining session integrity.

### npub - Your Nostr Public Key

An **npub** is your Nostr public identity key. Key characteristics:

- **Public and shareable**: Your npub is meant to be shared publicly
- **Unique identifier**: Used to look up your profile and connect with you
- **Verification**: Others use it to verify your identity through message signatures
- **Encryption**: Used by others to encrypt private messages to you
- **Format**: User-friendly encoding (vs hexadecimal) of your public key

**Example Usage in Profile:**
```markdown
**Nostr:** `npub1your_nostr_public_key_here`
```

### Why Include Nostr?

Including your npub allows supporters to connect with you on decentralized social platforms, providing an alternative to traditional centralized social media.

**Learn More:**
- [Nostr Official Site](https://nostr.com/)
- [Nostr on Wikipedia](https://en.wikipedia.org/wiki/Nostr)
- [Nostr FAQs](https://nostrdesign.org/docs/faq/)

## Additional Resources

- [GitHub README Stats Documentation](https://github.com/anuraghazra/github-readme-stats)
- [Available Themes](https://github.com/anuraghazra/github-readme-stats/blob/master/themes/README.md)
- [GitHub's Language Statistics](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-repository-languages)
- [Shields.io Badge Service](https://shields.io/)
