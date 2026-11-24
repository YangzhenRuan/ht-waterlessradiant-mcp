# HT MCP server

[![HT MCP connector](https://glama.ai/mcp/connectors/com.waterlessradiant/site/badges/score.svg)](https://glama.ai/mcp/connectors/com.waterlessradiant/site)

**Answers questions on waterless heat-pump radiant floor heating and cooling for US builders, architects, HVAC contractors and developers.**

A free, public [MCP](https://modelcontextprotocol.io) server from [HT](https://waterlessradiant.com?utm_source=github&utm_medium=readme&utm_campaign=mcp): **HT Waterless Radiant Heating Reference**. Connect it to ChatGPT, Claude or another AI assistant and it answers from HT's published guides and articles, citing the page each answer comes from.

```
https://waterlessradiant.com/mcp
```

No sign-in, no API key, nothing to install. Listed in the [official MCP Registry](https://registry.modelcontextprotocol.io/v0.1/servers?search=com.waterlessradiant%2Fsite) as `com.waterlessradiant/site`.

## What you can ask

- "What's the difference between a waterless refrigerant-direct radiant floor and a hydronic or air-to-water radiant system for a new custom home?"
- "Will heat-pump radiant floor heating keep up at -15°F in a Minnesota winter, or do I need a backup?"
- "I'm pouring a 2,400 sq ft slab next month. What do I need to plan for radiant heat before the pour?"
- "Can a waterless radiant floor also cool the house in summer and provide domestic hot water?"
- "What drives the install and running cost of heat-pump radiant floors compared with electric floor heat for a 1,800 sq ft retrofit?"
- "What happens if copper capillary tubing in a radiant floor leaks or the system sits in a freezing, unheated house?"

## Tools

| Tool | What it does |
|---|---|
| `about_site` | Start here: what waterless (refrigerant-direct) radiant floor heating and cooling database covers (Waterless (refrigerant-direct) vs hydronic radiant floors, Cold-climate heat pumps for radiant heating and cooling, Radiant floor cooling and optional domestic hot water, Radiant heat in concrete slabs: design before the pour, Radiant floor retrofits and whole-floor renovations, Radiant floor installation and lifecycle cost factors, Radiant floor leaks, freezing and common problems, Installer partner program, zoning and controls), who it is for (Custom home builders, architects, HVAC and radiant contractors, and developers planning radiant heating in the US), and its free calculators. |
| `search_site` | Search waterless (refrigerant-direct) radiant floor heating and cooling library: Waterless (refrigerant-direct) vs hydronic radiant floors, Cold-climate heat pumps for radiant heating and cooling, Radiant floor cooling and optional domestic hot water, Radiant heat in concrete slabs: design before the pour, Radiant floor retrofits and whole-floor renovations, Radiant floor installation and lifecycle cost factors, Radiant floor leaks, freezing and common problems, Installer partner program, zoning and controls. |
| `read_page` | The full text of one HT page: an article, guide, FAQ page or calculator page. |
| `ask_expert` | A question still open? With your OK, your name and email, the assistant sends it to HT's specialists, and a person replies by email. |

Every tool only reads HT's published pages, except `ask_expert`, which sends only what you approve.

## Connect it

**Claude** (claude.ai and desktop, every plan; Free allows one custom connector): Customize > Connectors > **+ Add** > **Add custom connector**. Name it, paste `https://waterlessradiant.com/mcp`, choose **No sign in**, then **Add**. In a chat: **+** > Connectors, switch it on. ([Claude help](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp))

**ChatGPT** (Pro, Business, Enterprise, Edu; web): **Plugins** > **+** > **Add custom MCP server**. Name it, paste the URL under Connection, accept the notice, **Create as a plugin**. In a new chat type **@** and pick it. ([OpenAI help](https://help.openai.com/en/articles/12584461))

**Claude Code**:
```bash
claude mcp add --transport http ht-waterlessradiant https://waterlessradiant.com/mcp
```
Or clone this repo: its `.mcp.json` connects it for the project.

**Cursor** (`~/.cursor/mcp.json`):
```json
{ "mcpServers": { "ht-waterlessradiant": { "url": "https://waterlessradiant.com/mcp" } } }
```

**VS Code (GitHub Copilot)**: Command Palette > **MCP: Add Server** > HTTP > paste the URL.

**Gemini CLI**:
```bash
gemini mcp add --transport http ht-waterlessradiant https://waterlessradiant.com/mcp
```

## Try it without an AI

```bash
curl -s https://waterlessradiant.com/mcp -H 'content-type: application/json' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call","params":{"name":"search_site","arguments":{"query":"waterless vs hydronic radiant"}}}'
```

## More from HT

- Website: [waterlessradiant.com](https://waterlessradiant.com?utm_source=github&utm_medium=readme&utm_campaign=mcp)
- Questions: [waterlessradiant.com/contact](https://waterlessradiant.com/contact?utm_source=github&utm_medium=readme&utm_campaign=mcp)

Answers are general information from HT's published pages.

## License

This repository (README and config) is MIT licensed. The server is operated by HT.
