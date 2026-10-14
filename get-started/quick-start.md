# Quick start

> Build, launch and check a local Zephyrium devnet.

A devnet is a complete private network on one machine: a highway, 4 beacon validators, 5 shard validators and a full node. It produces a block about every 10 seconds.

## Requirements

- Go 1.24 or newer, python3, curl
- macOS or Linux. Only macOS on Apple Silicon has been tested.
- Free ports: 9330, 9334-9344, 9350-9354, 9434-9454

## 1. Create the keys (once)

Validator and treasury keys live in `secrets/secrets.json`, which is git-ignored. On a new machine:

```bash
mkdir -p secrets && cd secrets
GO111MODULE=on GOFLAGS=-mod=mod go run -ldflags=-checklinkname=0 ../utility/genzephyriumkeys
# writes keylist.json, keylist-v2.json and secrets.json into this folder
cp keylist.json keylist-v2.json ../config/local/
cd ..
GO111MODULE=on GOFLAGS=-mod=mod go run -ldflags=-checklinkname=0 ./utility/gengenesis
```

`gengenesis` adds a foundation key to `secrets/secrets.json`, writes the genesis allocation to `config/local/init_tx.json`, and sets `dao_address` in `config/local/param.yaml` to the foundation address. Nothing to paste by hand.

Back up `secrets/secrets.json`. It is the only copy of the private keys.

## 2. Build

```bash
GO111MODULE=on GOFLAGS=-mod=mod go build -ldflags=-checklinkname=0 -o incognito ./
```

The `-ldflags=-checklinkname=0` flag is required with Go 1.24 or newer.

## 3. Launch

```bash
./launch_local.sh
```

This builds the highway on first use, starts it, then starts the nodes one second apart. Logs go to `logs/`, chain data to `data/`.

## 4. Check

```bash
python3 tests/devnet/check.py
```

It checks block production, the genesis balance, the stake rules, the reward split after the first epoch, and a DEX swap. It takes about 10 minutes because it waits for an epoch to end. Add `--stakers` to also stake two outside validators and wait until one is seated and paid (about 30 minutes; start `./start_node.sh shard0-5` and `./start_node.sh shard0-6` first).

To query the chain yourself, the full node answers JSON-RPC on port 9354:

```bash
curl -s -X POST http://127.0.0.1:9354 -H 'Content-Type: application/json' \
  -d '{"jsonrpc":"1.0","method":"getblockchaininfo","params":[],"id":1}'
```

## 5. Stop and reset

```bash
./stop_local.sh          # stops only this folder's nodes and highway
rm -rf data logs         # optional: the next launch starts a new chain at block 1
```

A reset is required after changing genesis or committee settings. Do not use the inherited `stop.sh`; it closes every tmux session on the machine.

## Nodes and ports

| Node | Role | Peer port | RPC port |
|---|---|---|---|
| highway | Introduces nodes and relays messages | 9330 | none |
| beacon-0 to beacon-3 | Beacon validators | 9450-9453 | 9350-9353 |
| shard0-0 to shard0-3 | Fixed shard validators | 9434-9437 | 9334-9337 |
| shard0-4 | Fixed shard validator | 9442 | 9342 |
| shard0-5, shard0-6 | Spare nodes for staked validators | 9443, 9444 | 9343, 9344 |
| full_node | Follows all chains; query this one | 9454 | 9354 |
