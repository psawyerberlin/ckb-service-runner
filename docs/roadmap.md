# Roadmap

Testnet always comes first. Each phase runs on testnet before mainnet.

## Phase 0 — Requirements (now)

- [ ] GitHub Discussion: problem, non-goals, requirements R1–R4, open questions
- [ ] Feedback from CKB / CKB-VM maintainers on the host-interface idea
- [ ] Funding for a prototype (Spark revision or Community Fund DAO proposal)

## Phase 1 — Node Runner dashboard and ranking

Goal: give operators value from day one, before any paying service exists.

- [ ] Dashboard: CKB fork of mempool, restyled with a cell-model look
- [ ] Runner process: local node checks (synced, localhost RPC, peers)
- [ ] Settings page, including "Join the node ranking" (on by default)
- [ ] Ranking page; greyed out with "join ranking to see stats" when opted out
- [ ] Probe/scoring server: availability, age, sync lag, peers, version, ASN/region/country
- [ ] Ranking covers only nodes running CKB Service Runner
- [ ] Weekly stat cell (summary + hash of detail) under an anyone-can-pay lock
- [ ] Service Runtime toggle shown, inactive
- [ ] Testnet → mainnet

## Phase 2 — Service Runtime

Activation criteria (both required):

- 12 months of Phase 1 operation
- ≥ 60 diverse nodes in the ranking (ASN, region, country)

Work:

- [ ] Service-cell format and host interface (RFC in nervosnetwork/rfcs)
- [ ] CKB-VM sandbox with cycle, memory and storage limits
- [ ] Per-service persistent storage with event-driven deletion
- [ ] Job assignment from the ranking (minimum reputation and diversity per app)
- [ ] Probing decentralised onto the runners themselves
- [ ] Security audit before mainnet
- [ ] First service: CRT (CKB Revocable Timelock)
