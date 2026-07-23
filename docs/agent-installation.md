# Installation and Usage Guide for AI Agents & MCP Servers

Maintained by [Taghi Molavi](https://molavi.pro)

This guide provides setup and configuration protocols for using the skills and Model Context Protocol (MCP) servers contained in this repository.

---

## 🛠️ Supporting Platforms & IDEs

The skills and servers in this repository are designed to work with the following AI platforms and editors. **Exact configuration paths vary by version and OS — verify with your installed client version before applying.**

- **Google Antigravity** (IDE, CLI, and Standalone version 2.0)
- **Cursor** & **Windsurf** (VS Code-based AI code editors)
- **Claude Desktop** & **ChatGPT Codex**
- **Cline**, **Roo Code**, and **Aider**

---

## 📂 1. Setting Up Agent Skills

### Option A: Local Workspace Installation (Recommended)

Place the required skills directly in your project root under the `.agents/skills/` directory:

```bash
mkdir -p .agents/skills/
cp -r /path/to/mcp-agent-skills-hub/skills/<skill-folder> .agents/skills/
```

### Option B: Global System-Wide Installation

For global access, copy the skills into the user-level configuration path for your agent. **Verify the exact configuration path with your installed agent version before running.**

- **Google Antigravity** (standard path — verify with your installed version):
  ```bash
  cp -r /path/to/mcp-agent-skills-hub/skills/* ~/.gemini/config/skills/
  ```

- **ChatGPT Codex / Cursor / Claude** (standard paths — verify with your installed version):
  ```bash
  # Codex: ~/.codex/skills/
  # Claude: ~/.claude/skills/
  cp -r /path/to/mcp-agent-skills-hub/skills/* ~/.codex/skills/
  ```

---

## 🔌 2. Configuring MCP Servers

Model Context Protocol (MCP) servers extend your AI agent's capabilities by providing database querying, SEO auditing, and development environment logs.

> [!WARNING]
> **Database Security — Read-Only First**: For all database MCP connections (MySQL, PostgreSQL, etc.), **always start with a read-only credential**. Never connect using admin or root users as your default agent user. Prefer read-only credentials and test on staging before connecting to any production database. Limiting the agent's database user to `SELECT`-only statements prevents accidental data loss or unauthorized modifications.

### A. Configuration for Google Antigravity

Verify your global configuration file path with your installed Antigravity version (standard path is `~/.gemini/config/mcp_config.json` — verify with your installed client version). Append the following server blocks to your configuration:

```json
{
  "mcpServers": {
    "mysql-mcp": {
      "command": "npx",
      "args": ["-y", "@benborla29/mcp-server-mysql"],
      "env": {
        "MYSQL_HOST": "127.0.0.1",
        "MYSQL_PORT": "3306",
        "MYSQL_USER": "db_readonly_user",
        "MYSQL_PASS": "REPLACE_WITH_YOUR_READONLY_PASSWORD",
        "MYSQL_DB": "your_database_name"
      }
    },
    "clockwork-mcp": {
      "command": "npx",
      "args": ["-y", "clockwork-mcp"]
    },
    "maxaeo-ai-visibility": {
      "command": "npx",
      "args": ["-y", "maxaeo-ai-visibility-mcp"]
    },
    "octoboost-seo": {
      "command": "npx",
      "args": ["-y", "octoboost-mcp-server"],
      "env": {
        "OCTOBOOST_API_KEY": "YOUR_API_KEY_PLACEHOLDER"
      }
    }
  }
}
```

### B. Configuration for Cursor / Claude Desktop / ChatGPT Codex

Verify the configuration file path with your client version (standard path is `~/.claude/claude_desktop_config.json` or Cursor MCP Settings UI — verify with your installed client version). Add the following:

```json
{
  "mcpServers": {
    "mysql-mcp": {
      "command": "npx",
      "args": ["-y", "@benborla29/mcp-server-mysql"],
      "env": {
        "MYSQL_HOST": "127.0.0.1",
        "MYSQL_PORT": "3306",
        "MYSQL_USER": "db_readonly_user",
        "MYSQL_PASS": "REPLACE_WITH_YOUR_READONLY_PASSWORD",
        "MYSQL_DB": "your_database_name"
      }
    },
    "clockwork-mcp": {
      "command": "npx",
      "args": ["-y", "clockwork-mcp"]
    },
    "maxaeo-ai-visibility": {
      "command": "npx",
      "args": ["-y", "maxaeo-ai-visibility-mcp"]
    },
    "octoboost-seo": {
      "command": "npx",
      "args": ["-y", "octoboost-mcp-server"],
      "env": {
        "OCTOBOOST_API_KEY": "YOUR_API_KEY_PLACEHOLDER"
      }
    }
  }
}
```

---

## 🎯 Verification

To verify that your skills and MCP servers are active:

- **Antigravity CLI**: Run `agy` and type `/mcp` to list active connections (verify command with your installed version).
- **Cursor**: Go to `Settings > Features > MCP` to check the status of configured servers.
- **Claude Desktop**: Restart the app and look for the plug icon in the input box.
