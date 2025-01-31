---
title: Starton V 2.2
displayed-sidebar: connectSidebar
---
# Starton V 2.2

### What’s new?

**Relayer:**

-   🚀 **Each wallet can now send up to 10k transactions per minute.**

    Transactions are now handled simultaneously freeing your transactions powers. You can now spread 150 times more transactions at a time. [Read more](https://docs.starton.com/connect/api-doc/relayer/transactions).

-   ⛽ **You can now select a gas fee speed for your transaction.**

    According to the transaction's priority, you can choose between low, average, fast, and fastest. Don’t worry, custom gas fees remain available, and you can enter your own value. [Read more](https://docs.starton.com/connect/api-doc/relayer/gas-price).

-   🔍 **More statuses are now available to better understand the state of your transaction.**

    Whether a transaction is in state success, pending, blocked or in error, the status and logs provide you with information on what happened and if needed, which actions are required. [Read more](https://docs.starton.com/connect/services/interact/transaction-state-and-status).

-   ⚖️ **You can now set up how Starton monitors your transactions.**

    Select if you want Starton to help with stuck transactions. You can choose the delay before increasing the gas price and the maximum gas price for the transaction. You can also decide how long you want us to wait before reallocating a nonce.

    To help you with gas prices, a new API is now available. [Read more](https://docs.starton.com/connect/api-doc/relayer/project).

-   📃  **You can now query all the functions available within your smart contract.**

    Thanks to Starton API’s new “available-functions” endpoint, you can query all the view, call, and event functions available for your smart contract. [Read more](https://docs.starton.com/connect/api-doc/relayer/smart-contracts).

Want to get to know our Relayer? At the core of Starton, the Relayer is key to the pre-chain management of all your transactions. Learn more in our [brand-new white paper](https://blog.starton.com/web3-transaction-lifecycle-dab0c9321259).

**Interact:**

-   **You can now interact with your Smart Contracts using the polymorphic functions.**

    Starton Interact now handles polymorphic functions. For the function `approve()` you can use it on your own or with two parameters as such `approve(address,uint256)`:

    -   `address` as the address of the sender to approve
    -   `uint256` as the token allowance approved by the owner

-   **You can now see the ABI parameters from the Interact interface.**

## Resolved issues

-   Fixed an issue with RabbitMQ losing transactions when the workload was too important.
