# Node types

> The four kinds of node, what each does and what it needs.

A wallet talks to a full node. Full nodes pass transactions to shard validators, who put them in blocks. Beacon validators keep the shards in step. Today a highway relays every message between them.

| Node | Stake | What it does | You can run it |
|---|---|---|---|
| Full node | None | Keeps a full copy of every chain and answers queries | Yes, on the devnet |
| Shard validator | 21,000 ZEP | Signs the blocks that carry transactions, tokens and swaps | On the devnet, 2 open seats |
| Beacon validator | 210,000 ZEP minimum | Coordinates the shards and tracks validators | Not yet; the beacon committee is closed |
| Highway | None | Relays messages and serves blocks to syncing nodes | Devnet only; being replaced |

## Full node

It downloads and checks every block and answers JSON-RPC requests. It holds no validator key and never signs blocks.

Run your own for independence and privacy: a wallet shares a viewing key with the node it uses, and on your own node that key stays on your machine.

```bash
./start_node.sh full_node     # RPC on port 9354
```

## Shard validator

A member of a shard committee. Stake exactly 21,000 ZEP, wait as a candidate, get assigned to a shard at random, sync it, then take a seat when one rotates. Seated validators earn a share of every block reward.

A validator must stay online. One that misses too many signatures loses its seat at the end of the epoch.

```bash
./start_node.sh shard0-5      # one of the two spare validator nodes on the devnet
```

## Beacon validator

A member of the beacon committee. Only a key that is already a shard validator can apply. The stake is at least 210,000 ZEP in multiples of 21,000, and auto-restake is always on.

It runs the same program as a shard validator; the beacon staking transaction is what changes its role.

## Highway

A relay server. Nodes do not connect to each other directly today: each one connects to the highway. It creates its own network identity on start and needs no keys to manage.

The [roadmap](/resources/roadmap) replaces it with direct node-to-node networking before any public network.

## What a node needs

Measured on the local devnet, which was nearly idle:

| | Disk growth | Memory at start |
|---|---|---|
| Full node | About 14 GB a year with empty blocks | About 50 MB |
| Validator | About 16 GB a year with empty blocks | About 50 MB |

Transactions add to this. Memory and processor use under real traffic have not been measured yet.
