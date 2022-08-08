# Cryptocurrency Payments through CPAY

In CPAY we can create the checkout (donation or sale) or just replenish the crypto wallets.

### Operations with currencies

\
In CPAY, you can replenish and withdraw funds from client and merchant wallets. You can also create a checkout (donate or sell). After that you can send a link to it. Thus, the user who follows the link will be create a charge. Charging is available for payment in all currencies supported by the merchant and in the network in which the merchant was at the time the payment was created. When the user selects the currency in which he wants to pay for the charge, the system generates a unique wallet. After the payment has passed, the client needs to generate a new wallet for the charge, funds can also be sent to the previous wallet, but this transaction will not be tracked.

These unique payment addresses are monitored for up to 60 minutes. If no payment is detected after 60 minutes then the checkout status changes to **Expired**.

### Payment statuses

When a customer makes a payment in cryptocurrency, they generate a **transaction**, which is then broadcast to the cryptocurrency network for verification / confirmation.

When the customer’s transaction was created, the **payment status** changes to **New**. When the customer’s transaction was detected on the blockchain, the **payment status** changes to **Pending**. This means the payment has been detected but it has not yet been confirmed by the network. When the transaction is fully validated and confirmed by the blockchain network, the payment status changes to **Done**. If transaction has been cancelled by something reason (high network load for example), the payment status changes to **Failed**.

After the funds have been credited to the client's wallet, they are sent to the merchant's wallet. To do this, the merchant's wallet must send funds to the client's wallet to pay for Miner Fee. For example, in order for Tether ERC-20 send to the ETH merchant's wallet, this merchant's wallet must send ETH in an amount sufficient to pay for Miner Fee.&#x20;

If the merchant's wallet does not have the funds to pay MinerFee for the transaction of replenishing the merchant's wallet from the client's wallet, then the system will send the necessary funds, but will create a transaction with the "**Refund"** status, which will be executed when the required amount is on the default or secondary merchant's wallet. If the system also has no funds, then a transaction to replenish the merchant's wallet from the client's wallet will be created with the status **"Wait for funds"**. Under the transaction, it will be indicated which of the wallets needs to be replenished and by what amount in order for the transaction to be completed.\
\
A list of all payment statuses can be found below:

|  PAYMENT STATUS |                                                               DESCRIPTION                                                               |
| :-------------: | :-------------------------------------------------------------------------------------------------------------------------------------: |
|       New       |                                                     The transaction has been created                                                    |
|     Pending     |                                                    The transaction has been detected                                                    |
|       Done      |                                         The transaction has been confirmed by blockchain network                                        |
|      Refund     | Reimbursement of funds to the system for the execution of a transaction for replenishing the merchant's wallet from the client's wallet |
|  Wait for funds |    The transaction cannot be completed, because the default wallet of the merchant and the system do not have funds to pay Miner Fee    |
|      Failed     |                          The transaction has been cancelled by something reason (high network load for example)                         |

Here's a visual representation of how transaction works for crypto merchant wallets replenishment:

![](../.gitbook/assets/screenshot-programforyou.ru-2021.10.11-15\_07\_24.png)

Here's a visual representation of how transaction works for crypto clients wallets replenishment:

![](../.gitbook/assets/screenshot-nimbusweb.me-2022.05.16-14\_39\_01.png)

Here's a visual representation of how transaction works for withdrawal:

![](<../.gitbook/assets/screenshot-programforyou.ru-2021.10.11-15\_07\_24 (1).png>)

Here's a visual representation for Swap:

![](../.gitbook/assets/screenshot-nimbusweb.me-2022.05.16-13\_29\_35.png)
