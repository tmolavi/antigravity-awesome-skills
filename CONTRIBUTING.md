# Contributing to Molavi Agent Skills

Thank you for your interest in contributing to **Molavi Agent Skills**! This repository is a curated collection of high-performance agent skills and Model Context Protocol (MCP) server configurations designed to make AI coding assistants (Google Antigravity, Cursor, Windsurf, Claude, and ChatGPT Codex) smarter, safer, and more efficient.

We welcome contributions of new skills, improvements to existing skills, and updates to documentation. To maintain high-quality standards, security, and format consistency across the ecosystem, please review and follow this guide.

---

## 🛡️ Safety & Quality Principles

Before writing or submitting a skill, make sure you align with our core principles:

1. **Safety First**: Skills must never run destructive commands by default (e.g., `DROP TABLE`, `rm -rf`, or deleting user configs without confirmation). Database and filesystem operations must prioritize read-only mode.
2. **No Secrets**: Never commit real credentials, API keys, passwords, database URLs, or private system paths. Use generic placeholders (e.g., `YOUR_API_KEY_PLACEHOLDER`, `db_readonly_user`).
3. **Trigger-Focused**: A skill should clearly declare its triggering criteria so that an AI agent knows exactly *when* and *why* to load it.
4. **Actionable & Practical**: Avoid general theory. AI agents need concrete commands, file layout patterns, error resolution steps, and architectural constraints.

---

## 📂 The `.skill` (SKILL.md) Format

Every skill in this repository is stored in its own folder: `skills/<skill-name>/SKILL.md`. 
The file uses a **Markdown format with a YAML frontmatter block** at the very top. AI agents read the YAML frontmatter to index the skill, map triggers, and determine scope.

### YAML Frontmatter Template

```yaml
---
name: skill-name-identifier
description: "A clear, 1-2 sentence explanation of what this skill does and when the agent should trigger it."
category: web-development / backend / database / devops / ai-integrations / seo-aeo-geo
risk: safe / medium / high
source: community / official
date_added: "YYYY-MM-DD"
author: github-username
tags: [tag1, tag2, tag3]
tools: [antigravity, claude, cursor, codex]
---
```

### Markdown Content Structure

After the YAML frontmatter block, your `SKILL.md` must contain structured markdown content. We recommend using the following standard sections:

1. **`# Skill Title`**: Human-readable name of the skill.
2. **`## Overview`**: A brief background context of the technology, tool, or protocol.
3. **`## When to Use This Skill`**: Bullet points explicitly telling the AI agent when to trigger/load this skill.
4. **`## How It Works / Implementation Steps`**: Step-by-step instructions, standard configurations, commands, directory structures, and code patterns.
5. **`## Verification & Testing`**: How the agent or user should verify the implementation (e.g., test commands, verification endpoints).
6. **`## Common Pitfalls & Solutions`**: Troubleshooting guidelines, common errors, and how to resolve them.

---

## 📝 Example of a Complete SKILL.md

Here is a simple reference template:

```markdown
---
name: nextjs-caching
description: "Optimizes caching and data revalidation strategies for Next.js App Router applications."
category: web-development
risk: safe
source: community
date_added: "2026-07-23"
author: tmolavi
tags: [nextjs, caching, performance, revalidate, fetch]
tools: [antigravity, cursor, claude]
---

# Next.js Caching Best Practices

## Overview
Next.js features a powerful data cache and router cache system to improve web application speed. Correct usage of revalidation ensures data freshness without redundant network overhead.

## When to Use This Skill
- Use when configuring fetch requests in Next.js App Router projects.
- Use when designing cache invalidation, ISR (Incremental Static Regeneration), or dynamic routes.
- Use when troubleshooting stale data issues or un-cached API calls.

## How It Works

### 1. Static Fetch Cache (Default)
By default, fetch requests are cached automatically:
```javascript
// Caches forever until revalidated
const res = await fetch('https://api.example.com/data');
```

### 2. Time-Based Revalidation
Specify a revalidation interval in seconds:
```javascript
const res = await fetch('https://api.example.com/data', {
  next: { revalidate: 3600 } // Revalidate every hour
});
```

## Verification & Testing
1. Run `npm run build` and observe the route types (Static `○` vs. Dynamic `λ`).
2. Inspect the network response headers for `x-nextjs-cache` (should show `HIT` or `MISS`).
```

---

## 🤝 Contribution Process

Ready to submit? Follow these steps:

1. **Fork the Repository**: Create a fork of [tmolavi/antigravity-awesome-skills](https://github.com/tmolavi/antigravity-awesome-skills).
2. **Create a Branch**: Create a new branch for your skill (e.g., `feature/add-my-skill`).
3. **Check for Duplicates**: Ensure a similar skill does not already exist in the `skills/` directory.
4. **Add the Folder & SKILL.md**:
   - Create a folder: `skills/<my-new-skill>/`
   - Add your `SKILL.md` inside that folder.
   - Run the Pre-PR Checklist to verify quality.
5. **Update the Main Directory (Optional)**: If you'd like, you can run a script or check that your skill matches standard naming conventions.
6. **Commit & Push**: Commit your changes with a descriptive message (e.g., `feat: add nextjs-caching skill`).
7. **Open a Pull Request**: Submit a PR to the `main` branch of our repository.
