# Roadmap

> Planned work, in order.

Zephyrium continues the development of the Incognito Chain codebase. The work below is planned; none of it is finished unless the [changelog](/resources/changelog) says so.

## 1. Remove the remaining central keys

- Remove the inherited central issuing key, which can mint new tokens.
- Remove the single admin key that can change DEX and bridge parameters; set bounds on the parameters that have none.
- Phase out fixed committee seats so that every seat is held by a staker.

## 2. Strengthen privacy

- Larger rings with decoys chosen to resemble real spending patterns.
- Hide the token type on every token transfer.
- Let wallets find their coins without giving a viewing key to a node.

## 3. Replace the highway

- Peer discovery, message gossip and block sync directly between nodes, with no relay in the middle.
- Hide which node a transaction came from.

## 4. Harden consensus

- Committee randomness that a single block proposer cannot steer.
- Slashing that burns part of a misbehaving validator's stake.

## 5. Tokenization

- Tokens owned by their issuer, with a public registry entry.
- Optional per-token auditor key, private distributions to holders, and blocking of specific coins after legal disclosure.

## 6. Research

- A shielded pool, so the anonymity set is every coin on the chain.
- Zero-knowledge holder credentials and sealed batch-auction swaps.

## Before a public network

A public testnet waits for items 1 to 3. Mainnet additionally waits for item 4 and an external security audit.
