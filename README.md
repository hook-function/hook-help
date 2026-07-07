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

## 5. How to i connect MCP Server to my executor?
### Get Started:
**1. Tutorial**
[![roblox-executor-mcp installation guide](http://img.youtube.com/vi/Tcy5RNf1TRc/0.jpg)](https://youtube.com/watch?v=Tcy5RNf1TRc)
**2. Quick Start**
Clone the server

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

3. Connect from Roblox

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

# MIT License: [MIT](https://github.com/hook-function/hook-help/blob/main/LICENSE)
