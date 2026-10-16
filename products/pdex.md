# pDEX

> The exchange built into the Zephyrium chain.

pDEX is an exchange that is part of the chain itself: pools and swaps are handled by the validators, with no separate contract to deploy.

## How it works

- **Pools** hold two assets and price swaps with the constant-product rule: the product of the two balances stays the same through a trade.
- **Liquidity providers** add both assets to a pool. A position is tied to a position key that the provider mints once.
- **Swaps** burn the asset being sold and pay out the asset being bought to a one-time address.

| Setting | Devnet value |
|---|---|
| Default pool fee | 0.30% |
| Highest fee a pool can have | 2% |
| Cost to mint a position key | 1 ZEP |

## What is private, and what is not

| | On pDEX today |
|---|---|
| Who traded | Hidden: the trade is signed by a ring of 8 |
| Where the proceeds go | Hidden: a one-time address |
| Amount sold | **Public** |
| Token pair | **Public** |

pDEX gives anonymous trades, not confidential ones. Hiding swap amounts is a research item on the [roadmap](/resources/roadmap).

## Try it on the devnet

The devnet check creates a test token, adds a ZEP pool for it and swaps 1 ZEP:

```bash
python3 tests/devnet/check.py
```

The last line of its output reports the swap, for example `DEX swap: 1 ZEP bought 1.998002 pUSDt`.

## Names in the code

The RPC methods carry the same name in lowercase: `pdexv3_getState`, `pdexv3_txAddLiquidity` and `pdexv3_txTrade`.

## Known limit

A single admin key can still change pDEX parameters such as fee rates. Removing it is the first phase of the [roadmap](/resources/roadmap).
