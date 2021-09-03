---
title: Events
---

ArConnect supports several custom events to enable developers to watch the extension from inside of their applications.

### Arweave Wallet Loaded

Triggers when the ArConnect global object (`window.arweaveWallet`) is injected into the page. This can be useful when executing functions on page load.

```ts
window.addEventListener("arweaveWalletLoaded", () => {
  /** Handle ArConnect load event **/
});
```

### Wallet Switched

Triggers when the user switches their wallet in the ArConnect extension popup.

```ts
window.addEventListener("walletSwitch", (e) => {
  const newAddress = e.detail.address;
  /** Handle wallet switch **/
});
```

Requires the `ACCESS_ADDRESS` and the `ACCESS_ALL_ADDRESSES` [permissions](#permissions).