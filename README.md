# CKB Service Runner

**Run a CKB full node — and let it do more.**

CKB Service Runner is a side application you install next to a fully synced
[CKB](https://github.com/nervosnetwork/ckb) full node. It gives node operators a
dashboard for their node, a public node ranking, and — later — a sandboxed
runtime that executes decentralised services published as cells on CKB.

> **Status: concept / pre-alpha. Testnet only. No release yet.**
> The design is open for discussion — see [Discussions](../../discussions).

---

## Why

CKB full nodes are run by volunteers at their own cost. At the same time,
many applications need things a smart contract alone can't do: hold a secret
and delete it on time, watch the chain, keep data, sign attestations.

CKB Service Runner aims to be a platform where **independent full nodes provide
those services to truly decentralised applications** — a win for users,
developers, the CKB network and node operators. Fees for operators are a
by-product, not the goal.

The first service planned is **CRT (CKB Revocable Timelock)**: a timelock with
cancellation, where key shares are spread across many independent nodes and
deleted when the switch cell is consumed.

## What it is — and isn't

| It is | It isn't |
|---|---|
| A separate process beside your node, talking to it over local RPC | A change to the `ckb` binary or to consensus |
| Opt-in: nothing runs unless the operator enables it | Auto-running arbitrary code found on-chain |
| Trust-minimised: secure unless a threshold of nodes collude | Trustless |
| Paid to one payout address you choose (multisig or JoyID possible) | A hot wallet on your server |

## Roadmap

### Phase 1 — Node Runner dashboard and ranking (testnet first)

- Web dashboard based on a CKB fork of [mempool](https://github.com/mempool/mempool),
  restyled to make CKB's cell model easy to understand.
- Node scoring for nodes running CKB Service Runner: availability, age, sync
  status, peers, version, network diversity (ASN, region, country).
- Weekly stats summary written to a **stat cell** under an anyone-can-pay lock
  (funded by the project at start).
- One probe/scoring server at launch, to be decentralised onto the runners themselves.
- "Join the node ranking" setting, **on by default**.
- Service Runtime toggle visible but **inactive**.

### Phase 2 — Service Runtime

Activated once **both** are true:

- 12 months of Phase 1 operation, and
- at least **60 diverse nodes** in the ranking (ASN, region, country).

Then: services run from cells in CKB-VM, starting with CRT. Being in the
ranking is required to be assigned jobs.

Details: [docs/roadmap.md](docs/roadmap.md).

## Hard requirements

- **R1 — Node reputation ledger.** Public, verifiable record of availability,
  sync, version, age and diversity, collected by independent probes.
- **R2 — Fully synced full node, enforced and proven.** Checked in code (not a
  config option) and provable to others over P2P.
- **R3 — Secure execution.** Services are isolated from the host: no access to
  node data, keys or files; no outbound network; fixed CPU, memory, time and
  storage limits.
- **R4 — Persistent service storage.** Per-service storage that survives
  restarts, with quotas, encryption at rest and deletion triggered by on-chain events.

Details: [docs/architecture.md](docs/architecture.md).

## Repository layout

```
docs/          design, roadmap, open questions
config/        example configuration
runner/        (planned) the runner process — Rust
probe/         (planned) probe / scoring server
spec/          (planned) service-cell format and host interface — RFC candidates
```

The dashboard (mempool fork) lives in its own repository because of its
AGPL-3.0 licence.

## Get involved

This project is meant to be built together by CKB developers and node operators.

- Design questions → [Discussions](../../discussions)
- Concrete, agreed work → [Issues](../../issues)
- Background: ["A Revenue Layer for CKB Nodes" on Nervos Talk](https://talk.nervos.org/t/a-revenue-layer-for-ckb-nodes/10734)

See [CONTRIBUTING.md](CONTRIBUTING.md). Security reports: [SECURITY.md](SECURITY.md).

## Licence

MIT — see [LICENSE](LICENSE).
