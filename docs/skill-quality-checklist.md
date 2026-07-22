# Skill Quality Checklist

Maintained by [Taghi Molavi](https://molavi.pro)

Use this checklist before submitting a new skill to the **Molavi Agent Skills** repository, or when reviewing an existing skill for quality and safety.

---

## ✅ Trigger & Purpose

- [ ] The `description` in the frontmatter clearly states **when and why** the skill should be invoked.
- [ ] The trigger condition is specific enough to avoid false positives (the agent should not accidentally invoke this skill in unrelated contexts).
- [ ] The skill does not duplicate an existing skill in the `skills/` directory.

---

## ✅ Safety & Security

- [ ] **No secrets**: No real API keys, passwords, tokens, or credentials are present. All sensitive values use clearly labeled placeholders.
- [ ] **No local private paths**: No absolute file paths specific to a local machine (e.g., `/Users/yourname/...`).
- [ ] **No destructive defaults**: Commands that modify, delete, or drop data require explicit user confirmation. Destructive operations (e.g., `DROP TABLE`, `rm -rf`, `DELETE FROM`) are never the default action.
- [ ] **MCP/database skills**: If the skill configures a database or file system MCP connection, the default credential must be read-only. Write access requires an explicit, clearly labeled opt-in by the user.
- [ ] **External requests**: If the skill instructs the agent to send data to an external endpoint, this is documented clearly and the purpose is benign and user-approved.

---

## ✅ Instructions Quality

- [ ] Instructions are written in clear, plain English.
- [ ] Instructions are concise — no unnecessary filler text or generic advice.
- [ ] References (external documentation, other skills) are included only when they add genuine value.
- [ ] If the skill was adapted from another source, attribution is included in a `## Source` or `## Credits` section.

---

## ✅ Installation & Testing

- [ ] The skill has been manually tested (or reviewed) in at least one of the supported environments: Antigravity, Cursor, Claude Desktop, or ChatGPT Codex.
- [ ] Any setup steps are documented clearly, including dependencies or configuration requirements.
- [ ] The `SKILL.md` file lives in its own named subdirectory: `skills/<skill-name>/SKILL.md`.

---

## ✅ MCP / Database Skills (additional review)

Applies only to skills that configure or use Model Context Protocol servers:

- [ ] Default database user is **read-only** (SELECT-only permissions).
- [ ] A warning is present if the skill could modify or delete data.
- [ ] Configuration examples use placeholder values, not real connection strings.
- [ ] The skill recommends testing on a staging environment before connecting to production.
