# Ultra Prompt — MCP Server

> Ultra Prompt (ultraprompt.co) is an MCP server that gives any MCP client (Claude, Cursor, ChatGPT, or a custom agent) a library of 1,000+ professionally engineered prompt templates with typed fields and structured outputs.

**Your prompt library, inside your AI.** Instead of copy-pasting prompts, your assistant searches the library, reads a template's typed fields, collects the values from you, and assembles a finished, ready-to-run prompt — search, assemble, apply reasoning frameworks, and save reusable workflows, without leaving your client. It is the prompt layer, not a model wrapper: your AI stays the answer engine; Ultra Prompt makes its input expert-grade.

> This repo is just the connection manifest. The server is a hosted remote MCP server (Streamable HTTP) — there's nothing to install or run.

## Get connected (60 seconds)

1. **Create a free account** at [ultraprompt.co](https://ultraprompt.co).
2. **Generate your key:** Account → **MCP Server** → Generate. (Docs: [ultraprompt.co/mcp](https://ultraprompt.co/mcp))
3. **Add it to your client.** Same endpoint and key everywhere: `https://up-mcp.unpluggedfeed.workers.dev`, header `Authorization: Bearer YOUR_KEY`.

### Cursor

Set the `ULTRAPROMPT_API_KEY` environment variable to your key, then add this to `.cursor/mcp.json` (or use the [`.mcp.json`](.mcp.json) in this repo):

```json
{
  "mcpServers": {
    "ultra-prompt": {
      "url": "https://up-mcp.unpluggedfeed.workers.dev",
      "headers": { "Authorization": "Bearer ${env:ULTRAPROMPT_API_KEY}" }
    }
  }
}
```

### Claude Code

```bash
claude mcp add --transport http ultraprompt https://up-mcp.unpluggedfeed.workers.dev -H "Authorization: Bearer YOUR_KEY"
```

### Claude Desktop / claude.ai

Settings → Connectors → Add custom connector, then enter:

```
URL:     https://up-mcp.unpluggedfeed.workers.dev
Header:  Authorization: Bearer YOUR_KEY
```

### ChatGPT and other MCP clients

Any client that supports remote (HTTP / Streamable) MCP servers uses the same two values above.

## What your assistant can do

| Tool | What it does |
|---|---|
| `search_templates` | Find the right template across 1,000+ professionally engineered prompts |
| `get_template` | Read a template's fields so the AI knows what to ask you |
| `build_prompt` | Assemble the finished, ready-to-run prompt |
| `suggest_vocab` | Curated, expert vocabulary for any field |
| `recommend_next` | The natural next templates in your workflow |
| `list_enhancements` | The Pro upgrades for `build_prompt` |
| `build_pipeline` *(Pro)* | Chain templates into one multi-step mega-prompt |
| `save_playbook` *(Pro)* | Save a workflow to your account, ready to run |

**Pro** also unlocks reasoning **frameworks** (RTCEE, CO-STAR, RACE, RISEN, APE, BROKE), quality guards, and output formats on `build_prompt`.

## Typical flow

1. `search_templates` to find a template for your task.
2. `get_template` to read its fields.
3. Give the values (use `suggest_vocab` if you are unsure what to enter).
4. `build_prompt` to assemble the finished prompt.
5. `recommend_next` for the natural next step.

## Pricing

- **Free** (any account): 5 tool-calls / month, no card.
- **Pro** ($5/mo): unlimited, plus frameworks, pipelines, and playbooks.
- **Business Hub:** 10 industry vertical libraries (Real Estate, Insurance, Financial Advisors, Marketing Agencies, Law Firms, Healthcare, Staffing Agencies, Restaurants, Retail, Contractors & Trades) unlock on Business Hub keys. Free and Pro keys keep the full general library (40+ categories).

## Links

- **Docs & setup:** [ultraprompt.co/mcp](https://ultraprompt.co/mcp)
- **Get a key:** [ultraprompt.co/account](https://ultraprompt.co/account)
- **Ultra Prompt:** [ultraprompt.co](https://ultraprompt.co)

_Built with Ultra Prompt — ultraprompt.co_
