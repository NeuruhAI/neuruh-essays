# How I Built an Open-Source MCP Gateway in 7 Files

7 files. Zero errors. Permission-first.

```
1. ToolInterface.ts     — standard tool schema
2. ToolRegistry.ts      — registration + discovery
3. PermissionGuard.ts   — TrustLayer access control
4. RiskClassifier.ts    — per-call risk assessment
5. BashTool.ts          — shell with allowlist
6. FileReadTool.ts      — path restrictions
7. WebFetchTool.ts      — domain filtering
```

## Request path

```
Agent → Registry → PermissionGuard → RiskClassifier → Tool → Response
```

Every tool call flows through permission and risk checks before it runs. The guard is not a layer you remember to add — it's the only path to execution.

## Design decisions

- **Permission-first** — no `if (auth)` sprinkled through handlers. Centralized TrustLayer.
- **Model-agnostic** — no hardcoded reference to any LLM provider.
- **Minimal surface** — 7 files. Readable in an hour. Forkable in a day.
- **MCP-compatible** — works with Claude Code, Cursor, and any MCP client.

## Source

[`github.com/NeuruhAI/neuruh-axon`](https://github.com/NeuruhAI/neuruh-axon) · Apache-style license in-repo.

## Roadmap

- **Phase 2** Coordinator + Memory
- **Phase 3** Prompt Composer + Cost Tracker
- **Phase 4** Adapter SDK for third-party tools
- **Phase 5** Public Gateway API

Star the repo. File an issue. Send a PR.
