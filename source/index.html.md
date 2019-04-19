---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - Usage

toc_footers:
  # - <a href='#'>Sign Up for a Developer Key</a>

includes:
  # - errors

search: true
---

# Introduction

Welcome to the React Native Elastos Wallet Bridges! You can use our bridges in javascript to access Elastos Wallet Core RPC endpoints, which can interact with Elastos Blockchain.

You can view usage in the dark area to the right.

# Wallet Bridges

## GenerateMnemonic

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

// Generate a new mnemonic (defaults to English)
RNElastosMainchain.GenerateMnemonic((err, mnemonic) => {
  console.log(mnemonic);
});
```
<!-- > Output Example:
```javascript
cry mechanic bean they discover vendor couple adapt walk room edit dinner
``` -->

This bridge returns a new mnemonic to create a new wallet.

## ImportWalletWithMnemonic

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.ImportWalletWithMnemonic(mnemonic, (err, res) => {
  console.log(res); //expect "success"
});
```

This bridge imports existing wallet using its mnemonic. Every wallet have its mnemonic so you can import any wallet you already created in web wallet or everywhere.

### Parameters

Parameter | Description
--------- | -----------
mnemonic | mnemonic of the wallet you're going to import

## ExportWalletWithMnemonic

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.ExportWalletWithMnemonic(payPassword, (err, walletStr) => {
  console.log(walletStr);
});
```

This bridge exports current wallet.

### Parameters

Parameter | Description
--------- | -----------
payPassword | payPassword of current wallet

## CreateWallet

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.CreateWallet(mnemonic, (err, res) => {
  console.log(res); //expect "success"
});
```

This bridge creates a new wallet using given mnemonic.

### Parameters

Parameter | Description
--------- | -----------
mnemonic | mnemonic of the wallet you're going to create

## CreateMultiSignMasterWallet

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.CreateMultiSignMasterWallet(masterWallet, privKey, payPassword, coSigners, requiredSignCount, (err, res) => {
  console.log(res); //expect "success"
});
```

This bridge creates a multi-sign wallet.

### Parameters

Parameter | Description
--------- | -----------
masterWallet | string of one of masterWallet which is participated in Multi-Sign
privKey | masterWallet privKey
payPassword | masterWallet payPassword
coSigners | string of coSigners
requiredSignCount | count(int) of required Sign

## CreateAddress

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.CreateAddress((err, newAddress) => {
  console.log(newAddress);
});
```

This bridge creates a new wallet address.

## IsAddressValid

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.IsAddressValid(address, (err, res) => {
  console.log(res); //expect "true" if the address is valid, "false" if it is invalid
});
```

This bridge validates the given address.

### Parameters

Parameter | Description
--------- | -----------
address | The address which should be validated

## GetPublicKey

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.GetPublicKey((err, publicKey) => {
  console.log(publicKey);
});
```

This bridge returns a public key of current wallet.

## GetMultiSignPubKeyWithMnemonic

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.GetMultiSignPubKeyWithMnemonic((err, multiSignPubKey) => {
  console.log(multiSignPubKey);
});
```

This bridge returns the multi-sign public key using current wallet mnemonic.

## GetMultiSignPubKeyWithPrivKey

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.GetMultiSignPubKeyWithPrivKey(privKey, (err, multiSignPubKey) => {
  console.log(multiSignPubKey);
});
```

This bridge returns the multi-sign public key using given privKey.

### Parameters

Parameter | Description
--------- | -----------
privKey | The private key which should be participated in multi-sign

## GetSupportedChains

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.GetSupportedChains((err, supportedChains) => {
  console.log(supportedChains);
});
```

This bridge returns the supported chains of the current wallet.
The return value is the string of string array.

## ChangePassword

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.ChangePassword(oldPassword, newPassword, (err, res) => {
  console.log(res); //expect "success"
});
```

This bridge sets new password of the current wallet.

### Parameters

Parameter | Description
--------- | -----------
oldPassword | current password of the wallet
newPassword | new password of the wallet

## GetBalance

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.GetBalance(balanceType, (err, balance) => {
  console.log(balance);
});
```

This bridge returns the balance of the current wallet.

### Parameters

Parameter | Description
--------- | -----------
balanceType | enum type -> 0 : Default, 1 : Voted, 2 : Total

## GetBalanceInfo

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.GetBalanceInfo((err, balanceInfo) => {
  console.log(balanceInfo);
});
```

This bridge returns the balance information of the current wallet.

## GetBalanceWithAddress

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.GetBalanceWithAddress(address, balanceType, (err, balance) => {
  console.log(balance);
});
```

This bridge returns the balance of the address of the current wallet.

### Parameters

Parameter | Description
--------- | -----------
address | address
balanceType | enum type -> 0 : Default, 1 : Voted, 2 : Total

## GetAllAddress

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.GetAllAddress((err, allAddress) => {
  console.log(allAddress);
});
```

This bridge returns all addresses of the current wallet.
The return value is the string of JSONArray.

## GetAllTransaction

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.GetAllTransaction((err, transactionHistory) => {
  console.log(transactionHistory);
});
```

This bridge returns all transactions of the current wallet.
The return value is the string of JSONArray.

## Send

```javascript
import RNElastosMainchain from 'react-native-elastos-wallet-core';

RNElastosMainchain.CreateMultiSignMasterWallet(amount, toAddress, useVotedUTXO, (err, transactionId) => {
  console.log(transactionId);
});
```

This bridge sends given amount of tokens to the given address and returns the published transaction Id.

### Parameters

Parameter | Description
--------- | -----------
amount | Send Amount
toAddress | Receiver's address

<!-- ```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside> -->