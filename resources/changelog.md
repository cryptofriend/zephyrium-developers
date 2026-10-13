# Changelog

> What Zephyrium has changed, by date.

Changes to the Zephyrium chain. Newest first.

## 2026-10-12

- Renamed the project to Zephyrium and the coin to ZEP. The Go module is `github.com/zephyrium/zephyrium-chain`.
- Devnet scripts read validator keys from the uncommitted secrets file; the highway creates its own network identity on start.
- Removed inherited scripts and files that carried upstream test keys.

## 2026-10-11

- ZEP minting schedule: 1,000,000,000 hard cap, 21,000,000 at genesis, 979,000,000 minted by blocks over 21 years with a 10% yearly decrease.
- Every block reward is split 309/330/330/10 (of 979) between validators, finance, DAO and satoshi addresses.
- The minting cap is counted on-chain from the first block.
- Genesis coins go to a newly generated treasury key (`utility/gengenesis`).
- Stake amounts come from config: 21,000 ZEP per shard validator, 210,000 ZEP beacon minimum.
- Devnet shard committee opened to 7 seats with 5 fixed; beacon committee closed at 4.
- Highway bundled under `./highway`. Fixed: staked validators could not report their supported features, so they were never seated.
- Added `tests/devnet/check.py`, a regression check for the local devnet.

## 2026-07-06

- New committee keys generated from fresh randomness (`utility/genzephyriumkeys`), replacing the publicly derivable upstream test keys.
- Working local devnet launch.
