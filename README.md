# MCP Experimental Lab

A collection of structured experiments, tools, and prototypes using Model Context Protocol (MCP). This repository showcases integrations, custom toolchains, and real-world use cases for MCP-based systems.

---

## Installing & Running Claude Desktop on Linux

Since Anthropic doesn’t officially support a native Claude desktop app, most people use web wrappers or Electron apps to create a desktop experience. Here's how you can do it using included shell script:

```bash
chmod +x install_debian_claude.sh
./install_debian_claude.sh
```

---

## Configure Claude to Use Local MCP Servers

After installing Claude Desktop, configure it to recognize your local tools:

### Step 2: Open the Configuration File

```bash
code ~/Library/Application\ Support/Claude/claude_desktop_config.json
```

> 💡 _This file controls which MCP servers Claude can access locally._

### Step 3: Add Your MCP Server(s)

Example configuration for a weather tool:

\`\`\`json
{
  "mcpServers": {
    "weather": {
      "command": "uv",
      "args": [
        "--directory", "/ABSOLUTE_PATH/TO/PARENT/FOLDER/weather",
        "run", "weather.py"
      ]
    }
  }
}
\`\`\`

> ⚠️ Replace `/ABSOLUTE_PATH/TO/PARENT/FOLDER/weather` with the actual absolute path on your system where you have your tools configured.

---

That’s it! Now when Claude launches, it will auto-start your MCP server(s) as needed and allow you to chat with your tools seamlessly.
