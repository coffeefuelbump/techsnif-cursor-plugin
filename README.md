# TechSnif Plugin for Cursor

Access real-time tech news from [TechSnif](https://techsnif.com) inside Cursor. Search articles, read full stories, and get trending tech news — all without leaving your editor.

## What's included

| Component | Description |
|---|---|
| **MCP Server** | Connects Cursor to TechSnif's live news feed via [`@techsnif/mcp-server`](https://www.npmjs.com/package/@techsnif/mcp-server) |
| **Tech News Skill** | Teaches the agent how to fetch, summarize, and present tech news effectively |
| **Writing Style Rules** | TechSnif's editorial style guide for headlines and news summaries |

## What you can do

Once installed, ask Cursor things like:

- "What's trending in tech right now?"
- "Latest AI news from TechSnif"
- "Search TechSnif for articles about OpenAI"
- "Give me a morning tech news briefing"
- "What's the latest in venture capital?"
- "Read the full article about [topic]"

## Tools

The MCP server exposes four tools:

| Tool | Description |
|---|---|
| `get_latest_articles` | Latest articles, optionally filtered by category or tag |
| `get_article` | Full article content by slug |
| `get_trending_articles` | Trending articles from the last 48 hours |
| `search_articles` | Search articles by keyword |

## Categories

- **AI** — Artificial intelligence and machine learning
- **Startups** — Tech startup news across every stage and industry
- **Venture** — Venture capital, funding rounds, IPOs, and investment trends
- **Robotics** — Robotics, automation, and autonomous systems

## Tags

Crypto, Space, EVs, Biotech, Cloud Computing, Hardware, Privacy, Social Media, Transportation, Fundraising, Commerce, Government, Media, Semiconductors, Wearables, Drones, Quantum Computing, SaaS, DevTools, Data, Apps, Security, Gadgets, Fintech, Open Source

## Manual setup

If you prefer to set up the MCP server manually instead of using the plugin, add this to `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "TechSnif": {
      "command": "npx",
      "args": ["-y", "@techsnif/mcp-server"]
    }
  }
}
```

No API keys required. The server runs locally and fetches from TechSnif's public API.

## Learn more

- [TechSnif MCP setup page](https://techsnif.com/mcp)
- [`@techsnif/mcp-server` on npm](https://www.npmjs.com/package/@techsnif/mcp-server)
- [TechSnif](https://techsnif.com)

## License

MIT
