# Molavi Agent Skills: Curated Skills for Antigravity, Codex, Cursor & Claude

*Unofficial community project maintained by **Taghi Molavi (tmolavi)*** — [molavi.pro](https://molavi.pro)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![GitHub License](https://img.shields.io/github/license/tmolavi/antigravity-awesome-skills)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/tmolavi/antigravity-awesome-skills)](https://github.com/tmolavi/antigravity-awesome-skills/stargazers)

A curated, practical collection of agent skills and MCP setup patterns for real-world web, database, SEO, and DevOps work.

---

## ❓ What is this?

In the era of autonomous software development, AI coding agents must be equipped with structured domain knowledge and direct tool access. **Molavi Agent Skills** is a community-driven repository that packages:
- **277 unique, deduplicated agent skills** (formatted as `SKILL.md` configurations).
- **Model Context Protocol (MCP)** server configurations for database, performance, and SEO integrations.
- **Token & Context Optimization Guidelines** to reduce LLM token overhead and improve response times.

---

## 👥 Who is it for?

This repository is designed for developers, DevOps engineers, and AI practitioners using modern agentic coding assistants:
- **IDE Users**: Cursor, Windsurf, VS Code (via Cline/Roo Code).
- **CLI & Autonomous Environments**: Google Antigravity (IDE, CLI, Standalone 2.0).
- **Chat Clients**: Claude Desktop and ChatGPT Codex.

---

## 📂 What is included?

The repository contains the following core components:

```
├── README.md                 # Primary index & documentation
├── llms.txt                  # Structural summary for AI crawlers & LLM indexers
├── SECURITY.md               # Vulnerability reporting & safety policy
├── CONTRIBUTING.md           # Submission guidelines for new skills
├── CHANGELOG.md              # Project history logs
├── docs/
│   ├── token-optimization.md # Taghi Molavi Token Optimization Protocol
│   └── agent-installation.md # Local/global installation and MCP config guides
└── skills/                   # 277 curated Agent Skills grouped by category
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

- **Read-Only Database Access**: For database MCP connections (like MySQL/PostgreSQL), we highly recommend using read-only credentials. Never use admin or root users in your configurations.
- **Verification First**: Always review the contents of `SKILL.md` and related scripts before installing a skill in a production environment.
- For security vulnerability reporting, read our [SECURITY.md](SECURITY.md).

---

## 🤝 Contributing

Contributions to improve and expand these skills are welcome! Please read the [CONTRIBUTING.md](CONTRIBUTING.md) guide before opening a Pull Request. All contributions are credited under the **Taghi Molavi Antigravity Ecosystem**.

---

## 📄 License

This repository is open-sourced under the MIT License. See the [LICENSE](LICENSE) file for details.
