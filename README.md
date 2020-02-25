# bip32
[![Build Status](https://travis-ci.org/bitcoinjs/bip32.png?branch=master)](https://travis-ci.org/bitcoinjs/bip32)

[![NPM](https://img.shields.io/npm/v/bip32.svg)](https://www.npmjs.org/package/bip32)

[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)

A [BIP32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki) compatible library written in TypeScript with transpiled JavaScript committed to git.


## Example

TypeScript

``` typescript
import * as bip32 from 'bip32grs';
import { BIP32Interface } from 'bip32grs';
let node: BIP32Interface = bip32.fromBase58('xprv9s21ZrQH143K3XpLJrX92hM28H2o1CgVi6HXCWGBXtMkHxSkpxiFcnmzjy5qNyi3QUfSVXXapRT8St3wyLbWux9JysZZgvmvQZ75FUqrakP');

let child: BIP32Interface = node.derivePath('m/0/0');
// ...
```

NodeJS

``` javascript
let bip32 = require('bip32grs')
let node = bip32.fromBase58('xprv9s21ZrQH143K3XpLJrX92hM28H2o1CgVi6HXCWGBXtMkHxSkpxiFcnmzjy5qNyi3QUfSVXXapRT8St3wyLbWux9JysZZgvmvQZ75FUqrakP')

let child = node.derivePath('m/0/0')
console.log(child)
//BIP32 {
//  __D: <Buffer ea 39 8f 84 c7 5d 85 d5 4d 85 e6 84 1e c4 43 30 d4 07 98 f6 97 76 fd 49 54 9e 03 4e 30 af 11 ad>,
//  __Q: undefined,
//  chainCode: <Buffer 9f ec e5 30 ff 91 d7 23 82 20 c2 d2 5f 16 ed 29 34 eb b9 31 d2 20 0b 27 c7 8b 35 36 ad 17 d2 c8>,
//  network: { wif: 36, bip32: { public: 76067358, private: 76066276 } },
//  __DEPTH: 2,
//  __INDEX: 0,
//  __PARENT_FINGERPRINT: 1537180878,
//  lowR: false }
```

## LICENSE [MIT](LICENSE)
A derivation (and extraction for modularity) of the `HDWallet`/`HDNode` written and tested by [bitcoinjs-lib](https://github.com/bitcoinjs/bitcoinjs-lib) contributors since 2014.
