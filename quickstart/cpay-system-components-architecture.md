# CPAY system components architecture

![](../.gitbook/assets/screenshot-nimbusweb.me-2022.05.16-14\_08\_53.png)

### **User component**

This is one of the fundamental components of the system. It is the connecting link with other components. Its main goal is to provide access to the creation of a merchant. \
&#x20;It is used in two variants:\
&#x20; \- Individual;\
&#x20; \- Business.\
**Individual** is a type of user who operates only with the merchant's wallets, can accept, send payments, add new merchant wallets, create checkouts and swap currency. This user has only one merchant.&#x20;

**Business** is a type of user that is business-oriented, for example, in a retail environment. It is possible to create merchants up to 5, set up its commissions, integrate with a third-party system and create client wallets.

### Merchant component

This is the main component of the system, around which the entire functional model of the system is built. Merchant is an entity for storing crypto wallets, which also makes it possible to accept payments in cryptocurrency. You can integrate CPAY into any system as a payment method using private and public key, which you can get in merchant settings.

### Currency component

The component that is responsible for the list and functionality of cryptocurrencies in the system and their environment. This is the entry point for wallets replenishment, funds withdrawing, wallets creating, merchants creating, and checkouts creating.

### Wallet component

Component responsible for creating and storing cryptocurrency wallets that the system supports. These wallets are linked to merchants created in the system.&#x20;

There are two types of wallets in the system: merchant wallets and client wallets. Merchant Wallet is a wallet that accepts funds from client wallets. Roughly speaking, this is the wallet of the business owner. You can create a new merchant wallets or import the existing wallet. Client Wallet is a wallet that is created when a customer pays for a product or service. A business owner can create a client wallet himself and reset it to a client for replenishment. Also, such wallets are generated when paying for a checkout: donation or sale. Each wallet in the system is unique, you cannot create two identical wallets.

### Transaction component <a href="#id-1.arkhitekturakomponentovsistemycryptopay-cypy.io-komponenttransaction" id="id-1.arkhitekturakomponentovsistemycryptopay-cypy.io-komponenttransaction"></a>

A component that allows you to track the movement of funds in wallets. There are three types of transactions in the system:\
&#x20;\- Replenishment;\
&#x20;\- Withdraw;\
&#x20;\- Refund - refunds to the system wallet for providing funds to pay for Miner Fee when the required amount of funds was not on the merchant's wallet.\
The client's wallet, after its replenishment, sends all its funds to the merchant's wallet, while creating transaction for replenishment. The client wallet replenishment transaction is not created.

### Withdrawal component <a href="#id-1.arkhitekturakomponentovsistemycryptopay-cypy.io-komponentwithdrawal" id="id-1.arkhitekturakomponentovsistemycryptopay-cypy.io-komponentwithdrawal"></a>

A component that allows you to withdraw funds from the CPAY system to another wallet. You can withdraw funds both from the merchant's wallet and from the client's wallet (through public API). In case of withdrawal from the client's wallet, the necessary funds are first sent from the merchant's wallet to the client's wallet (no transactions are created for this), and then a withdrawal transaction  from the client's wallet will be created.

### Checkout component

A component that allows you to create the checkout: donation or sale. Donation is a payment without fixed sum. Sale is a payment that has fixed sum. You can create a checkout and send it. After clicking on the link, the user creates a charge.

### **Swap component**

A component that allows users to exchange their currency that they have for another.
