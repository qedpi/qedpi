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
- `layout` - Display layout (compact, default)
- `hide` - Comma-separated list of languages to exclude
- `langs_count` - Number of languages to display

Example with more customization:
```markdown
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=qedpi&theme=radical&layout=compact&langs_count=8&hide=html,css)](https://github.com/anuraghazra/github-readme-stats)
```

## Future Improvements

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

## Additional Resources

- [GitHub README Stats Documentation](https://github.com/anuraghazra/github-readme-stats)
- [Available Themes](https://github.com/anuraghazra/github-readme-stats/blob/master/themes/README.md)
- [GitHub's Language Statistics](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-repository-languages)
