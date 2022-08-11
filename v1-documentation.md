# Documentation

All Spice Trade Swap pairs consist of two different tokens.

Results are cached for 5 minutes (or 300 seconds).

## [`/summary`](https://api56.spicetrade.ai/api/summary)

Returns data for the top ~1000 Spice Trade Swap pairs, sorted by reserves. 

### Request

`GET https://api56.spicetrade.ai/api/summary`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "0x..._0x...": {                  // BEP20 token addresses, joined by an underscore
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // last 24h volume denominated in token0
      "quote_volume": "...",          // last 24h volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_USDS": "..."          // liquidity denominated in USDS
    },
    // ...
  }
}
```

## [`/tokens`](https://api56.spicetrade.ai/api/tokens)

Returns the tokens in the top ~1000 pairs on Spice Trade Swap, sorted by reserves.

### Request

`GET https://api56.spicetrade.ai/api/tokens`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "0x...": {                        // the address of the BEP20 token
      "name": "...",                  // not necessarily included for BEP20 tokens
      "symbol": "...",                // not necessarily included for BEP20 tokens
      "price": "...",                 // price denominated in USD
      "price_USDS": "...",             // price denominated in USDS
    },
    // ...
  }
}
```

## [`/tokens/0x...`](https://api56.spicetrade.ai/api/tokens/0xde7d1ce109236b12809c45b23d22f30dba0ef424)

Returns the token information, based on address.

### Request

`GET https://api56.spicetrade.ai/api/tokens/0xde7d1ce109236b12809c45b23d22f30dba0ef424`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "name": "...",                    // not necessarily included for BEP20 tokens
    "symbol": "...",                  // not necessarily included for BEP20 tokens
    "price": "...",                   // price denominated in USD
    "price_USDS": "...",               // price denominated in USDS
  }
}
```

## [`/pairs`](https://api56.spicetrade.ai/api/pairs)

Returns data for the top ~1000 Spice Trade Swap pairs, sorted by reserves.

### Request

`GET https://api56.spicetrade.ai/api/pairs`

### Response

```json5
{
  "updated_at": 1234567,              // UNIX timestamp
  "data": {
    "0x..._0x...": {                  // the asset ids of USDS and BEP20 tokens, joined by an underscore
      "pair_address": "0x...",        // pair address
      "base_name": "...",             // token0 name
      "base_symbol": "...",           // token0 symbol
      "base_address": "0x...",        // token0 address
      "quote_name": "...",            // token1 name
      "quote_symbol": "...",          // token1 symbol
      "quote_address": "0x...",       // token1 address
      "price": "...",                 // price denominated in token1/token0
      "base_volume": "...",           // volume denominated in token0
      "quote_volume": "...",          // volume denominated in token1
      "liquidity": "...",             // liquidity denominated in USD
      "liquidity_USDS": "..."          // liquidity denominated in USDS
    },
    // ...
  }
}
```
