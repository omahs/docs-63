---
title: ERC1155 NFT Sale
description: The smart contract standard to manage unique tokens.
keywords: [ERC-1155, ERC1155, Deploy, Starton, Smart contracts, parameters, functions]
---

# ERC1155 NFT Sale

<p>The smart contract to help you sell ERC1155 tokens.In a video game, you can sell a piece of equipment to another player.</p>
	<p>The sale version enables you to mint a new token and sell it to your users. It helps you set up a whole sale choosing when it starts and ends, set a maximum number of tokens that can be sold in total or to the same user.</p>
	<p>Notice that you must set the price of the tokens you want to sell after creating the contract by calling the setPrices function.</p>

## Parameters

<ul>
	<li><strong>definitiveTokenAddress:</strong> The token address of the ERC721 that you want to sell</li>
	<li><strong>definitiveStartTime: </strong> The time when the sale will begin and users can mint tokens</li>
	<li><strong>definitiveEndTime: </strong> The time when the sale will end and users couldn't mint anymore tokens</li>
	<li><strong>definitiveMaxTokensPerAddress: </strong> The maximum amount of tokens that can be minted by a single address</li>
	<li><strong>definitiveMaxSupply: </strong> The maximum amount of tokens that can be minted during the sale</li>
	<li><strong>definitiveFeeReceiver: </strong> The address that will receive all the price paid to mint the NFTs</li>
	</ul>

## Functions

| Function            | Input Parameters                                             | Description                                                                                                                                                                                      |
| ------------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| token               | None                                                         | Returns the NFT contract where the new tokens will be minted at.                                                                                                                                 |
| pricePerToken       | (uint256)                                                    | Returns the price of the selected token                                                                                                                                                          |
| startTime           | None                                                         | Returns the start time of the sale.                                                                                                                                                              |
| endTime             | None                                                         | Returns the end time of the sale.                                                                                                                                                                |
| maxTokensPerAddress | None                                                         | Returns the max number of tokens that a address can mint.                                                                                                                                        |
| leftSupply          | None                                                         | The left amount of token that can be minted during this sale.                                                                                                                                    |
| tokensClaimed       | (address)                                                    | The amount of token claimed per address                                                                                                                                                          |
| mint                | (address to, uint256 id, uint256 amount)                     | Mint nth new tokens to a specific address from the token collection with the given id. Notice the minter must send the required amount defined by price times the amount of tokens minted.       |
| mintBatch           | (address to, uint256[] memory ids, uint256[] memory amounts) | Batch mint nth new tokens to a specific address from the token collection with the given id. Notice the minter must send the required amount defined by price times the amount of tokens minted. |
| withdraw            | None                                                         | Withdraw the price paid for the mints                                                                                                                                                            |
| setPrices           | (uint256[] memory ids, uint256[] memory prices)              | Set the prices of a list of tokens by a list of prices.                                                                                                                                          |
