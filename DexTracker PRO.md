# DexTracker PRO

Private API endpoint to get fastest information with no limits

**Current Price**: $200/month
**Contacts**: [https://t.me/daniil_jave](https://t.me/daniil_jave)

## Listen All DEX Trades

You can listen all dex transactions by one request

**Supported networks**: sol, eth, bsc, base, tron

```
wss://api.cryptoscan.pro/v1/listen?type=dex
```

## Listen All CEX Trades

You can listen all cex transactions by one request

**Supported exchanges**: mexc, mexc-futures, binance, bingx, bitget, bybit, bitmart, coinbase, coinex, digifinex, gate, htx, kucoin, kucoin-futures, lbank, lbank-futures, okx, okx-futures, phemex, poloniex, upbit, xt, yobit

```
wss://api.cryptoscan.pro/v1/listen?type=cex
```

## Listen New CEX Listings

You can listen new token listings on CEX with no delay

**Supported exchanges**: mexc, mexc-futures, binance, bingx, bitget, bybit, bitmart, coinbase, coinex, digifinex, gate, htx, kucoin, kucoin-futures, lbank, lbank-futures, okx, okx-futures, phemex, poloniex, upbit, xt, yobit

```
wss://api.cryptoscan.pro/v1/listen?type=listings
```

## Networks API

Get information about enabled/disabled networks on tokens from any exchange

**Supported exchanges**: mexc, mexc-futures, binance, bingx, bitget, bybit, bitmart, coinbase, coinex, digifinex, gate, htx, kucoin, kucoin-futures, lbank, lbank-futures, okx, okx-futures, phemex, poloniex, upbit, xt, yobit

```
https://api.cryptoscan.pro/v1/networks?exchange=
```

## Request parameters

- `exchange` - mexc, mexc-futures, binance, bingx, bitget, bybit, bitmart, coinbase, coinex, digifinex, gate, htx, kucoin, kucoin-futures, lbank, lbank-futures, okx, okx-futures, phemex, poloniex, upbit, xt, yobit

## Response parameters

- `symbol` - example: BTC_USDT
- `exchange` - example: mexc
