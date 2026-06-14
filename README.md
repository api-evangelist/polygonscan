# PolygonScan

PolygonScan is the leading blockchain explorer, search, API, and analytics platform for the Polygon PoS network (Chain ID 137). It provides a comprehensive REST API for querying on-chain data including account balances, transactions, token transfers, smart contract source code and ABI, event logs, gas prices, and network statistics.

API access has been unified under Etherscan API V2, enabling a single API key to access 60+ EVM-compatible chains by passing a `chainid` parameter.

## API Base URL

**V2 (current):** `https://api.etherscan.io/v2/api?chainid=137`

**Legacy (deprecated Aug 15, 2025):** `https://api.polygonscan.com/api`

**Amoy Testnet:** `https://api-amoy.polygonscan.com/api` (chainid=80002)

## Authentication

All requests require an `apikey` query parameter. Obtain a free API key at [polygonscan.com/myapikey](https://polygonscan.com/myapikey).

Without a key, requests are limited to 1 call per 5 seconds.

## API Modules

| Module | Description |
|--------|-------------|
| `account` | POL/MATIC balances, normal and internal transactions, ERC-20/721/1155 token transfers |
| `contract` | Smart contract ABI, source code, creation details, verification |
| `transaction` | Transaction execution status, receipt status |
| `block` | Block rewards, block number by timestamp, countdown to block |
| `logs` | Filtered event logs by address and topics |
| `token` | ERC-20 token info, total supply, holder lists (PRO) |
| `stats` | POL total supply, POL price, validator set size |
| `gastracker` | Gas oracle, gas estimation, confirmation times |
| `proxy` | JSON-RPC proxy methods (eth_blockNumber, eth_getBalance, eth_call, etc.) |

## Rate Limits

| Plan | Calls/Second | Daily Calls | Price |
|------|-------------|-------------|-------|
| Free | 5 | 100,000 | $0/mo |
| Lite | 5 | 100,000 | $49/mo |
| Standard | 10 | 200,000 | $199/mo |
| Advanced | 20 | 500,000 | $299/mo |
| Professional | 30 | 1,000,000 | $399/mo |
| Pro Plus | 30 | 1,500,000 | $899/mo |

## Quick Start

```
GET https://api.etherscan.io/v2/api
  ?chainid=137
  &module=account
  &action=balance
  &address=0x...
  &tag=latest
  &apikey=YourApiKey
```

## Resources

- [Explorer](https://polygonscan.com/)
- [API Documentation](https://docs.etherscan.io/etherscan-v2)
- [API Registration](https://polygonscan.com/myapikey)
- [Rate Limits & Errors](https://info.polygonscan.com/api-return-errors/)
- [API Terms](https://polygonscan.com/apiterms)
- [V2 Migration Guide](https://docs.etherscan.io/v2-migration)
- [Contact / Support](mailto:apisupport@etherscan.io)
