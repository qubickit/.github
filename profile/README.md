# QubicKit

Tooling for the Qubic ecosystem maintained by a tiny team (currently two devs). QubicKit delivers:

- **@qubickit/core** – typed RPC clients, transport resiliency (retry/backoff, 429 handling, caching), transaction serialization, identity helpers.
- **@qubickit/sdk** – wallet/session orchestration, durable transfer queues, watchers, transport hooks.
- **@qubickit/cli** – operator-focused CLI wrapping the SDK (wallet management, diagnostics, live watchers).
- **@qubickit/web** – React helpers (WIP).

## Quick start
```bash
bun add @qubickit/core
bun add @qubickit/sdk
bun add -g @qubickit/cli
```

```ts
import { createQubicSdk } from '@qubickit/sdk';

const sdk = createQubicSdk();
const session = sdk.createSessionClient();
const watcher = session.watchBalance('BAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAARMID');
watcher.channel.subscribe((payload) => console.log('balance', payload.balance));
```

## Docs & Support
- Docs: [apps/docs](https://github.com/qubickit/qubickit/tree/main/apps/docs) (Fumadocs)
- Issues/feature requests: open a GitHub issue in this org.
- Security: email security@qubickit.dev.

Public RPC endpoints enforce ~100 req/min per IP; add your own hosts via env vars or talk to a node operator about whitelisting.

*“Install what you need, keep every layer typed and observable.”*
