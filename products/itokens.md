# iTokens

> Private tokens on Zephyrium.

An iToken is a token on Zephyrium that moves with the same privacy as ZEP: the sender hides in a ring, the receiver gets a one-time address and the amount is hidden.

## Creating one

Any account can create a token with a fixed supply in one transaction. The whole supply is issued to the creator.

On the devnet this is the `createandsendtokeninittransaction` RPC method, and iWallet lists the new token once it arrives. A newly created token needs a few blocks before it can be spent.

## Privacy of a token transfer

| | Visible to the public? |
|---|---|
| Sender | No |
| Receiver | No |
| Amount | No |
| Which token | Hidden for tokens in confidential-asset mode; visible otherwise |

Making confidential-asset mode the rule for every token is on the [roadmap](/resources/roadmap).

## What is planned

- **Issuer-owned tokens** with a public registry entry and an optional mintable supply.
- **An auditor key per token**, so an issuer can show activity to a regulator without showing it to everyone.
- **Private distributions** such as dividends to current holders.

## Known limit

The code inherited a central issuing key that can mint new tokens. It is scheduled for removal in the first phase of the [roadmap](/resources/roadmap).
