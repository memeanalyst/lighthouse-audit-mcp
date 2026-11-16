# Lighthouse Audit — MCP Server

Run Google Lighthouse audits on any web page, directly from your AI agent or MCP client. Get performance, SEO, accessibility, and best-practices scores — plus the core metrics and top fixes behind them — for one URL or a whole list, on mobile or desktop.

This repo is the MCP listing for the [Lighthouse Audit](https://apify.com/magnova/lighthouse-audit) Actor by Magnova on Apify. The server is hosted by Apify at the pinned endpoint below — there is nothing to install or run from this repository; you just point your MCP client at the URL.

## Tools

The pinned connection loads a focused tool set:

- **magnova--lighthouse-audit** — Run Google Lighthouse audits. Input: one or more URLs, with mobile or desktop emulation. Returns category scores (performance, SEO, accessibility, best practices), key metrics such as LCP, CLS, and TBT, the top recommended fixes, optional performance budgets, and the score change since the previous run.
- **fetch-actor-details** — Fetch the Actor's full input schema, pricing, and documentation, so an agent can check parameters and cost before running it.
- **get-actor-run / get-dataset-items** — Run and storage helpers, loaded automatically, used to fetch the results a run produced.

## Connect

Pinned endpoint (Streamable HTTP):

```
https://mcp.apify.com?tools=fetch-actor-details,magnova/lighthouse-audit
```

On first connect, your client will ask you to sign in with your Apify account (OAuth). If your client cannot do OAuth, pass your Apify API token as an `Authorization: Bearer <YOUR_APIFY_TOKEN>` header instead.

### Cursor / VS Code / other Streamable HTTP clients

```json
{
  "mcpServers": {
    "lighthouse-audit": {
      "url": "https://mcp.apify.com?tools=fetch-actor-details,magnova/lighthouse-audit"
    }
  }
}
```

### Claude Desktop

Claude Desktop's config file only runs local commands, so use the `mcp-remote` bridge:

```json
{
  "mcpServers": {
    "lighthouse-audit": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.apify.com?tools=fetch-actor-details,magnova/lighthouse-audit"
      ]
    }
  }
}
```

The same pinned URL also lives in this repo's `.mcp.json`, and `server.json` is the listing for the Official MCP Registry, published as `io.github.memeanalyst/lighthouse-audit-mcp`.

## Pricing

Pay per event, billed to your own Apify account: **$0.02 per audit** — $20 per 1,000 audits. No start fee, no subscription, and you are only charged for audits actually delivered.

## Links

- Actor on Apify Store: https://apify.com/magnova/lighthouse-audit
- MCP endpoint: https://mcp.apify.com?tools=fetch-actor-details,magnova/lighthouse-audit
