# DEX Trades API

## API Url

```
wss://api.cryptoscan.pro/dex?network=&address=
```

## Usage example

```
wss://api.cryptoscan.pro/dex?network=sol&address=4k3Dyjzvzp8eMZWUXbBCjEvwSkkk59S5iCNLY3QrkX6R
```

## Request parameters

- `network` - sol, eth, bsc, base, tron
- `address` - coin address

## Response parameters

Listens transactions of all pools for coin contract address in real time with zero delay.

- `type` - buy, sell
- `network` - sol, eth, bsc, base, tron
- `volume` - Amount of USD
- `price` - Price in USD
- `exchange` - Name of transaction exchange
- `txn` - Unique ID of transaction
- `walletAddress` - Wallet address of transaction
- `pool` - Pool address of transaction
