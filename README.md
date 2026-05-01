# code-code-console

Console BFF, console web UI, and showcase-facing application surfaces for Code Code.

This repository owns:

- `packages/console-api`: aggregate copy of console HTTP/BFF services and the current chat service implementation.
- `packages/console-web`: aggregate copy of React console and showcase web workspaces.
- `packages/showcase-api`: aggregate copy of showcase HTTP API.

Focused console splits now exist:

- `code-code-console-api`: console BFF and chat HTTP services.
- `code-code-console-web`: React console and showcase web workspaces.
- `code-code-showcase-api`: showcase-facing HTTP API.

This split preserves source history from the original monorepo. Contract
dependency migration is the next step: console code should consume
`code-code-contracts` through versioned Go/TypeScript packages instead of local
workspace paths.

Useful checks:

```bash
cd packages/console-api && go test ./...
cd packages/showcase-api && go test ./...
cd packages/console-web && pnpm install && pnpm typecheck
```
