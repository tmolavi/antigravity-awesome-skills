# Contributing Guidelines

Thank you for your interest in contributing to **Molavi Agent Skills**!

To maintain the quality, safety, and security of this collection, please follow these guidelines when submitting a new skill or improvement.

---

## Pre-PR Checklist

Before opening a Pull Request, verify every item below:

- [ ] **No secrets**: The skill contains no real API keys, passwords, tokens, or credentials. All sensitive values use clearly labeled placeholders (e.g., `YOUR_API_KEY_PLACEHOLDER`).
- [ ] **No local private paths**: No absolute paths specific to your local machine (e.g., `/Users/yourname/...`).
- [ ] **No destructive defaults**: Any command that modifies, deletes, or drops data must require explicit user confirmation. `DROP`, `DELETE`, `TRUNCATE`, and `rm -rf` patterns should not be the default action.
- [ ] **Frontmatter is complete**: The `SKILL.md` file includes a valid `name` and `description` in its YAML frontmatter.
- [ ] **Examples use placeholders**: All example configs, connection strings, and credentials use safe, clearly marked placeholder values.
- [ ] **Credits retained**: If the skill is adapted from another source, include attribution in a comment or `## Source` section.
- [ ] **No duplicate skill**: Search the `skills/` directory to confirm a similar skill does not already exist before submitting a new one.
- [ ] **Safety-first for MCP/database skills**: Any skill that configures a database or file system MCP must default to read-only access and include a clear warning for users who want write access.

---

## Submission Rules

1. **English documentation**: Write all `SKILL.md` configurations, guides, and comments in English.
2. **Structured format**: Follow the standard `SKILL.md` frontmatter layout (name, description, and detailed instructions).
3. **Concise and actionable**: Skills should clearly describe when and why to invoke them. Avoid vague or overly broad trigger descriptions.
4. **Review the quality checklist**: See [docs/skill-quality-checklist.md](docs/skill-quality-checklist.md) for a detailed quality standard before submitting.

---

## How to Submit

1. Fork the repository on GitHub.
2. Clone your fork locally and create a new feature branch.
3. Add your skill in `skills/<skill-name>/SKILL.md`.
4. Stage and commit your changes with a clear description.
5. Open a Pull Request pointing to the `main` branch of `tmolavi/antigravity-awesome-skills`.
