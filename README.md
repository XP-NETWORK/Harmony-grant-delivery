# Harmony Grant Delivery Report

The present report documents integrating Harmony Testnet into XP.network Multi-Chain NFT Bridge.

Harmony is assigned the internal bridge nonce #12:
```typescript
export const HARMONY: Web3Nonce = 0xc;
```

1. The other Bridge related smart contract addresses: https://docs.xp.network/docs/Testnet/smartContracts
2. The XP.network NFT Bridge in the testnets of blockchains is available at: https://testnet.bridge.xp.network/

![Testnet Bridge](assets/TestnetChains.png)

## Bridge Smart Contracts Deployed on Harmony Testnet

Creator address: one1p47lggq5qe9pv00a5szz20af76yrhyv8r6e346

| SC Name / Type | Address|
|:-:|:-:|
|UserNftMinter|0x57d2Ad1a14C77627D5f82B7A0F244Cfe391e59C5 <br/> one12lf26xs5camz040c9daq7fzvlcu3ukw9txkkkd|
|Erc1155Minter|0xbED4a5b36fae07943589a0b34CC2Ec3a1c208E53 <br/> one1hm22tvm04cregdvf5ze5eshv8gwzprjn20frdv|
|XPNft1155|0x7cB14C4aB12741B5ab185C6eAFb5Eb7b5282A032 <br/> one10jc5cj43yaqmt2cct3h2ld0t0dfg9gpjrxgkjn|
|XPNft|0x0AA29baB4F811A9f3dcf6a0F9cAEa9bE18ECED78 <br/> one1p23fh260sydf70w0dg8eet4fhcvwemtcmknt67|
|Minter|0xCbA56d441da86dEfe31d3AdDeEc2bA04f7e27d9e <br/> one1ewjk63qa4pk7lcca8tw7as46qnm7ylv7exqnh3|

## 1. Sending NFTs

<br/>

1.1 **Selecting** an NFT from the list of available:<br/>
![1](assets/1.png)

<br/>
1.2 Approving the bridge smart contract as an *operator* of the selected NFT:<br/>

![2](assets/2.png)

<br/>
1.3 After approval, a user can start sending the selected NFT:<br/>

![3](assets/3.png)

<br/>
1.4. Signing the Sending transaction and paying the fees:<br/>

![4](assets/4.png)

## 2. Viewing the results of the transaction
<br/>
2.1 Bridge pop-up window notifying the user about success:<br/>

![5](assets/5.png)

<br/>
2.2 Transaction on the chain of departure (harmony):<br/>

```
https://explorer.testnet.harmony.one/tx/0x62b05a8d45e19aea78db50693a22c26fa8fd2192297044c879da5fd80202b160
```

<br/>
2.3 Viewing the transaction in the explorer of the chain of NFT origin:<br/>

![6](assets/6.png)

## 3. Receiving NFTs

<br/>
3.1 Viewing the transaction on the chain of destination:<br/>

```
https://testnet.snowtrace.io/tx/0x3162d691ab8e8b6937ad328d22a7bf7acf1026d37a56a9b1c95d3bfcf081113b
```
![7](assets/7.png)

<br/>
3.2 NFT is gone from the chain of origin (Harmony):<br/>

![8](assets/8.png)

<br/>
3.3 Viewing NFTs on the chain of destination (e.g. Avalance):<br/>

![9](assets/9.png)

## 4. Returning a wrapped NFT to Harmony

<br/>
4.1 Selecting a wrapped NFT to be sent <br/>

![10](assets/10.png)
<br/>
4.2 Approving the bridge contract as an operator of the NFT:<br/>

![11](assets/11.png)

<br/>
4.3 After approving has succeeded, a user can send the NFT to Harmony:<br/>

![12](assets/12.png)

<br/>
4.4 Signing the transaction and paying the fees in <br/>

![13](assets/13.png)

<br/>
4.5 Bridge pop-up window signifying success of the operation:<br/>

![14](assets/14.png)
<br/>
4.6 Vewing the transaction in the explorer of the chain of origin (Avalanche):<br/>
```
https://testnet.snowtrace.io/tx/0xfd74106bde337d038128b3f6e677dc8d41a95337d01afcb03a9cadddd797faec
```
<br/>

![15](assets/15.png)

<br/>
4.7 NFTs are gone from Avalanche:<br/>

![16](assets/16.png)

## 5. Receiving Native NFT on Harmony

