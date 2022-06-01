---
id: faq
title: FAQ
---

:::tip
If you do not find your question in this list, please submit your question on the <ins>**[Polygon Nightfall discord server](https://discord.com/invite/pZkC3JV2bR)**</ins>.
:::

## Where can I find the Smart Contracts?

Polygon Nightfall contracts have been deployed in [testnet Goerli](../deployments/testnet.md) and [mainnet](../deployments/mainnet.md).

## What's the state of Polygon Nightfall's security audit?
Polygon Nightfall is currently undergoing a security audit that is planned to be finished during Q3. Meanwhile, several restrictions have been added to the protocol:

- Single proposer running, and managed by Polygon
- [Restricted deposit and withdrawal amounts](../tools/nightfall-wallet.md#deposit-and-withdraw-restrictions)

## How do I set up my Nightfall Wallet?
There is a complete wallet tutorial [here](../tools/nightfall-wallet.md) with all details on how to get started with Polygon Nightfall wallet.

## How do I connect a Ledger Hardware Wallet to Nightfall Wallet?
There is a section in the wallet tutorial that explains [how to connect a Ledger Hardware Wallet with Metamask](../tools/nightfall-wallet.md#how-to-connect-a-ledger-hardware-wallet-to-nightfall).

## How long do transfers take on Polygon Nightfall Network from start to finish?
Current proposer takes transactions from users and makes blocks of up to 32 transactions. As soon as enough transactions are collected to build a block, the transaction will be processed.

Additionally, there is an upper limit on the block generation period so that at least one block is proposed every 6 hours (regardless of the number of transactions collected by the proposer).

## Who can I transact with?
To transfer assets within Polygon Nightfall one only needs the `Destination Wallet Address`. Read the wallet tutorial to understand [how to share your Wallet Address](../tools/nightfall-wallet.md#your-wallet-address) to receive funds.

## What are some privacy recommendations?

Some privacy guidelines include:
- Don't deposit a very unique coin value (e.g. 3.1415 USDC) and then withdraw the same amount. People will be able to guess who you probably sent it to. Likewise don't deposit and withdraw exceptionally large values.
- Withdraw different amounts from what you deposit. This makes it harder to guess who you paid.
- Wait awhile. You should ensure that there are at least a few other transactions between the deposit and withdraw. If there are no other transactions in the time you make a deposit and withdraw, people may be able to guess that they are connected.
- Don't make regular or predictable transactions. For example, if a deposit from a particular Ethereum address is always made at 12:01 on the first of the month and a withdraw is always made to a particular Ethereum address at 12:05 on the second of the month people may guess that they are related; you expose yourself to statistical analysis even if the amounts are uncorrelated.

When used correctly, the Polygon Nightfall wallet can provide fully private transfers of ERC20 tokens.

**Privacy of commitments**
Zero Knowledge proofs are computed in the browser, so that your secret keys remain with you, and the wallet keeps track of any commitments that you own, in its IndexedDb. Anyone with access to this data can find out which commitments you own, although they can't steal them without your keys. Keys are only decrypted when you enter the mnemonic. Thus you should only use the wallet on a machine which you trust.

For now, this data is not exported anywhere. Thus, if you use a browser on a different machine, you will not have access to your commitments unless you transfer the IndexedDB contents. We may change this in future, depending on Beta feedback. It's a security versus convenience debate.

**On-chain privacy**
It's important to understand that Deposit and Withdraw transactions are not private. That is because they interact with Layer 1 and Layer 1 is not private. This means that everyone knows if you create a Layer 2 commitment and how much it contains. Likewise, if you return a token back to Layer 1 by destroying a Layer 2 commitment, everyone knows who received it and how much.

Privacy comes entirely from transfers within Layer 2. From the point of view of the Ethereum blockchain, these are fully private. The only data leaked is your IP address when you send a transfer transaction to a Block Proposer. For early Beta, Polygon runs the only Proposers.


## How to withdraw funds?
Funds can be withdrawn with Polygon Nightfall wallet. Withdrawals have a **one week** finalization period from the moment when the block including the withdrawal transaction was created. Once this time period has elapsed, you can finalize the withdrawal to have your funds sent to your Ethereum account.

## How much will transactions cost on Nightfall?
There are two types of transactions that bear different costs:

- On-chain transactions: These transactions are sent to the smart contract and require gas fees on Ethereum to be mined. Any proposer can take this transaction and put it in a block. Currently, `deposit` and `finalize withdrawal` are on-chain transactions.
- Off-chain transactions: These transactions are sent directly to the proposer. Currently, all `transfer` and `withdrawal` are configured as off-chain transactions. These transactions cost `1 MATIC` paid in the PoS network.

## Which tokens can I use on Nightfall Network?
The following tokens are operative on Nightfall:

- MATIC
- WETH
- DAI
- USDC

## Do I need MATIC tokens to use Nightfall?
Yes. You need MATIC on PoS to be able to send off-chain transactions to the proposer.

## Where can I submit a bug report or contact Nightfall for additional help?
Best way is to join our [Polygon Nightfall discord server](https://discord.com/invite/pZkC3JV2bR) and submit your question.