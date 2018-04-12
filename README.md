Bitcore P2P-GoByte
=======

[![NPM Package](https://img.shields.io/npm/v/bitcore-p2p-gobyte.svg?style=flat-square)](https://www.npmjs.org/package/bitcore-p2p-gobyte)
[![Build Status](https://img.shields.io/travis/gobytecoin/bitcore-p2p-gobyte.svg?branch=master&style=flat-square)](https://travis-ci.org/gobytecoin/bitcore-p2p-gobyte)
[![Coverage Status](https://img.shields.io/coveralls/gobytecoin/bitcore-p2p-gobyte.svg?style=flat-square)](https://coveralls.io/r/gobytecoin/bitcore-p2p-gobyte?branch=master)

`bitcore-p2p-gobyte` adds GoByte protocol support for Bitcore-GoByte.

See [the main bitcore-gobyte repo](https://github.com/gobytecoin/bitcore-gobyte) for more information.

## Getting Started

```sh
npm install bitcore-p2p-gobyte
```
In order to connect to the GoByte network, you'll need to know the IP address of at least one node of the network, or use [Pool](/docs/pool.md) to discover peers using a DNS seed.

```javascript
var Peer = require('bitcore-p2p-gobyte').Peer;

var peer = new Peer({host: '127.0.0.1'});

peer.on('ready', function() {
  // peer info
  console.log(peer.version, peer.subversion, peer.bestHeight);
});
peer.on('disconnect', function() {
  console.log('connection closed');
});
peer.connect();
```

Then, you can get information from other peers by using:

```javascript
// handle events
peer.on('inv', function(message) {
  // message.inventory[]
});
peer.on('tx', function(message) {
  // message.transaction
});
```

Take a look at the [bitcore guide](http://bitcore.io/guide/peer.html) on the usage of the `Peer` class.

## Contributing

See [CONTRIBUTING.md](https://github.com/gobytecoin/bitcore-gobyte/blob/master/CONTRIBUTING.md) on the main bitcore-gobyte repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/bitpay/bitcore/blob/master/LICENSE).

Copyright 2013-2015 BitPay, Inc. Bitcore is a trademark maintained by BitPay, Inc.