5.1 Viewing the transaction in the destination chain explorer (Harmony):
```
https://explorer.testnet.harmony.one/tx/0x628a05dc57869ded05977cbf44e48ce442f7524d08c75b525426b4e8e0e152da
```
![17](assets/17.png)

<br/>
5.2The NFT has successfully arrived to its native chain:<br/>

![18](assets/18.png)

# Adding Harmony to the mainnet

## Milestone Delivery

|#|Milestone|Deliverables|
|:-:|:-:|:-|
|1|Smart contracts|1. [Support ERC-721](https://github.com/XP-NETWORK/XP.network-HECO-Migration/blob/dist/dist/BridgeNFT.d.ts)<br/>2. [Support ERC-1155](https://github.com/XP-NETWORK/XP.network-HECO-Migration/blob/dist/dist/Erc1155Minter.d.ts)<br/>3. [Freeze/Unfreeze Native NFTs](https://github.com/XP-NETWORK/XP.network-HECO-Migration/blob/f474704150da557f931e011026d0c033b391bd7a/dist/Minter.d.ts#L160)<br/>4. [Mint/Burn wrapped NFTs](https://github.com/XP-NETWORK/XP.network-HECO-Migration/blob/f474704150da557f931e011026d0c033b391bd7a/dist/Minter.d.ts#L160)<br/>5. [Pay the TX fees on the target chain in native tokens](https://github.com/XP-NETWORK/XP.network-HECO-Migration/blob/f474704150da557f931e011026d0c033b391bd7a/dist/Minter.d.ts#L295)<br/>6. [Send / Receive NFTs in batches](https://github.com/XP-NETWORK/XP.network-HECO-Migration/blob/dist/dist/BridgeNFTBatch.d.ts)|
|2|Integration into Validators|We've added Harmony to the [Validators](https://github.com/XP-NETWORK/migration-validator/search?q=Harmony)|
|3|Backend Integration|1. [NFT Index](#nft-indexing-for-harmony)<br/>2. TX Fee Estimator<br/>3. Crypto-currency converter|
|4|UI Integration|1. [User Interface](#mainnet-ui-integration)<br/>2. [Wallets (Metamask, WalletConnect)](#wallets-support)|

## Mainnet UI Integration

Harmony can be found the [production version of the bridge](https://bridge.xp.network/) connecting 14+ blockchain mainnets.

![Harmony Mainnet](./assets/harmony-mainnet.png)

### Wallets Support

Harmony is supported though Metamask & WalletConnect (for the mobile interaction)
![Wallets](assets/wallets.png)

Switching Metamask to Harmony:
![switching to Harmony](assets/switshing-to-harmony.png)

### NFT Indexing for Harmony

![NFT Indexing](assets/harmony-nfts.jpg)

## Mainnet transactions

1.1. Sending an NFT Polygon -> Harmony
![Polygon - Harmony](assets/polygon-harmony-success.jpg)
Transaction on Polygon: [0x31fc6ea9493fb85e7c6b0ce6d22b8fc2172840bd5b9222c629f50007ac3046f7](https://polygonscan.com/tx//0x31fc6ea9493fb85e7c6b0ce6d22b8fc2172840bd5b9222c629f50007ac3046f7)

![Polygon-Harmony-tx](./assets/Polygon-Harmony-tx.png)

1.2 Destination Transaction on Harmony: [0x35533f9b3c97e7ced6ebeb14cb90b954e1131c02b15b2a635923cd827e4ae973](https://explorer.harmony.one/tx/0x35533f9b3c97e7ced6ebeb14cb90b954e1131c02b15b2a635923cd827e4ae973)

![Arrival on Harmony](./assets/harmony-receipt.png)

2.1 Sending from Harmony -> Polygon

![Harmony to Polygon](./assets/harmony-polygon.jpg)

Transaction on Harmony: [0x290e695463e621f46405f3edd8caf4cc70173182c3a35cea1c1f07c065eb11fc](https://explorer.harmony.one/tx/0x290e695463e621f46405f3edd8caf4cc70173182c3a35cea1c1f07c065eb11fc)

![Sending from Harmony](./assets/harmony-sending.png)

2.2. Receiving on Polygon

Transaction on Polygon: [0xe8db8d1dd9a5e08798727727b2e17c4242955a5c9f5285b9aafee8247acaec5f](https://polygonscan.com/tx/0xe8db8d1dd9a5e08798727727b2e17c4242955a5c9f5285b9aafee8247acaec5f)

![Receiving on Polygon](./assets/polygon-receiving.png)