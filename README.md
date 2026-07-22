# Molavi Agent Skills: Curated Skills for Antigravity, Codex, Cursor & Claude

Maintained by [Taghi Molavi](https://molavi.pro) · [GitHub](https://github.com/tmolavi/antigravity-awesome-skills)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![GitHub License](https://img.shields.io/github/license/tmolavi/antigravity-awesome-skills)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/tmolavi/antigravity-awesome-skills)](https://github.com/tmolavi/antigravity-awesome-skills/stargazers)

A curated, practical collection of agent skills and MCP setup patterns for real-world web, database, SEO, and DevOps work.

---

## ❓ What is this?

In the era of autonomous software development, AI coding agents need structured domain knowledge and safe tool access. **Molavi Agent Skills** is a community-curated repository that packages:

- **277 unique, deduplicated agent skills** (formatted as `SKILL.md` configurations).
- **Model Context Protocol (MCP)** server configurations for database, performance, and SEO integrations.
- **Token & Context Optimization Guidelines** to reduce LLM token overhead and improve response times.

---

## 💡 Why this repository exists

Most agentic skill collections focus on feature coverage. This one focuses on three practical concerns:

1. **Safer MCP usage** — database MCP configs default to read-only credentials; destructive defaults are explicitly flagged.
2. **Token & context discipline** — guidelines for range reads, AST-first search, and precise diffs to keep agent sessions efficient.
3. **Practical agent workflows** — skills are written to be triggered, not just read. Each includes a clear description of when and why to invoke it.

---

## 👥 Who is it for?

This repository is designed for developers, DevOps engineers, and AI practitioners using modern agentic coding assistants:

- **IDE Users**: Cursor, Windsurf, VS Code (via Cline/Roo Code).
- **CLI & Autonomous Environments**: Google Antigravity (IDE, CLI, Standalone 2.0).
- **Chat Clients**: Claude Desktop and ChatGPT Codex.

---

## 📂 What is included?

```
├── README.md                          # Primary index & documentation
├── llms.txt                           # Structural summary for AI crawlers & LLM indexers
├── SECURITY.md                        # Vulnerability reporting & safety policy
├── CONTRIBUTING.md                    # Submission guidelines for new skills
├── CHANGELOG.md                       # Project history logs
├── docs/
│   ├── token-optimization.md          # Token & context optimization patterns
│   ├── agent-installation.md          # Local/global installation and MCP config guides
│   └── skill-quality-checklist.md     # Checklist for contributors adding new skills
└── skills/                            # 277 curated Agent Skills grouped by category
```

### Curated Skill Categories

1. **Web & Frontend**: Next.js 15, React 19, Tailwind CSS, SvelteKit, Astro, Inertia.js (SSR).
2. **Backend & Databases**: Node.js & NestJS, Python (FastAPI), PHP (Laravel 13), Go, Rust, MySQL, PostgreSQL.
3. **DevOps & Cloud**: Docker (multi-stage), Terraform (AWS/GCP/Azure), GitHub Actions.
4. **AI & Integrations**: OpenAI, Claude, Gemini API, RAG setups, Vector databases.
5. **SEO, AEO & GEO**: Technical SEO audits, AEO microcopy, GEO citation analysis.

---

## ⚡ Installation

To install these skills locally in your project workspace:

```bash
mkdir -p .agents/skills/
cp -r skills/<skill-name> .agents/skills/
```

For complete configuration instructions (including setting up local/remote MCP servers), read the [Agent Installation Guide](docs/agent-installation.md).

---

## 🛡️ Safety Notes

- **Read-Only Database Access**: For database MCP connections (like MySQL/PostgreSQL), always use read-only credentials. Never use admin or root users in your configurations.
- **Verification First**: Always review the contents of `SKILL.md` and related scripts before installing a skill in a production environment.
- **Quality Standards**: Before contributing a new skill, review the [Skill Quality Checklist](docs/skill-quality-checklist.md).
- For security vulnerability reporting, read [SECURITY.md](SECURITY.md).

---

## 🤝 Contributing

Contributions to improve and expand these skills are welcome! Please read the [CONTRIBUTING.md](CONTRIBUTING.md) guide before opening a Pull Request. All contributions are credited under the **Taghi Molavi Antigravity Ecosystem**.

---

## 📄 License

This repository is open-sourced under the MIT License. See the [LICENSE](LICENSE) file for details.
