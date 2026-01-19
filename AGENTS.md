# AGENTS.md

Guidelines for AI agents working on this repository.

## Principles

- **Update this file**: Whenever you discover something new about this project—APIs, tools, gotchas—append it here.
- **Keep README current**: Update `README.md` after adding or modifying skills.
- **Skill format**: Each skill lives in its own folder with a markdown file. Use YAML frontmatter for metadata (`description:`).

## Structure

```
agent-skills/
├── github-readme-builder/
│   └── github-readme-builder.md
├── repo-bootstrapper/
│   ├── repo-bootstrapper.md
│   └── LICENSE_TEMPLATE
└── tidy-repo/
    └── tidy-repo.md
```

## Adding a New Skill

1. Create a new folder: `skill-name/`
2. Add a markdown file: `skill-name.md`
3. Include YAML frontmatter with a `description` field.
4. Update the table in `README.md`.
