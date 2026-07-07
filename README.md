# Welcome to Hook's Guidebook
**My Official Discord server: https://discord.gg/QmKEQXFWjf**

## 1. How to i find trusted executor list?
> Answer is, Join my discord server for trusted exploit server, if you wont trust me, try https://weao.xyz or https://inject.today or https://voxlis.net or https://pulsery.gg

## 2. Where do i learn roblox lua scripting or exploit scripting?
**Luau Learning:**
1. Basic Luau Learning: https://luau.org and https://create.roblox.com/docs and https://devforum.roblox.com/
2. Exploit Learning: https://docs.voltbz.net and https://synapsexdocs.github.io/ and https://docs.potassium.pro/api-reference/
3. Assistiants: https://deepseek.com and https://v3rm.net and https://reddit.com and https://claude.ai

**General:**
1. Github - https://github.com - reason is the best thing you can code for first time, like loadstring, basic things.
2. Gitlab - https://gitlab.com - alternative version of github
3. Visual Studio Code - https://code.visualstudio.com/ - Best for luau learning.
4. Notepad++ - https://notepad-plus-plus.org/ - Alternative but not recommended
5. Roblox Executor MVP Server - https://github.com/notpoiu/roblox-executor-mcp/ - Best one if you want ai to make your very first script

## 3. How to i find best and better script?
> Answer is directly from website. https://scriptblox.com, https://rscripts.net, https://haxhell.com/, https://robloxscripts.com/

## 4. How to i make my first script?
**Normal guide:**
1. Basic Luau Learning: https://luau.org and https://create.roblox.com/docs and https://devforum.roblox.com/
2. Exploit Learning: https://docs.voltbz.net and https://synapsexdocs.github.io/ and https://docs.potassium.pro/api-reference/
3. Github - https://github.com - the best deploy site.
4. Visual Studio Code - https://code.visualstudio.com/ - Best for luau learning.

**Script guide:**
1. Get DexPlusPlus -> https://github.com/AZYsGithub/DexPlusPlus
2. Get Cobalt RSpy -> https://github.com/notpoiu/cobalt
3. Get Roblox Executor MVP Server - https://github.com/notpoiu/roblox-executor-mcp/

