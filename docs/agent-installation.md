# Installation and Usage Guide for AI Agents & MCP Servers

## Compiled by Taghi Molavi (tmolavi) — [molavi.pro](https://molavi.pro)

This guide provides setup and configuration protocols for using the skills and Model Context Protocol (MCP) servers contained in this repository.

---

## 🛠️ Supporting Platforms & IDEs

The skills and servers in this repository are designed to work seamlessly with the following AI platforms and editors:
- **Google Antigravity** (IDE, CLI, and Standalone version 2.0)
- **Cursor** & **Windsurf** (VS Code-based AI code editors)
- **Claude Desktop** & **ChatGPT Codex**
- **Cline**, **Roo Code**, and **Aider**

---

## 📂 1. Setting Up Agent Skills

### Option A: Local Workspace Installation (Recommended)
Place the required skills directly in your project root under the `.agents/skills/` directory.

```bash
mkdir -p .agents/skills/
cp -r /path/to/antigravity-awesome-skills/skills/<skill-folder> .agents/skills/
```

### Option B: Global System-Wide Installation
For global access, copy the skills into the user-level configuration path for your agent. Please **verify the exact configuration path with your installed agent version** before running:

- **Google Antigravity**:
  ```bash
  # Standard path: ~/.gemini/config/skills/
  cp -r /path/to/antigravity-awesome-skills/skills/* ~/.gemini/config/skills/
  ```
- **ChatGPT Codex / Cursor / Claude**:
  ```bash
  # Standard path: ~/.codex/skills/ or ~/.claude/skills/
  cp -r /path/to/antigravity-awesome-skills/skills/* ~/.codex/skills/
  ```

---

## 🔌 2. Configuring MCP Servers

Model Context Protocol (MCP) servers extend your AI agent's capabilities by providing database querying, SEO auditing, and development environment logs directly.

> [!WARNING]
> **Database Security Priority**: For database MCP connections (like MySQL/PostgreSQL), **always use a read-only credential**. Do not connect using admin or root users. Limiting the agent's database user to SELECT-only statements prevents accidental data loss or unauthorized modifications.

### A. Configuration for Google Antigravity
Verify your global configuration file path with your installed Antigravity version (standard path is `~/.gemini/config/mcp_config.json`). Append the following server blocks to your configuration:

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
        "MYSQL_PASS": "secured_readonly_password_placeholder",
        "MYSQL_DB": "my_db_name"
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
Verify the configuration file path with your client version (standard path is `~/.claude/claude_desktop_config.json` or custom Cursor MCP Settings UI). Add the following server configuration:

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
        "MYSQL_PASS": "secured_readonly_password_placeholder",
        "MYSQL_DB": "my_db_name"
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

To verify that your skills and MCP servers are running successfully:
- **Antigravity CLI**: Run `agy` and type `/mcp` to list active connections.
- **Cursor**: Go to `Settings > Features > MCP` to check the status of configured servers.
- **Claude Desktop**: Restart the app and look for the electrical plug icon in the input box.
