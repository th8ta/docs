---
title: Permissions
---

There are 8 permissions currently available. When calling `connect`, you need to specify at least one of them, commonly `ACCESS_ADDRESS`.

```ts
"ACCESS_ADDRESS"
```
Access the current address selected in ArConnect

```ts
"ACCESS_PUBLIC_KEY"
```
Access the public key of the current address selected in ArConnect

```ts
"ACCESS_ALL_ADDRESSES"
```
Access all addresses added to ArConnect

```ts
"SIGN_TRANSACTION"
```
Sign a transaction

```ts
"ENCRYPT"
```
Encrypt data with the user's keyfile

```ts
"DECRYPT"
```
Decrypt data with the user's keyfile

```ts
"SIGNATURE"
```
Sign data with the user's keyfile

```ts
"ACCESS_ARWEAVE_CONFIG"
```
Access the user's custom Arweave config