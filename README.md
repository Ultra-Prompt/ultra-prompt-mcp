# Ultra Prompt — MCP Server

**Your prompt library, inside your AI.** Connect Ultra Prompt to Cursor (or any MCP client)
and your assistant can build professional, Ultra Prompt-grade prompts from **1,000+
templates** — search the library, assemble finished prompts, apply reasoning frameworks,
and save reusable workflows — without leaving your editor.

> This repo is just the connection manifest. The server is a hosted remote MCP server
> (Streamable HTTP) — there's nothing to install or run.

## Get connected (60 seconds)

1. **Create a free account** at [ultraprompt.co](https://ultraprompt.co).
2. **Generate your key:** Account → **MCP Server** → Generate. (Docs: [ultraprompt.co/mcp](https://ultraprompt.co/mcp))
3. **Add it to Cursor** — set the `ULTRAPROMPT_API_KEY` environment variable to your key, then add this to your `.cursor/mcp.json` (or use the [`.mcp.json`](.mcp.json) in this repo):

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

**Pro** also unlocks reasoning **frameworks** (RTCEE, CO-STAR, RACE, RISEN, APE, BROKE),
quality guards, and output formats on `build_prompt`.

## Pricing

- **Free** (any account): 5 tool-calls / month
- **Pro:** unlimited + frameworks, pipelines, and playbooks

## Links

- **Docs & setup:** [ultraprompt.co/mcp](https://ultraprompt.co/mcp)
- **Ultra Prompt:** [ultraprompt.co](https://ultraprompt.co)

_Built with Ultra Prompt — ultraprompt.co_
