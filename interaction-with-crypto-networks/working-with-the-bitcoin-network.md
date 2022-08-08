# Working with the Bitcoin network

In the CPAY system, the following operations will be performed with the participation of the Bitcoin blockchain network: obtaining a balance for a wallet, creating a wallet, transferring funds, receiving transactions.

To work with the Bitcoin network, you can already use ready-made third-party api, but there is a possibility that there will be a delay in the transfer of information, it is possible that data transfer limits have been set. If possible, you need to deploy your Bitcoin blockchain network, to which all requests from CPAY will be sent. This is necessary in order to avoid a delay in data transmission and also there will be no problems with the CPAY operation if any problems occur on a third-party service and the service is not available.

General scheme of interaction between CPAY and FullNode Bitcoin:

![](../.gitbook/assets/screenshot-app.gitbook.com-2021.10.13-20\_05\_22.png)

CPAY currently supports BTC currency.
