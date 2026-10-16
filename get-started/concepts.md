# Concepts

> What Zephyrium keeps private, how the chain is structured, and its current limits.

Zephyrium is a layer-1 chain where privacy is the default for transfers.

## What is private

| | Transfers of ZEP and tokens | Swaps on pDEX | Staking |
|---|---|---|---|
| Sender | Hidden in a ring of 8 | Hidden in a ring of 8 | Public |
| Receiver | One-time address | One-time address | Public |
| Amount | Hidden | **Public** | Public |
| Which token | Hidden for tokens in confidential-asset mode | **Public** | ZEP only |

Three mechanisms do the work:

- **Ring signatures.** A spend is signed by a ring of eight keys. One is the real spender; seven are decoys taken from the chain.
- **One-time addresses.** Every payment lands on a fresh address derived for that payment, so two payments to the same person look unrelated.
- **Hidden amounts.** Amounts are commitments. A range proof shows the amount is valid and that inputs equal outputs, without revealing the number.

## How the chain is built

- **Shards** process transactions, token transfers and swaps. The devnet runs one shard.
- **The beacon chain** coordinates the shards: it records who the validators are, confirms shard blocks and carries messages between shards.
- **Committees** of validators sign blocks. A block is final when more than two thirds of the committee sign it.
- **The highway** is a relay that every node connects to. It introduces nodes to each other and forwards their messages.

[Node types](/validators/node-types) explains who runs each part.

## Current limits

These are known and on the [roadmap](/resources/roadmap):

- **Small rings with uniform decoys.** Eight members, chosen without regard to coin age, is weaker than a larger, age-aware ring.
- **Swap amounts are public.** pDEX hides who trades, not how much or which pair.
- **The highway is a single relay.** It can see which address a transaction came from, and the chain stops if it is down.
- **Fixed committee seats.** On the devnet, 5 of 7 shard seats and all 4 beacon seats are held by fixed validators.
- **Wallets share a viewing key with their node.** A wallet registers a viewing key with the node it uses so the node can find its coins.
- **No slashing penalty.** A validator that misbehaves loses its seat and gets its stake back.
