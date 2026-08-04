# PolygonScan

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
