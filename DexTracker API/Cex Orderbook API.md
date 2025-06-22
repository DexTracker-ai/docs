# Cex Orderbook API

```
https://api.cryptoscan.pro/depth?exchange=&symbol=
```

## Usage example

```
https://api.cryptoscan.pro/depth?exchange=mexc-futures&symbol=LAUNCHCOIN_USDT&from=0.08&to=0.09
```

## Request parameters

- `exchange` - mexc, mexc-futures, binance, bingx, bitget, bybit, bitmart, coinbase, coinex, digifinex, gate, htx, kucoin, kucoin-futures, lbank, lbank-futures, okx, okx-futures, phemex, poloniex, upbit, xt, yobit
- `symbol` - example: `BTC_USDT` or `BTC`
- `from` - Price from
- `to` - Price to

Also we support list of dex exchanges: defx, derive, hyperliquid, idex, paradex, woofipro

## Response parameters

Get amount of USD between two prices in orderbook

- `totalVolumeUSD` - USD between prices
- `fromPrice` - Price from
- `toPrice` - Price to
- `exchange` - name of the exchange
- `symbol` - name of the token
