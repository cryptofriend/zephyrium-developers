# ZEP tokenomics

> The ZEP supply cap, who receives it, and the 21-year release schedule.

ZEP has a hard cap of 1,000,000,000. 71,000,000 are pre-minted at genesis for the ICO, and the remaining 929,000,000 are released over 21 years, with each year releasing 10% less than the one before.

:::note On the devnet
The project devnet still runs the previous schedule (21,000,000 at genesis, 979,000,000 minted by blocks, 299 of every 979 ZEP to validators). The 71,000,000 ZEP genesis and the 299/929 split are ready in the chain repository and take effect when the devnet is reset. The split between liquidity, foundation and team, and the team cliff, are not enforced on-chain yet; see [Validators and rewards](/validators/overview).
:::

## The schedule in short

| Setting | Value |
|---|---|
| Hard cap | 1,000,000,000 ZEP |
| Pre-minted at genesis | 71,000,000 ZEP (ICO) |
| Released on the 21-year curve | 929,000,000 ZEP |
| Yearly decrease | 10% |
| Curve years | 21 |
| Year 1 curve release | 104,313,924 ZEP |
| Cliff, Team & Contributors | 12 months |

## Who receives it

| Share | Of the 1B cap | ZEP | Release | Cliff |
|---|---|---|---|---|
| Validators | 29.9% | 299,000,000 | 21-year curve | None |
| Liquidity | 21% | 210,000,000 | 21-year curve | None |
| Foundation | 21% | 210,000,000 | 21-year curve | None |
| Team & Contributors | 21% | 210,000,000 | 21-year curve | 1 year |
| ICO | 7.1% | 71,000,000 | Pre-minted at genesis | None |

The ICO includes what was earlier a separate investor allocation. It is minted in the genesis block to the foundation wallet, which distributes it to buyers.

Team & Contributors accrue from genesis, but nothing is liquid during the first 12 months. What they accrued in year 1 unlocks when the cliff ends, so it is counted in year 2.

## Year by year

All figures are whole ZEP. Inflation is the year's unlock as a share of the supply at the start of that year.

<div className="table-wrap">

| Year | Total unlocked | Validators | Liquidity | Foundation | Team & Contributors | ICO | Cumulative supply | Inflation |
|---|---|---|---|---|---|---|---|---|
| Genesis | 71,000,000 | 0 | 0 | 0 | 0 | 71,000,000 | 71,000,000 |  |
| 1 | 80,733,812 | 33,573,588 | 23,580,112 | 23,580,112 | 0 | 0 | 151,733,812 | 113.71% |
| 2 | 117,462,644 | 30,216,229 | 21,222,101 | 21,222,101 | 44,802,213 | 0 | 269,196,456 | 77.41% |
| 3 | 84,494,279 | 27,194,606 | 19,099,891 | 19,099,891 | 19,099,891 | 0 | 353,690,735 | 31.39% |
| 4 | 76,044,852 | 24,475,146 | 17,189,902 | 17,189,902 | 17,189,902 | 0 | 429,735,587 | 21.50% |
| 5 | 68,440,364 | 22,027,631 | 15,470,911 | 15,470,911 | 15,470,911 | 0 | 498,175,951 | 15.93% |
| 6 | 61,596,328 | 19,824,868 | 13,923,820 | 13,923,820 | 13,923,820 | 0 | 559,772,279 | 12.36% |
| 7 | 55,436,695 | 17,842,381 | 12,531,438 | 12,531,438 | 12,531,438 | 0 | 615,208,974 | 9.90% |
| 8 | 49,893,025 | 16,058,143 | 11,278,294 | 11,278,294 | 11,278,294 | 0 | 665,101,999 | 8.11% |
| 9 | 44,903,724 | 14,452,329 | 10,150,465 | 10,150,465 | 10,150,465 | 0 | 710,005,723 | 6.75% |
| 10 | 40,413,353 | 13,007,096 | 9,135,419 | 9,135,419 | 9,135,419 | 0 | 750,419,076 | 5.69% |
| 11 | 36,372,017 | 11,706,386 | 8,221,877 | 8,221,877 | 8,221,877 | 0 | 786,791,093 | 4.85% |
| 12 | 32,734,815 | 10,535,748 | 7,399,689 | 7,399,689 | 7,399,689 | 0 | 819,525,908 | 4.16% |
| 13 | 29,461,333 | 9,482,173 | 6,659,720 | 6,659,720 | 6,659,720 | 0 | 848,987,241 | 3.59% |
| 14 | 26,515,200 | 8,533,956 | 5,993,748 | 5,993,748 | 5,993,748 | 0 | 875,502,441 | 3.12% |
| 15 | 23,863,679 | 7,680,560 | 5,394,373 | 5,394,373 | 5,394,373 | 0 | 899,366,120 | 2.73% |
| 16 | 21,477,312 | 6,912,504 | 4,854,936 | 4,854,936 | 4,854,936 | 0 | 920,843,432 | 2.39% |
| 17 | 19,329,580 | 6,221,254 | 4,369,442 | 4,369,442 | 4,369,442 | 0 | 940,173,012 | 2.10% |
| 18 | 17,396,622 | 5,599,128 | 3,932,498 | 3,932,498 | 3,932,498 | 0 | 957,569,634 | 1.85% |
| 19 | 15,656,959 | 5,039,215 | 3,539,248 | 3,539,248 | 3,539,248 | 0 | 973,226,593 | 1.64% |
| 20 | 14,091,263 | 4,535,294 | 3,185,323 | 3,185,323 | 3,185,323 | 0 | 987,317,856 | 1.45% |
| 21 | 12,682,144 | 4,081,765 | 2,866,793 | 2,866,793 | 2,866,793 | 0 | 1,000,000,000 | 1.28% |
| **Total** | 1,000,000,000 | 299,000,000 | 210,000,000 | 210,000,000 | 210,000,000 | 71,000,000 | | |

</div>

Year 21 takes the rounding remainder so each total is exact.

## Around the cliff

Cumulative ZEP unlocked at the end of selected months.

<div className="table-wrap">

| Month | Circulating supply | Validators | Liquidity | Foundation | Team & Contributors | ICO |
|---|---|---|---|---|---|---|
| 6 | 111,366,906 | 16,786,794 | 11,790,056 | 11,790,056 | 0 | 71,000,000 |
| 11 | 145,005,995 | 30,775,789 | 21,615,103 | 21,615,103 | 0 | 71,000,000 |
| 12 | 151,733,812 | 33,573,588 | 23,580,112 | 23,580,112 | 0 | 71,000,000 |
| 13 | 183,137,467 | 36,091,607 | 25,348,620 | 25,348,620 | 25,348,620 | 71,000,000 |
| 18 | 222,255,189 | 48,681,703 | 34,191,162 | 34,191,162 | 34,191,162 | 71,000,000 |
| 24 | 269,196,456 | 63,789,817 | 44,802,213 | 44,802,213 | 44,802,213 | 71,000,000 |

</div>

Circulating supply rises from 151,733,812 at month 12 to 183,137,467 at month 13, when the first year of Team & Contributors accrual unlocks.
