# PAI Gateways

Unified Cloudflare Workers edge layer: **api-gateway** (Hono middleware/routes) + **mcp** (MCP server). One TypeScript repo, one CI.

## Workers

| Worker | Entry | Wrangler | Purpose |
|--------|-------|----------|---------|
| api-gateway | `src/gateway/index.ts` | `wrangler.gateway.jsonc` | Hono API with auth, rate-limit, cache, skills, payments routes |
| mcp | `src/mcp/index.ts` | `wrangler.mcp.jsonc` | Model Context Protocol server (al-mizan worker) |

## Scripts

```bash
npm ci
npm run typecheck
npm run test
npm run dev:gateway   # wrangler dev -c wrangler.gateway.jsonc
npm run dev:mcp       # wrangler dev -c wrangler.mcp.jsonc
npm run deploy:gateway
npm run deploy:mcp
```

## Merged from

- [`pai-list/pai-api-gateway`](https://github.com/pai-list/pai-api-gateway) (archived)
- [`pai-list/pai-mcp`](https://github.com/pai-list/pai-mcp) (archived)

**PiWorker** (sovereign Go+TS+Docker monorepo, 241 files) remains separate.
