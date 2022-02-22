# Harmony Grant Delivery Report

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

**Selecting** an NFT from the list of available:
![1](assets/1.png)

Approving the bridge smart contract as an *operator* of the selected NFT:
![2](assets/2.png)

After approval, a user can start sending the selected NFT:
![3](assets/3.png)

Signing the Sending transaction and paying the fees:
![4](assets/4.png)

## 2. Viewing the results of the transaction
Bridge pop-up window notifying the user about success:
![5](assets/5.png)

Transaction on the chain of departure (harmony):
```
https://explorer.testnet.harmony.one/tx/0x62b05a8d45e19aea78db50693a22c26fa8fd2192297044c879da5fd80202b160
```
Viewing the transaction in the explorer of the chain of NFT origin:
![6](assets/6.png)

## 2. Receiving NFTs

Viewing the transaction on the chain of destination:
```
https://testnet.snowtrace.io/tx/0x3162d691ab8e8b6937ad328d22a7bf7acf1026d37a56a9b1c95d3bfcf081113b
```
![7](assets/7.png)

NFT is gone from the chain of origin (Harmony):
![8](assets/8.png)
Viewing NFTs on the chain of destination (e.g. Avalance):
![9](assets/9.png)

## 3. Returning a wrapped NFT to Harmony

Selecting a wrapped NFT to be sent 
![10](assets/10.png)
Approving the bridge contract as an operator of the NFT:
![11](assets/11.png)
After approving has succeeded, a user can send the NFT to Harmony:
![12](assets/12.png)
Signing the transaction and paying the fees in 
![13](assets/13.png)
Bridge pop-up window signifying success of the operation:
![14](assets/14.png)
Vewing the transaction in the explorer of the chain of origin (Avalanche):
```
https://testnet.snowtrace.io/tx/0xfd74106bde337d038128b3f6e677dc8d41a95337d01afcb03a9cadddd797faec
```
![15](assets/15.png)
NFTs are gone from Avalanche:
![16](assets/16.png)

## 4. Receiving Native NFT on Harmony

```
https://explorer.testnet.harmony.one/tx/0x628a05dc57869ded05977cbf44e48ce442f7524d08c75b525426b4e8e0e152da
```
![17](assets/17.png)
The NFT has successfully arrived to its native chain:<br/>
![18](assets/18.png)