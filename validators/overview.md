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

Each shard block mints 34.834156126 ZEP on the devnet (one shard, 10-second blocks). The amount falls 10% each year and stops after 21 years, for a total of 979,000,000 ZEP minted by blocks. Transaction fees are added to the same pool.

## How a reward is split

| Share | Part of every reward | Paid to |
|---|---|---|
| Validators | 309 / 979 (31.56%) | Beacon and shard committees |
| Finance | 330 / 979 (33.71%) | `finance_address` |
| DAO | 330 / 979 (33.71%) | `dao_address` |
| Satoshi | 10 / 979 (1.02%) | `satoshi_address` |

The validator share is 309 and not 330 because 21,000,000 ZEP of the validators' third is issued at genesis.

Within the validator share, the beacon committee receives the share of two shards, and each shard's committee splits the rest equally among its seated members. On a one-shard network this gives the beacon committee two thirds of the validator share. Changing that ratio is an open design question.

Rewards accumulate per address and are claimed with a withdraw-reward transaction.

## Checking it

`python3 tests/devnet/check.py` verifies the split against these shares after the first epoch, and `--stakers` verifies that an outside validator is seated and paid.