## 5. How to i connect MCP Server to my executor? Made by https://github.com/notpoiu/roblox-executor-mcp/
### Tutorial:
[![roblox-executor-mcp installation guide](http://img.youtube.com/vi/Tcy5RNf1TRc/0.jpg)](https://youtube.com/watch?v=Tcy5RNf1TRc)

### Get Started

**1. Clone the server**

```bash
git clone https://github.com/notpoiu/roblox-executor-mcp.git
cd roblox-executor-mcp
```

**2. Run the harness installer**

The installer builds the server, lets you choose AI clients, writes supported MCP configs, and prints the Roblox loader script.

```bash
npm run install:harnesses
```

The picker is built with [OpenTUI](https://opentui.com/) and runs through Bun. `npm run install:harnesses` installs Bun first if it is not already available. It shows detected local clients by default; if none are detected, it warns you to install a harness first. Press `s` in the picker or pass `--show-all-harnesses` to reveal every supported config target. If your terminal has trouble with the interactive picker, use the plain numbered prompt:

```bash
npm run install:harnesses -- --plain
```

The installer can also place the Roblox loader into a detected executor autoexec folder, such as MacSploit on macOS or supported Windows executor autoexec folders. Use the prompt, or run:

```bash
npm run getscript -- --autoexec
```

It can also help with:

- cross-machine setup on the same LAN
- copying the Roblox loader to your clipboard
- optional Ollama `embeddinggemma` setup for semantic indexing
- pulling latest repo changes before install/build

To update an existing install later, run:

```bash
npm run update
```

The update command can stop currently running MCP server processes, optionally pull latest changes, and always rebuilds the server.

**3. Connect from Roblox**

The installer prints this for you. Put it in your executor or Auto Execute:

```lua
local bridgeUrl = getgenv().BridgeURL or "localhost:16384"
loadstring(game:HttpGet("http://" .. bridgeUrl .. "/script.luau"))()
```

**Optional settings** (set before the `loadstring`):

```lua
getgenv().BridgeURL = "10.0.0.4:16384"                  -- default: localhost:16384
getgenv().DisableWebSocket = true                        -- force HTTP polling
getgenv().DisableInitialScriptDecompMapping = true       -- skip initial decompilation
```

After the MCP server starts and Roblox connects, open the dashboard:

```text
http://localhost:16384/
```

# How to setup MCP Server

**Recommended, ask ai how to connect mcp server within that mcp server overlay**
```json
{
  "mcpServers": {
    "roblox-executor-mcp": {
      "command": "node",
      "args": ["/path/to/roblox-executor-mcp/dist/index.js"]
    }
  }
}
```

## Antigravity Setup

### 1. Open the MCP config

In Antigravity, open the command palette (`Ctrl+Shift+P` / `Cmd+Shift+P`) and search for **"Antigravity: Manage MCP Servers"**, or manually edit the config file:

- **macOS:** `~/.gemini/antigravity/mcp_config.json`
- **Windows:** `%USERPROFILE%\.gemini\config\mcp_config.json`
- **Linux:** `~/.gemini/antigravity/mcp_config.json`

### 2. Add the MCP server

Clock on "View raw config" button and add or merge the following:

```json
{
  "mcpServers": {
    "roblox-executor-mcp": {
      "command": "node",
      "args": ["/path/to/roblox-executor-mcp/dist/index.js"]
    }
  }
}
```

Replace `/path/to/roblox-executor-mcp` with the actual path where you cloned the repo.

### 3. Reload

Click on the "Refresh" button next to the View raw config button.

### Verify

Check that the MCP tools are available in the AI panel. If the server isn't connecting:

- Make sure you ran `pnpm install && pnpm run build` first
- Check that the path to `dist/index.js` is correct
- Ensure Node.js ≥ 18 is installed

## Claude Code (CLI) Setup

### 1. Add the MCP server

Run this command in your terminal:

```bash
claude mcp add roblox-executor-mcp -- node /path/to/roblox-executor-mcp/dist/index.js
```

Replace `/path/to/roblox-executor-mcp` with the actual path where you cloned the repo.

This adds the server to your local project config (`.claude/settings.local.json`). To add it globally instead, use:

```bash
claude mcp add --global roblox-executor-mcp -- node /path/to/roblox-executor-mcp/dist/index.js
```

### 2. Verify

Start Claude Code and run:

```
/mcp
```

You should see `roblox-executor-mcp` listed with a status of `connected`. If it shows `failed`:

- Make sure you ran `pnpm install && pnpm run build` first
- Check that the path to `dist/index.js` is correct
- Ensure Node.js ≥ 18 is installed

### Managing the server

```bash
# List configured MCP servers
claude mcp list

# Remove the server
claude mcp remove roblox-executor-mcp
```

## Claude Desktop Setup

### 1. Open the config file

- **macOS:** `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows classic:** `%APPDATA%\Claude\claude_desktop_config.json`
- **Windows MSIX:** `%LOCALAPPDATA%\Packages\Claude_pzs8sxrjxfjjc\LocalCache\Roaming\Claude\claude_desktop_config.json`

If the file doesn't exist, create it.

### 2. Add the MCP server

Add or merge the following into your config:

```json
{
  "mcpServers": {
    "roblox-mcp": {
      "command": "node",
      "args": ["/path/to/MCPServer/dist/index.js", "--server-name", "roblox-mcp"]
    }
  }
}
```

Replace `/path/to/MCPServer` with the actual path where you cloned the repo.

**Windows example:**
```json
{
  "mcpServers": {
    "roblox-mcp": {
      "command": "node",
      "args": ["C:\\Users\\YourName\\MCPServer\\dist\\index.js", "--server-name", "roblox-mcp"]
    }
  }
}
```

### 3. Restart Claude Desktop

Fully quit and reopen Claude Desktop for changes to take effect.

### Verify

Click the MCP icon (hammer) in the chat input area. You should see `roblox-mcp` listed with its tools. If it doesn't appear:

- Make sure you ran `pnpm install && pnpm run build` first
- Check that the path in the config is correct
- Ensure Node.js ≥ 18 is installed
- Check the logs at `~/Library/Logs/Claude/` (macOS) or the Claude folders under `%APPDATA%` and `%LOCALAPPDATA%\Packages\Claude_pzs8sxrjxfjjc\LocalCache\Roaming\Claude` (Windows)

## Codex Setup

### 1. Add the MCP server

Open Codex and go to **Settings** > **MCP**, then add a new server:

- **Name:** `roblox-executor-mcp`
- **Type:** `STDIO`
- **Command:** `node`
- **Args:** `/path/to/roblox-executor-mcp/dist/index.js`

Replace `/path/to/roblox-executor-mcp` with the actual path where you cloned the repo.

### 1. Open the config file

The Codex CLI config is located at `~/.codex/config.toml`. Open it in your editor.

### 2. Add the MCP server

Add the following to your `config.toml`:

```toml
[mcp_servers.roblox-executor-mcp]
command = "node"
args = ["/path/to/roblox-executor-mcp/dist/index.js"]
```

Replace `/path/to/roblox-executor-mcp` with the actual path where you cloned the repo.

### 3. Restart Codex

Restart your Codex session for the new server to connect.

### Verify

After setup, the MCP tools should appear in your Codex session. If they don't:

- Make sure you ran `pnpm install && pnpm run build` first
- Check that the path to `dist/index.js` is correct
- Ensure Node.js ≥ 18 is installed

## Cursor Setup

### Option 1: Deeplink (Quick)

Click the button below to auto-install (you'll need to update the path afterwards):

[![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/en-US/install-mcp?name=roblox-executor-mcp&config=eyJjb21tYW5kIjoibm9kZSAvcGF0aC90by9NQ1BTZXJ2ZXIvZGlzdC9pbmRleC5qcyJ9)

### Option 2: Manual

1. Open Cursor
2. Go to **Settings** > **Features** > **MCP**
3. Click **Add New MCP Server**
4. Fill in:
   - **Name:** `roblox-executor-mcp`
   - **Type:** `command`
   - **Command:** `node /path/to/roblox-executor-mcp/dist/index.js`

Replace `/path/to/roblox-executor-mcp` with the actual path where you cloned the repo.

### Option 3: JSON Config

Add this to your Cursor MCP config file (`.cursor/mcp.json` in your project or global config):

```json
{
  "mcpServers": {
    "roblox-executor-mcp": {
      "command": "node",
      "args": ["/path/to/roblox-executor-mcp/dist/index.js"]
    }
  }
}
```

### Verify

After setup, you should see `roblox-executor-mcp` listed in your MCP servers with a green status indicator. If it shows red, check that:

- You ran `pnpm install && pnpm run build` first
- The path to `dist/index.js` is correct
- Node.js ≥ 18 is installed

## Windsurf Setup

### 1. Open the MCP config

In Windsurf, open the command palette (`Ctrl+Shift+P` / `Cmd+Shift+P`) and search for **"Windsurf: Open MCP Config"**, or manually edit the config file:

- **macOS:** `~/.codeium/windsurf/mcp_config.json`
- **Windows:** `%USERPROFILE%\.codeium\windsurf\mcp_config.json`
- **Linux:** `~/.codeium/windsurf/mcp_config.json`

### 2. Add the MCP server

Add or merge the following:

```json
{
  "mcpServers": {
    "roblox-executor-mcp": {
      "command": "node",
      "args": ["/path/to/roblox-executor-mcp/dist/index.js"]
    }
  }
}
```

Replace `/path/to/roblox-executor-mcp` with the actual path where you cloned the repo.

### 3. Reload

Restart Windsurf or reload the window for the MCP server to connect.

### Verify

Open Cascade (Windsurf's AI panel) and check that the MCP tools are available. If the server isn't connecting:

- Make sure you ran `pnpm install && pnpm run build` first
- Check that the path to `dist/index.js` is correct
- Ensure Node.js ≥ 18 is installed

# MIT License: [MIT](https://github.com/hook-function/hook-help/blob/main/LICENSE)
