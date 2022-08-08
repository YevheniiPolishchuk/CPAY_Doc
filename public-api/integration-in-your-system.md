# Integration in your system

To work with the system, you can use REST API or through the npm library. To do this, you need to generate access keys in the merchant's settings and use them for further work with the system.

Library for Node.js - [https://www.npmjs.com/package/cpay-node-api-sdk](https://www.npmjs.com/package/cpay-node-api-sdk)

To create a payment wallet, you only need to have access keys. If you need withdraw from the wallet, see information about it, etc., then you also need to use the walletId and passphrase.

Steps for working with the library:

```
npm i cpay-node-api-sdk

import CpaySDK from 'cpay-node-api-sdk';

const options = {
  publicKey: 'publicKey',
  privateKey: 'privateKey',
  walletId?: 'walletId',
  passphrase?: 'passphrase wallet'
};

const cpay = new CpaySDK(options);
```

All available library methods are available in the documentation at the link above.

