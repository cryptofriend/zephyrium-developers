# ZEP tokenomics

> The ZEP supply cap, the three pillars that receive it, and the 21-year release schedule.

ZEP has a hard cap of 1,000,000,000. 31,000,000 are pre-minted at genesis for the ICO, and the remaining 969,000,000 are minted block by block over 21 years, with each year minting 10% less than the one before. Every block is split on-chain in three equal parts, the three pillars of the network: validators run the chain, liquidity providers make the markets, the DAO funds growth and R&D. There is no other way to earn ZEP.

:::note On the devnet
The project devnet still runs the previous schedule (71,000,000 at genesis, 929,000,000 minted by blocks, 299 of every 929 ZEP to validators and the rest to one wallet). The schedule on this page is implemented in the chain repository and takes effect when the devnet is reset with a new genesis.
:::

## The schedule in short

| Setting | Value |
|---|---|
| Hard cap | 1,000,000,000 ZEP |
| Pre-minted at genesis | 31,000,000 ZEP (ICO) |
| Minted by blocks on the 21-year curve | 969,000,000 ZEP |
| Yearly decrease | 10% |
| Curve years | 21 |
| Year 1 block reward | 34.478342477 ZEP per shard block (one shard, 10-second blocks) |
| Year 1 minted | 108,805,374 ZEP |
| Cliffs and vesting | None |

## The three pillars

| Share | Of every block | Of the 1B cap | ZEP over 21 years | How it is paid |
|---|---|---|---|---|
| Validators | 323 / 969 | 32.3% | 323,000,000 | To the beacon and shard committees' reward balances, per seat |
| Liquidity providers | 323 / 969 | 32.3% | 323,000,000 | Minted at the end of each epoch into the SWAP pools, pro rata to the ZEP each pool holds; providers withdraw it with their LP fees |
| DAO | 323 / 969 | 32.3% | 323,000,000 | To the DAO treasury address (`dao_address`) |
| ICO | genesis | 3.1% | 31,000,000 | Pre-minted to the DAO treasury, which distributes it to buyers |

The liquidity part is paid by the pDEX's liquidity-mining mechanism: the chain credits each pool's reward-per-share, and a provider's claim grows with the LP shares they hold. By default pools are weighted by their ZEP reserve; governance can instead set per-pool weights in the pDEX parameters. While no pool holds ZEP there is no provider to pay, and that part goes to the DAO treasury, so nothing minted is lost.

The DAO treasury therefore ends with 354,000,000 ZEP over 21 years: 323,000,000 minted plus the 31,000,000 ICO it distributes. Contributors and the team are paid by the DAO; there is no team allocation, cliff or vesting in the protocol.

## Year by year

All figures are whole ZEP, rounded; year 21 takes the rounding remainder so each column total is exact. Inflation is the year's minting as a share of the supply at the start of that year.

<div className="table-wrap">

| Year | Total minted | Validators | Liquidity | DAO | ICO | Cumulative supply | Inflation |
|---|---|---|---|---|---|---|---|
| Genesis | 31,000,000 | 0 | 0 | 0 | 31,000,000 | 31,000,000 |  |
| 1 | 108,805,374 | 36,268,458 | 36,268,458 | 36,268,458 | 0 | 139,805,374 | 350.99% |
| 2 | 97,924,836 | 32,641,612 | 32,641,612 | 32,641,612 | 0 | 237,730,210 | 70.04% |
| 3 | 88,132,353 | 29,377,451 | 29,377,451 | 29,377,451 | 0 | 325,862,563 | 37.07% |
| 4 | 79,319,118 | 26,439,706 | 26,439,706 | 26,439,706 | 0 | 405,181,681 | 24.34% |
| 5 | 71,387,205 | 23,795,735 | 23,795,735 | 23,795,735 | 0 | 476,568,886 | 17.62% |
| 6 | 64,248,486 | 21,416,162 | 21,416,162 | 21,416,162 | 0 | 540,817,372 | 13.48% |
| 7 | 57,823,638 | 19,274,546 | 19,274,546 | 19,274,546 | 0 | 598,641,010 | 10.69% |
| 8 | 52,041,273 | 17,347,091 | 17,347,091 | 17,347,091 | 0 | 650,682,283 | 8.69% |
| 9 | 46,837,146 | 15,612,382 | 15,612,382 | 15,612,382 | 0 | 697,519,429 | 7.20% |
| 10 | 42,153,432 | 14,051,144 | 14,051,144 | 14,051,144 | 0 | 739,672,861 | 6.04% |
| 11 | 37,938,087 | 12,646,029 | 12,646,029 | 12,646,029 | 0 | 777,610,948 | 5.13% |
| 12 | 34,144,278 | 11,381,426 | 11,381,426 | 11,381,426 | 0 | 811,755,226 | 4.39% |
| 13 | 30,729,852 | 10,243,284 | 10,243,284 | 10,243,284 | 0 | 842,485,078 | 3.79% |
| 14 | 27,656,865 | 9,218,955 | 9,218,955 | 9,218,955 | 0 | 870,141,943 | 3.28% |
| 15 | 24,891,180 | 8,297,060 | 8,297,060 | 8,297,060 | 0 | 895,033,123 | 2.86% |
| 16 | 22,402,062 | 7,467,354 | 7,467,354 | 7,467,354 | 0 | 917,435,185 | 2.50% |
| 17 | 20,161,854 | 6,720,618 | 6,720,618 | 6,720,618 | 0 | 937,597,039 | 2.20% |
| 18 | 18,145,671 | 6,048,557 | 6,048,557 | 6,048,557 | 0 | 955,742,710 | 1.94% |
| 19 | 16,331,103 | 5,443,701 | 5,443,701 | 5,443,701 | 0 | 972,073,813 | 1.71% |
| 20 | 14,697,993 | 4,899,331 | 4,899,331 | 4,899,331 | 0 | 986,771,806 | 1.51% |
| 21 | 13,228,194 | 4,409,398 | 4,409,398 | 4,409,398 | 0 | 1,000,000,000 | 1.34% |
| **Total** | 1,000,000,000 | 323,000,000 | 323,000,000 | 323,000,000 | 31,000,000 | | |

</div>

Source data: `docs/zep-minting.csv` in the chain repository. The chain-side parameters are `basic_reward`, `max_reward` and the `tokenomics` block of `param.yaml`; see [Network parameters](/validators/network-parameters) and [Validators and rewards](/validators/overview).
