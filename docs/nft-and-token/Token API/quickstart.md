---
sidebar_label: "Quickstart"
sidebar_position: 1
---

# Token API Quickstart

A new developer's guide to using the Token API and mastering how to get token information. Learn how to query Token data using alchemy-web3 (recommended), fetch, or axios.

---

With the Token API, you can easily request information on specific tokens such as metadata or balances. Alchemy currently supports the following Token API Endpoints:

- [`alchemy_getTokenAllowance`](https://www.alchemy.com): Returns the amount which the sender is allowed to withdraw from the owner.
- `alchemy_getTokenBalances`: Returns ERC20 token balances for all tokens the given address has ever transacted in with. Optionally accepts a list of contracts.
- `alchemy_getTokenMetadata`: Returns metadata (name, symbol, decimals, logo) for a given token contract address.
