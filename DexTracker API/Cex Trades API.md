# CEX Trades API

## API Url

```
wss://api.cryptoscan.pro/cex?exchange=&symbol=
```

## Usage example

```
wss://api.cryptoscan.pro/cex?exchange=mexc&symbol=TRUMP_USDT
```

## Request parameters

- `exchange` - mexc, mexc-futures, binance, bingx, bitget, bybit, bitmart, coinbase, coinex, digifinex, gate, htx, kucoin, kucoin-futures, lbank, lbank-futures, okx, okx-futures, phemex, poloniex, upbit, xt, yobit
- `symbol` - example: `BTC_USDT` or `BTC`

Also we support list of dex exchanges: defx, derive, hyperliquid, idex, paradex, woofipro

## Response parameters

Listens transactions of all exchanges by a coin symbol in real time with zero delay.

- `exchange` - name of the exchange
- `symbol` - name of the token
- `type` - buy, sell
- `volume` - Amount of USD
- `price` - Price in USD
