# Differences from Incognito

> What Zephyrium changed, what it kept, and the naming table.

Zephyrium started from Incognito Chain (see [NOTICE](/resources/credits) for the exact source). This page lists what has changed and what has deliberately stayed the same.

## Changed

| Area | Incognito | Zephyrium |
|---|---|---|
| Coin | PRV, 100M cap | ZEP, 1,000,000,000 cap |
| Minting | 9% yearly decrease, no end date | 10% yearly decrease, ends after 21 years |
| Reward split | 10% to the DAO falling to 3%, rest to validators | 309/330/330/10 of 979 to validators, finance, DAO, satoshi |
| Minting cap | Enforced only from a later block version | Counted from the first block |
| Shard stake | 1,750 PRV, hard-coded | 21,000 ZEP, set in config |
| Beacon stake minimum | 87,500 PRV, hard-coded | 210,000 ZEP, set in config |
| Local network genesis | Coins on a publicly known test key | 21,000,000 ZEP on a freshly generated key |
| Local network committee keys | Derived from a public passphrase | Generated from fresh randomness |
| Highway | Separate repository | Bundled under `./highway` |
| Highway bug | Staked validators could not report features and were never seated | Fixed |
| Devnet scripts | Keys written into scripts | Keys read from an uncommitted secrets file |

## Not changed

The privacy transaction system, the consensus protocol, the DEX and the bridge code are as inherited. Zephyrium has not yet changed any cryptography.

Known inherited limits that are planned work, not finished work, are in the [roadmap](/resources/roadmap).

## Names

| Incognito | Zephyrium | Renamed in code? |
|---|---|---|
| Incognito | Zephyrium | Yes, in text and the Go module path |
| PRV | ZEP | The display name is ZEP. Identifiers and JSON fields such as `FeeInPRV`, and the `"PRV"` key in RPC replies, are unchanged. |
| Incognito Wallet | iWallet | Separate project, not in this repository |
| `incognito` (the program) | `incognito` | No |
| `INCOGNITO_*` environment variables | unchanged | No |
| pDEX | iDEX | No; the code and RPC methods still say `pdex` |
| pToken | iToken | No |

Identifiers, RPC field names and the program name are left as they are on purpose. Renaming them would break wallets and tools that talk to a node, and would change stored chain data.

In documents, "Incognito" is kept wherever it refers to the upstream project or its history.
