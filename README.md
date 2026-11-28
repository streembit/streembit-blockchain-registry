# streembit-blockchain-registry

This repository belongs to [streembit-blockchain](https://github.com/streembit/streembit-blockchain), the node software of the Streembit blockchain. It holds the published files of the blockchain: the Open Call documents and the bootstrap policy of each network. The blockchain is governed by the Streembit Blockchain Protocol Specification, in the main repository at [`docs/specifications/streembit-sbrit-protocol-specification.md`](https://github.com/streembit/streembit-blockchain/blob/main/docs/specifications/streembit-sbrit-protocol-specification.md).

The repository is also the npm package `streembit-blockchain-registry`. The package holds the Open Call documents and the policy files. It has no code and no dependencies: installing it puts the files on a node's disk.

## Open Calls

Under the protocol an Open Call is the only route to admission: a public, dated invitation to apply for a stated number of Accountable Node or validator places. The Open Call documents are in `open-calls` and are part of the npm package.

## Policies

A policy file holds what a node needs to start a chain: the bootstrap policy (the Accountable Node, the genesis validators, the approval threshold and the approval sender) and the genesis timestamp of one network.

| Field | Content |
|---|---|
| `name` | The file's own name with its version, for example `devnet-1` |
| `network` | The network name, as in the node config |
| `chainId` | The chain id of that network |
| `genesisTimestamp` | The start time of the chain, in milliseconds |
| `policy` | The bootstrap policy: `accountableNode`, `validators`, `approvalThreshold`, `approvalSender` |

A published file is never changed. A new chain or a corrected policy is a new file with a new version in its name, in a new version of the package.

The nodes of a published network must use the registry's file: on `testnet` and `mainnet` a node loads its policy from this package only.

### Published policies

| File | Network | Chain id | Genesis timestamp | Policy hash |
|---|---|---|---|---|
| `policies/devnet-1.json` | devnet | 1337 | 1795778846000 (2026-11-27 11:27:26 UTC) | `065bd463615b164615e20bac91faff67afe343d984dad18ac5bb9db64ad67ec5` |

The policy hash is the BLAKE2b-256 hash of the policy as the node encodes it. A node logs it when it writes the policy into its store; an operator compares the logged value with this table.

`devnet-1` is the policy of the development network of the `streembit-blockchain` repository, with that repository's devnet keys. It exists so that loading a policy from this package can be tested on a local network.
