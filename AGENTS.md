# Working with AI Agents

This repository showcases projects and code developed in collaboration with AI assistants.

*`CLAUDE.md` and `GEMINI.md` are symlinks to this file so multiple AI coding tools read the same guidance.*

## About This Approach

I believe in transparent collaboration between human creativity and AI capabilities. The projects here represent a partnership where:

- **Human:** Provides direction, domain expertise, architectural decisions, and critical thinking
- **AI Agent:** Assists with implementation, code generation, research, and problem-solving

## Development Workflow

When working with AI agents on software projects, I typically:

1. Define clear objectives and requirements
2. Collaborate on architecture and design decisions
3. Leverage AI coding agents for implementation assistance and code review
4. Maintain ownership of critical decisions and final code quality

## Projects

Projects in this profile may involve AI agent assistance in various capacities:
- Code generation and refactoring
- Documentation and technical writing
- Research and problem-solving
- Testing and debugging assistance

## Why Document This?

Transparency matters. As AI tools become integral to software development, I believe in being open about:
- How these tools are used in the development process
- The collaborative nature of modern software engineering
- The value of human-AI partnership in technical work

## Agent Context Structure

Agent-facing context lives in `.agents/` as the canonical source. Reusable workflows belong in `.agents/skills/<name>/SKILL.md`, and durable reference material belongs in `.agents/shared-references/`. Tool-specific views should symlink to that structure; `.claude/skills` and `.codex/skills` point to `.agents/skills`.

## AI Assistants Used

- [Claude](https://claude.ai) - Anthropic's AI assistant
- [Gemini](https://gemini.google.com) - Google's AI assistant
- [Codex](https://openai.com/codex/) - OpenAI's coding agent

---

*This approach to AI collaboration reflects my commitment to leveraging modern tools while maintaining high standards for code quality and engineering practices.*
