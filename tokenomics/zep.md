# ZEP tokenomics

> The ZEP supply cap, minting schedule and how every block reward is split.

ZEP has a hard cap of 1,000,000,000. 21,000,000 exist at genesis and the remaining 979,000,000 are minted by blocks over 21 years, with each year minting 10% less than the one before.

## The schedule in short

| Setting | Value |
|---|---|
| Hard cap | 1,000,000,000 ZEP |
| At genesis | 21,000,000 ZEP, counted as part of the validators' share |
| Minted by blocks | 979,000,000 ZEP |
| Yearly decrease | 10% |
| Minting years | 21 |
| Year 1 mint | 109,928,237 ZEP |

## Who receives it

Every block reward is split four ways.

| Share | Of the 1B cap | Of each block reward | Purpose |
|---|---|---|---|
| Validators (Security) | 33% | 309 / 979 | Paid to seated beacon and shard validators |
| Finance | 33% | 330 / 979 | Liquidity and the neobank |
| DAO | 33% | 330 / 979 | Growth and development |
| Satoshi | 1% | 10 / 979 | Creators |

Validators receive 309 parts of each block and not 330 because 21,000,000 ZEP of their third is issued at genesis.

## Year by year

All figures are whole ZEP.

<div className="table-wrap">

| Year | Minted | Validators | Finance | DAO | Satoshi | Total supply |
|---|---|---|---|---|---|---|
| Genesis | 21,000,000 | 21,000,000 | 0 | 0 | 0 | 21,000,000 |
| 1 | 109,928,237 | 34,696,451 | 37,054,462 | 37,054,462 | 1,122,862 | 130,928,237 |
| 2 | 98,935,414 | 31,226,806 | 33,349,016 | 33,349,016 | 1,010,576 | 229,863,651 |
| 3 | 89,041,872 | 28,104,125 | 30,014,114 | 30,014,114 | 909,519 | 318,905,523 |
| 4 | 80,137,686 | 25,293,713 | 27,012,703 | 27,012,703 | 818,567 | 399,043,209 |
| 5 | 72,123,915 | 22,764,341 | 24,311,432 | 24,311,432 | 736,710 | 471,167,124 |
| 6 | 64,911,524 | 20,487,907 | 21,880,289 | 21,880,289 | 663,039 | 536,078,648 |
| 7 | 58,420,371 | 18,439,116 | 19,692,260 | 19,692,260 | 596,735 | 594,499,019 |
| 8 | 52,578,335 | 16,595,205 | 17,723,034 | 17,723,034 | 537,062 | 647,077,354 |
| 9 | 47,320,501 | 14,935,684 | 15,950,731 | 15,950,731 | 483,355 | 694,397,855 |
| 10 | 42,588,452 | 13,442,116 | 14,355,658 | 14,355,658 | 435,020 | 736,986,307 |
| 11 | 38,329,606 | 12,097,904 | 12,920,092 | 12,920,092 | 391,518 | 775,315,913 |
| 12 | 34,496,646 | 10,888,114 | 11,628,083 | 11,628,083 | 352,366 | 809,812,559 |
| 13 | 31,046,982 | 9,799,302 | 10,465,275 | 10,465,275 | 317,130 | 840,859,541 |
| 14 | 27,942,283 | 8,819,372 | 9,418,747 | 9,418,747 | 285,417 | 868,801,824 |
| 15 | 25,148,054 | 7,937,435 | 8,476,872 | 8,476,872 | 256,875 | 893,949,878 |
| 16 | 22,633,249 | 7,143,692 | 7,629,185 | 7,629,185 | 231,187 | 916,583,127 |
| 17 | 20,369,925 | 6,429,322 | 6,866,267 | 6,866,267 | 208,069 | 936,953,052 |
| 18 | 18,332,932 | 5,786,390 | 6,179,640 | 6,179,640 | 187,262 | 955,285,984 |
| 19 | 16,499,639 | 5,207,751 | 5,561,676 | 5,561,676 | 168,536 | 971,785,623 |
| 20 | 14,849,674 | 4,686,976 | 5,005,508 | 5,005,508 | 151,682 | 986,635,297 |
| 21 | 13,364,703 | 4,218,278 | 4,504,956 | 4,504,956 | 136,513 | 1,000,000,000 |

</div>

## How the chain enforces it

- The block reward, yearly decrease and number of minting years are network settings; see [Network parameters](/validators/network-parameters).
- The chain counts every minted coin from the first block and stops at 979,000,000.
- On the devnet the split was checked against these shares after the first epoch; see [Validators and rewards](/validators/overview).

Transaction fees are added to the same pool and split by the same shares.
