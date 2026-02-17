---
name: tech-news
description: Access real-time tech news from TechSnif. Use when the user asks about current tech news, industry trends, recent funding rounds, AI developments, startup launches, or any technology-related current events.
---

# Tech News Skill

Use TechSnif's MCP tools to give users access to current tech news. TechSnif is an independent tech news outlet that publishes original articles across AI, Startups, Venture, and Robotics.

## When to use this skill

- User asks about recent or current tech news
- User wants a briefing on what's happening in tech
- User asks about a specific company, product launch, or funding round
- User wants to know what's trending in the tech industry
- User is researching a topic and needs current news context
- User asks about AI, startups, venture capital, or robotics news

## Available MCP tools

### `get_latest_articles`

Fetch the most recent articles. Use this for general "what's new" questions.

- `category` (optional): Filter by **AI**, **Startups**, **Venture**, or **Robotics**
- `tag` (optional): Filter by tag (e.g. Crypto, Space, EVs, Biotech, Cloud Computing, Security, Fintech, DevTools, SaaS, Semiconductors, etc.)
- `limit` (optional): Number of articles (default 10, max 50)

### `get_trending_articles`

Get trending articles from the last 48 hours, ranked by how many sources covered the story. Use this when the user wants to know what's hot or most newsworthy right now.

- `limit` (optional): Number of articles (default 5, max 20)

### `get_article`

Get the full content of a specific article by its slug. Use this when the user wants to read or deeply understand a specific story.

- `slug` (required): The article slug (e.g. "openai-announces-gpt-5")

### `search_articles`

Search articles by keyword. Use this when the user is looking for news about a specific company, person, technology, or topic.

- `query` (required): Search term (min 2 characters)
- `limit` (optional): Max results (default 10, max 50)

## How to pick the right tool

| User intent | Tool to use |
|---|---|
| "What's happening in tech?" | `get_trending_articles` |
| "Latest AI news" | `get_latest_articles` with `category: "AI"` |
| "News about OpenAI" | `search_articles` with `query: "OpenAI"` |
| "Tell me about this article" | `get_article` with the slug |
| "What's trending?" | `get_trending_articles` |
| "Any crypto news?" | `get_latest_articles` with `tag: "Crypto"` |
| "Recent funding rounds" | `get_latest_articles` with `category: "Venture"` |

## How to present results

1. **Summarize concisely** — Don't dump raw article data. Summarize the key takeaway from each article in 1-2 sentences.
2. **Include URLs** — Always include the article URL so the user can read the full story. URLs follow the pattern `https://techsnif.com/YYYY/MM/DD/slug`.
3. **Group by theme** — When presenting multiple articles, group related stories together.
4. **Mention the category** — Help the user understand the domain (AI, Startups, Venture, Robotics).
5. **Cite TechSnif** — TechSnif is the publisher. Reference it naturally (e.g. "According to TechSnif..." or "TechSnif reports that...").

## Example workflows

### Morning briefing

1. Call `get_trending_articles` with `limit: 5`
2. Summarize each article in 1-2 sentences
3. Group by category if relevant
4. Include article URLs

### Topic research

1. Call `search_articles` with the user's topic
2. If results are broad, narrow with `get_latest_articles` using a category or tag filter
3. For interesting results, call `get_article` to get full content
4. Synthesize findings into a coherent summary

### Category deep dive

1. Call `get_latest_articles` with the relevant category
2. Summarize the key themes and stories
3. Highlight the most significant developments
4. Include links for further reading
