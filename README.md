# 🛠️ Agent Skills

Reusable instructions for AI coding agents. Each skill is a standalone set of guidelines that can be invoked to automate common repository tasks.

## Skills

| Skill | Description |
|-------|-------------|
| [**github-readme-builder**](./github-readme-builder/github-readme-builder.md) | Build or enhance a professional GitHub README for any project. |
| [**repo-bootstrapper**](./repo-bootstrapper/repo-bootstrapper.md) | Bootstrap a new repository with README, License, CI, and pre-commit hooks. |
| [**tidy-repo**](./tidy-repo/tidy-repo.md) | Perform repository cleanup, documentation audits, and maintenance chores. |

## Usage

Point your AI coding agent to the relevant skill file. For example, in your prompt:

```
Invoke the skill at ./repo-bootstrapper/repo-bootstrapper.md
```

Or copy the skill file into your project's `.agent/skills/` directory for persistent access.

## License

[MIT](./LICENSE)
