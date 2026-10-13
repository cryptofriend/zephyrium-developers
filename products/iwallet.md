# iWallet

> The browser-extension wallet for Zephyrium.

iWallet is a Chrome extension wallet for the Zephyrium devnet. It builds private transactions in the browser, so spending keys never leave your device.

:::note Devnet only
iWallet is not in the Chrome Web Store. It is loaded as an unpacked extension and connects to a devnet node. Coins on a devnet have no value.
:::

## What it does

| Feature | Details |
|---|---|
| Send and receive ZEP | Payments land on one-time addresses automatically |
| Tokens | Lists every iToken you hold and sends them |
| iDEX | Add liquidity and swap from the popup |
| Connect to apps | Web pages can request a connection, balances and transactions; each needs your approval |

## How it protects keys

- The wallet seed is encrypted on your device with your password.
- Ring signatures and range proofs are computed in the browser, then the finished transaction is sent to a node.
- Building a transaction takes roughly 5 to 15 seconds, and the popup has to stay open while it does.

## What the node learns

To find your coins, the wallet registers a **viewing key** with the node it uses. That node can see your incoming coins; it cannot spend them. Use a node you run yourself if that matters to you. Removing this step is on the [roadmap](/resources/roadmap).

## Fees on the devnet

| Transaction | Minimum fee |
|---|---|
| ZEP transfer | 0.1 ZEP |
| Token transaction | 10 ZEP |
