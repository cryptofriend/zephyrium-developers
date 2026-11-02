# Validators and rewards

> Stake amounts, how a validator gets a seat, and how rewards are split.

The figures are the devnet's settings in `config/local/param.yaml`.

## Becoming a validator

| | Shard validator | Beacon validator |
|---|---|---|
| Stake | Exactly 21,000 ZEP | At least 210,000 ZEP, in multiples of 21,000 |
| Who can apply | Anyone | Only a key that is already a shard validator |
| Auto-restake | Optional | Always on |
| Stake returned | When the validator unstakes or loses its seat | Same |

A staking transaction burns the stake and names the validator key. The validator then moves through four stages:

1. **Candidate**: registered, waiting for the next random assignment.
2. **Syncing**: assigned to a shard, downloading it.
3. **Pending**: synced and waiting for a seat.
4. **Committee**: seated, signing blocks and earning.

Rotation happens once per epoch (50 beacon blocks on the devnet, about 8 minutes). A validator that misses too many signatures loses its seat at the end of the epoch. Today it gets its full stake back; burning part of the stake is on the [roadmap](/resources/roadmap).

## Committees on the devnet

| Committee | Seats | Fixed seats | Open to stakers |
|---|---|---|---|
| Shard 0 | 7 | 5 | 2 |
| Beacon | 4 | 4 | 0 |

Fixed seats are never rotated out. A block is final when more than two thirds of the committee sign it.

## Where rewards come from

Each shard block mints 34.478342477 ZEP (one shard, 10-second blocks). The amount falls 10% each year and stops after 21 years, for a total of 969,000,000 ZEP minted by blocks. Transaction fees are added to the same pool.

## How a reward is split

Every reward is split in three equal parts, the three pillars of the network:

| Share | Part of every reward | Paid to |
|---|---|---|
| Validators | 323 / 969 (33.3%) | Beacon and shard committees |
| Liquidity providers | 323 / 969 (33.3%) | The SWAP pools, in proportion to the ZEP each pool holds |
| DAO | 323 / 969 (33.3%) | `dao_address`, the DAO treasury |

The liquidity share is minted at the end of every epoch into the pDEX (SWAP) pools, by default pro rata to each pool's ZEP reserve or by the per-pool weights governance sets in the pDEX parameters. Inside a pool it accrues per LP share and is withdrawn together with the LP fees. While no pool holds ZEP there is no provider to pay, and that share goes to the DAO treasury, so nothing minted is lost.

The DAO treasury also holds the 31,000,000 ZEP genesis allocation (the ICO). Over 21 years this gives validators 323,000,000 ZEP, liquidity providers 323,000,000 ZEP and the DAO 354,000,000 ZEP (323,000,000 minted plus the ICO it distributes). There are no other allocations, cliffs or vesting; see the [release schedule](/tokenomics/zep).

:::note On the devnet
The project devnet still runs the previous split (299 of every 929 ZEP to validators, the rest to one wallet) until it is reset with the new genesis.
:::

Within the validator share, the beacon committee receives the share of two shards, and each shard's committee splits the rest equally among its seated members. On a one-shard network this gives the beacon committee two thirds of the validator share. Changing that ratio is an open design question.

Rewards accumulate per address and are claimed with a withdraw-reward transaction.

## Checking it

`python3 tests/devnet/check.py` verifies the split after the first epoch (323 to validators, 646 to the DAO treasury while no pool exists), then opens a ZEP/pUSDt pool and verifies that in the next epoch validators, the pool's liquidity provider and the DAO each receive one third. `--stakers` also verifies that an outside validator is seated and paid.
