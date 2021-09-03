---
title: Additional Functions
---

ArConnect supports much more with its powerful API. These features are not integrated into arweave-js, but please let us know if you would like to see them added. You can access all of these using the global `window.arweaveWallet` object (`window.arweaveWallet.getActiveAddress()`, etc.).

All of these functions are asynchronous, so you will need to `await` them. If you are using Typescript, read [this](#typescript-types) for type declarations.

### Connect

```ts
connect(permissions, appInfo?)
```

Connect to ArConnect and request permissions. This function can always be called again if you want to request more permissions for your site. See the available permissions [here](#permissions).

- `permissions`: An array of [permissions](#permissions)
- `appInfo`: Optional information about your application (see the [format](#app-info))

#### App info

```ts
{
  name?: string; // optional application name
  logo?: string; // optional application logo
}
```

### Disconnect

```ts
disconnect()
```

Disconnect from ArConnect. Removes all permissions from your site.

### Get Active Address

```ts
getActiveAddress(): Promise<string>
```

Get the current wallet address in the extension.

- `returns`: A wallet address

Requires the `ACCESS_ADDRESS` [permission](#permissions).

### Get Active Public Key

```ts
getActivePublicKey(): Promise<string>
```

Get the user's active public key from their wallet.

- `returns`: The active public key

Requires the `ACCESS_PUBLIC_KEY` [permission](#permissions).

### Get All Addresses

```ts
getAllAddresses(): Promise<string[]>
```

Get all addresses added to the ArConnect extension.

- `returns`: A list of the added wallets' addresses

Requires the `ACCESS_ALL_ADDRESSES` [permission](#permissions).

### Get Wallet Names

```ts
getWalletNames(): Promise<{ [addr: string]: string }>
```

Get wallet names for addresses.

- `returns`: An object with addresses and wallet names

Requires the `ACCESS_ALL_ADDRESSES` [permission](#permissions).

### Sign

```ts
sign(transaction, options?): Promise<Transaction>
```

Sign a transaction. This is a raw version of what is used in the `arweave-js` [API](#api).

- `transaction`: A valid Arweave transaction without a wallet keyfile added to it
- `options`: Arweave signing options
  <br />
- `returns`: Signed transaction instance

Requires the `SIGN_TRANSACTION` [permission](#permissions).

### Encrypt

```ts
encrypt(data, options): Promise<Uint8Array>
```

Encrypt a string with the user's wallet.

- `data`: String to encrypt
- `options`: Encrypt [options](#encryption-options)
  <br />
- `returns`: Encrypted string

Requires the `ENCRYPT` [permission](#permissions).

#### Encryption options

```ts
{
  algorithm: string; // encryption algorithm
  hash: string; // encryption hash
  salt?: string; // optional salt
}
```

TODO: Supported algorithms

### Decrypt

```ts
decrypt(data, options): Promise<string>
```

Decrypt a string [encrypted](#encryptdata-options-promiseuint8array) with the user's wallet.

- `data`: `Uint8Array` data to decrypt to a string
- `options`: Decrypt [options](#encryption-options)
  <br />
- `returns`: Decrypted string

Requires the `DECRYPT` [permission](#permissions).

### Signature

```ts
signature(data, options): Promise<string>
```

Get the signature for a data array.

- `data`: `Uint8Array` data to get the signature for
- `options`: Signature options
  <br />
- `returns`: Signature

Requires the `SIGNATURE` [permission](#permissions).

### Get Permissions

```ts
getPermissions(): Promise<PermissionType[]>
```

Get the [permissions](#permissions) allowed for you site by the user.

- `returns`: A list of [permissions](#permissions) allowed for your dApp

### Get Arweave Config

```ts
getArweaveConfig(): Promise<ArweaveConfig>
```

Get the user's custom [Arweave config](#arweave-config) set in the extension.

- `returns`: Custom [Arweave config](#arweave-config)

Requires the `ACCESS_ARWEAVE_CONFIG` [permission](#permissions).

### Add Token

```ts
addToken(id)
```

Add a token to ArConnect (if it is not already present).

- `id`: Token contract ID