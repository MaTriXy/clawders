# 🔌 MCP Servers for Claude Code

MCP (Model Context Protocol) servers extend Claude Code's capabilities by connecting it to external tools and data sources.

---

## Recommended MCP Servers

### 1. n8n MCP

Connect Claude Code to your n8n workflows for automation:

```bash
/plugin marketplace add n8n-mcp-skills@n8n-mcp-skills
```

### 2. Sequential Thinking

Adds structured, step-by-step reasoning to Claude Code. After installation and a restart, the **Superpowers plugin** will also use it — but note it runs only within the folder it was initialized in, so reinitialize per project.

---

## Getting Started

1. Install the MCP server of your choice
2. Restart Claude Code
3. The server becomes available as tools Claude Code can call

For more MCP servers, check the [official Claude Code plugins marketplace](https://claudemarketplaces.com/).
