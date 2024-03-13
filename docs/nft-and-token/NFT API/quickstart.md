---
sidebar_label: "Quickstart"
sidebar_position: 1
---

# NFT API Quickstart

Go from zero to hero with the Alchemy NFT API. Learn how to query NFT data, then dive into some fun tutorials!

---

## Getting Started Instructions

Follow along with the steps below to get started with the NFT API:

1. Choose a package manager
2. Set up your repo
3. Choose a library
   1. Alchemy SDK (recommended)
   2. Node-Fetch
   3. Axios

### 1. Choose a package manager

For this guide, we will be using `npm` or `yarn` as our package manager to install either `alchemy-sdk`, `fetch`, or `axios`.

### npm

To get started with npm, follow the documentation to install Node.js and npm for your operating system: https://docs.npmjs.com/downloading-and-installing-node-js-and-npm

### yarn

To get started with yarn, follow these steps: https://classic.yarnpkg.com/lang/en/docs/install

### 2. Set up your repo

### npm

Open up a terminal, and from the command line, create a new repository to hold your quickstart scripts. We'll also initialize the repo as an npm project.

```
mkdir alchemy-nft-api
cd alchemy-nft-api
npm init --yes
```

> ### 📘 Support Import Syntax
>
> Since we'll be using import syntax to load ES6 modules, add `'type': 'module'` to your `package.json` file:
>
> ```js
> // package.json
> {
>   ...
>   "type": "module"
> }
> ```
>
> See this discussion for more context.

:::note

Some **content** with _Markdown_ `syntax`. Check [this `api`](#).

:::

:::tip

Some **content** with _Markdown_ `syntax`. Check [this `api`](#).

:::

:::info

Some **content** with _Markdown_ `syntax`. Check [this `api`](#).

:::

:::warning

Some **content** with _Markdown_ `syntax`. Check [this `api`](#).

:::

:::danger

Some **content** with _Markdown_ `syntax`. Check [this `api`](#).

:::

```js title="alchemy-sdk-script.js"
// This script demonstrates access to the NFT API via the Alchemy SDK.
import { Network, Alchemy } from "alchemy-sdk";

// Optional Config object, but defaults to demo api-key and eth-mainnet.
const settings = {
  apiKey: "demo", // Replace with your Alchemy API Key.
  network: Network.ETH_MAINNET, // Replace with your network.
};

const alchemy = new Alchemy(settings);

// Print owner's wallet address:
const ownerAddr = "vitalik.eth";
console.log("fetching NFTs for address:", ownerAddr);
console.log("...");

// Print total NFT count returned in the response:
const nftsForOwner = await alchemy.nft.getNftsForOwner("vitalik.eth");
console.log("number of NFTs found:", nftsForOwner.totalCount);
console.log("...");

// Print contract address and tokenId for each NFT:
for (const nft of nftsForOwner.ownedNfts) {
  console.log("===");
  console.log("contract address:", nft.contract.address);
  console.log("token ID:", nft.tokenId);
}
console.log("===");

// Fetch metadata for a particular NFT:
console.log("fetching metadata for a Crypto Coven NFT...");
const response = await alchemy.nft.getNftMetadata(
  "0x5180db8F5c931aaE63c74266b211F580155ecac8",
  "1590"
);

// Uncomment this line to see the full api response:
// console.log(response);

// Print some commonly used fields:
console.log("NFT name: ", response.title);
console.log("token type: ", response.tokenType);
console.log("tokenUri: ", response.tokenUri.gateway);
console.log("image url: ", response.rawMetadata.image);
console.log("time last updated: ", response.timeLastUpdated);
console.log("===");
```
