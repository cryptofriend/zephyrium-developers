# Network parameters

> Every devnet setting and where it lives.

Zephyrium has one network today, the local devnet, configured in `config/local/`.

| Setting | Devnet value | Key in `param.yaml` |
|---|---|---|
| Shards | 1 | `active_shards` |
| Block interval | 10 seconds | `block_time` |
| Epoch length | 50 beacon blocks | `epoch_param.number_of_block_in_epoch` |
| Shard committee | 5 to 7 seats, 5 fixed | `committee_size` |
| Beacon committee | 4 seats, 4 fixed | `committee_size` |
| Shard stake | 21,000 ZEP | `staking_amount_shard` |
| Beacon stake minimum | 210,000 ZEP | `staking_amount_beacon_min` |
| Block reward | 34.834156126 ZEP per shard block | `basic_reward` |
| Yearly decrease | 10%, for 21 years | `tokenomics` |
| Minted by blocks, cap | 979,000,000 ZEP | `max_reward` |
| Reward shares | 309 / 330 / 330 / 10 | `tokenomics` |
| Genesis allocation | 21,000,000 ZEP to the treasury key | `init_tx.json` |

Amounts in the config files are in the smallest unit: 1 ZEP = 1,000,000,000 units.

## Notes

- `basic_reward` is per shard block. A network with more shards or a different block interval needs a different value to mint the same yearly total.
- The committee members at genesis come from `keylist.json`: the first 4 beacon keys and the first 5 keys of shard 0.
- These are consensus settings. Every node must run the same values, and changing genesis or committee settings requires a new chain.
- Other folders under `config/` (`mainnet`, `testnet-1`, `testnet-2`) are Incognito's networks, kept for reference. They do not describe a Zephyrium network.
