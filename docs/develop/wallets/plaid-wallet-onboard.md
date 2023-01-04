---
id: plaid-wallet-onboard
title: Plaid Wallet Onboard
description: Easily connect your dApp to hundreds of self-custody wallets.
keywords:
  - wiki
  - polygon
  - wallet
  - dapp
  - integrate
  - guide
image: https://wiki.polygon.technology/img/polygon-wiki.png
---

import useBaseUrl from '@docusaurus/useBaseUrl';

**Plaid Wallet Onboard** lets you integrate multiple wallets such as Coinbase Wallet, Metamask, and more into your dApp.

Wallet Onboard can be configured to automatically ensure users have their wallet setup to use Polygon.

<div align="center">
<img width="603" src={useBaseUrl("img/plaid-wallet-onboard/splash.png")} />
</div>

## Installation and Prerequisites

Wallet Onboard can be used in any JavaScript web dApp, and there is a [React library](https://github.com/plaid/react-plaid-link#usage-with-wallet-onboard) for React applications as well.

You can read about the entire setup and installation process in the [Wallet Onboard docs](https://plaid.com/docs/wallet-onboard/add-to-app/#enable-wallet-onboard-and-retrieve-a-link-token).

## Integrating with Polygon

Wallet Onboard returns an [EIP-1193](https://eips.ethereum.org/EIPS/eip-1193) provider that your dApp can use to request the user’s addresses as well as signatures and transactions.

Here's a simple example of the code used to integrate Wallet Onboard on Polygon Mainnet in a vanilla JavaScript dApp:

```html
<script src="https://cdn.plaid.com/link/v2/stable/link-initialize.js"></script>

<script>
  const plaidWeb3 = await Plaid.web3();
  const handler = plaidWeb3.createEthereumOnboarding({
    // retrieve from Plaid Dashboard
    token: 'token-abc',
    chain: {
      rpcUrl: 'https://polygon-rpc.com/',
      chainId: '0x89',
    },
    onSuccess: async (provider) => {
      const accounts = await provider.request({ method: 'eth_accounts' });
    }
  });

  handler.open();
</script>
```

If a user connects their wallet and it is not using Polygon, Wallet Onboard will attempt to add or switch to Polygon automatically, or will instruct the user to switch.

<div align="center">
<img width="244" src={useBaseUrl("img/plaid-wallet-onboard/switch.png")} />
</div>

For a complete overview of the configuration options and capabilities of Wallet Onboard, refer to [its docs](https://plaid.com/docs/wallet-onboard/).
