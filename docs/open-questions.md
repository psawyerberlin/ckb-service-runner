# Open questions and V1 proposals

Comment in [Discussions](../../../discussions). Each row can become its own thread.

| Question | V1 proposal |
|---|---|
| Verify service code by hash or author signature? | Code hash, pinned by the operator |
| Discover services by registry cell or convention? | Convention (a known type script); a registry adds governance |
| Versioning | Each version is its own code hash |
| Who collects fees? | The node, to its payout address |
| Cross-service calls | No |
| How are nodes chosen for a job? | From the ranking, with minimum reputation and diversity set by the application |
| Node identity | P2P peer ID; service key bound to it by signature |
| How to stop result copying / fee front-running? | Claims bound to the signer's key; first-claim or assignment rule — open |
| How to prove deletion of a secret? | Not provable; diversity + bonding/slashing + thresholds |
| Who runs probes long-term? | Runners probe each other; method open |
| Stat cell funding after launch | Anyone-can-pay lock; long-term funding open |
| Neuron (desktop) support | Later; full-node mode only, light client cannot satisfy R2 |
