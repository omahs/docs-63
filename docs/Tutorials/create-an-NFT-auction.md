---
title: How to Sell an NFT in an Auction
---

# How to Sell an NFT in an Auction

In this tutorial, you will learn how to sell an NFT in an Auction.

<div class="row-is-multiline">

<div class="col col--2" class="cards">
	<a class="button-card button-card--vertical" href="https://app.starton.com/projects">
		<h3>Deploy your Smart contracts on the Dashboard</h3>
		<div class="button-card__inner">
			<p color="white">Go to <b>Starton Dashboard</b>, deploy your smart contracts and check all the transactions of your smart contract at one glance.</p>
		</div>
	</a>
</div>

</div>

## Deploy an ERC721

You will start by deploying an ERC721 that will be the base of the NFT you want to sell in an auction.

### Upload Contract-level metadata on IPFS

To enter a name on the marketplace’s dashboard and perceive fees when someone sells one of our NFTs, we need to implement the contract-level metadata.

Here are the values we will use:

```jsx
{
  "name": “My Super NFT on Auction“,
  "description": “You’ve never seen NFTs this beautiful.”,
  "image": "",
  "external_link": "",
  "seller_fee_basis_points": 100,
  "fee_recipient": “PUT YOUR ADDRESS HERE”
}
```

We now have the content of our metadata, we need to upload it on IPFS.

To upload our files on IPFS we will now use the [Starton IPFS](/IPFS/understanding-IPFS.md) pinning service.

As the contract-level metadata only needs to be uploaded once, we can directly do it from [our dashboard](https://app.starton.com/ipfs).

1. Go to **IPFS**.
1. Click **Upload**.
1. Select **JSON**.
1. Enter JSON content.
1. Enter a name for the file.
1. Click **Upload**.

Once done, a column “CID” appears with a value for our file. We will use this data for the Contract Uri Suffix of our smart contract!

### Upload a file on IPFS

We also use IPFS to store the content that will be referenced in our deployed contract.
We do not store the content directly on blockchain as it is too heavy and would induce a very high cost.
The best solution is to store it somewhere else and only store a reference on-chain.

1. Go to **IPFS**.
1. Click **Upload**.
1. Select File(s).
1. Select content.
1. Enter a name for the file.
1. Click **Upload**.

Once our image uploaded, let's upload its metadata so that we can call it from our smart contract function.

### Upload the metadata of your content on IPFS

:::info

Consult the [metadata standard format](https://docs.element.market/welcome-to-element/) on your marketplace's documentation.

:::

1. Go to **IPFS**.
1. Click **Upload**.
1. Select JSON.
1. Select content.
1. Enter a name for the file.
1. Click **Upload**.

Everything we need to sell your NFT is an auction is done.

## Deploy the base contract

We will deploy the contract only once, so we will do it directly from Starton’s dashboard.

We can access the list of templates in the [Smart contract section](/Smart-contract/understanding-smart-contracts.md).

1. Select the ERC721 NFT Smart Contract template.
1. Enter:
    - a name for your contract,
    - a wallet to sign the transaction,
    - a blockchain / network on which to deploy, here BNB testnet.
    - the parameters of our contract.
      For more information on parameters, check out the [Deploying a Smart Contract](/Smart contract/deploying-a-smart-contract).

For example, we can call our contract “Best NFTs on BNB” and deploy it on the BNB Testnet network.

The following constructor parameters are:

-   definitiveName: This name stored on blockchain, we will use “Best NFTs on BNB”.
-   initialTokenUri: This is the public URL that contains the metadata of the collection. Here it starts with ipfs://ipfs/,
-   initialContractUri: The URI of the metadata that will be used to give more details about the description.
-   initialOwnerOrMultisigContract: The address that will own the NFT Collection.

We can finally deploy our contract!

## Deploy an ERC721 Auction

We will deploy the contract only once, so we will do it directly from Starton’s dashboard.

We can access the list of templates in the [Smart contract section](/Smart-contract/understanding-smart-contracts.md).

1. Select the ERC721 Auction template.
1. Enter:

-   **definitiveTokenAddress**: The token address of the ERC721 that you want to sell.
-   **definitiveFeeReceiver**: The address that will receive all the price paid to mint the NFTs.
-   **initialStartingPrice**: The initial price that the NFT will be sold for.
-   **initialMinPriceDifference**: The price increase that a user needs to at least put to bid on top of the current auction winner.
-   **initialStartTime**: The time when the sale will begin and users can bid.
-   **initialEndTime**: The time when the sale will end and users couldn't bid anymore.
-   **initialTokenURI**: The URI that will be append in the end of the base token URI for the token that will be minted.

### Interact with your contract

You can now bid, claim, or start a new auction. The mint of your NFT is made when the bidder which has won the auction claims it.
