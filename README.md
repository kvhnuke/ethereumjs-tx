# SYNOPSIS 
[![NPM Package](https://img.shields.io/npm/v/ethereumjs-tx.svg?style=flat-square)](https://www.npmjs.org/package/ethereumjs-tx)
[![Build Status](https://img.shields.io/travis/ethereumjs/ethereumjs-tx.svg?branch=master&style=flat-square)](https://travis-ci.org/ethereumjs/ethereumjs-tx)
[![Coverage Status](https://img.shields.io/coveralls/ethereumjs/ethereumjs-tx.svg?style=flat-square)](https://coveralls.io/r/ethereumjs/ethereumjs-tx)
[![Gitter](https://img.shields.io/gitter/room/ethereum/ethereumjs-lib.svg?style=flat-square)](https://gitter.im/ethereum/ethereumjs-lib) or #ethereumjs on freenode  

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)  

# INSTALL
`npm install ethereumjs-tx`

# USAGE

  - [example](https://github.com/ethereumjs/ethereumjs-tx/blob/master/examples/transactions.js)

```javascript
var Tx = require('ethereumjs-tx')
var privateKey = new Buffer('e331b6d69882b4cb4ea581d88e0b604039a3de5967688d3dcffdd2270c0fd109', 'hex')

var rawTx = {
  nonce: '0x00',
  gasPrice: '0x09184e72a000', 
  gasLimit: '0x2710',
  to: '0x0000000000000000000000000000000000000000', 
  value: '0x00', 
  data: '0x7f7465737432000000000000000000000000000000000000000000000000000000600057'
}

var tx = new Tx(rawTx)
tx.sign(privateKey)

var serializedTx = tx.serialize()


var eip155tx = new Tx(rawTx,{chainId: 1}) //mainnet chain_id = 1
eip155tx.sign(privateKey)

var serializedEip155Tx = eip155tx.serialize()
```

**Note:** this package expects ECMAScript 6 (ES6) as a minimum environment. From browsers lacking ES6 support, please use a shim (like [es6-shim](https://github.com/paulmillr/es6-shim)) before including any of the builds from this repo.


# BROWSER  
For a browser build please see https://github.com/ethereumjs/browser-builds.

# API
[./docs/](./docs/index.md)

# LICENSE
[MPL-2.0](https://tldrlegal.com/license/mozilla-public-license-2.0-(mpl-2))
