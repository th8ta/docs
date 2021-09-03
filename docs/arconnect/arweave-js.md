---
title: ArweaveJS API
---

You can interact with basic ArConnect functionalities using [`arweave-js`](https://npmjs.com/arweave). To create a transaction, you just *don't* pass in the user's wallet instance:

```ts
const tx = await arweave.createTransaction({
  /* config */
});
```

Then you can use ArConnect to add the user's wallet to the transaction and sign it (as before, you don't pass in the user's wallet instance, that is done by ArConnect):

```ts
await arweave.transactions.sign(tx);
```

Done! Now you can post the transaction.