# Release 3.3

**What's new:**

1\)Added the ability to upload an image to the checkout

![ ](../../.gitbook/assets/screenshot-app.cpay.world-2022.01.17-18\_38\_45.png)

2\)Added clickId to checkout, it can be your web shop order id or customer id or anything else id (only numbers and chars are allowed). This option added to transaction information and search available on it.

![](<../../.gitbook/assets/screenshot-app.cpay.world-2022.01.17-18\_52\_02 (1).png>)

![](../../.gitbook/assets/screenshot-app.cpay.world-2022.01.17-18\_54\_06.png)

3\)Added sending funds by the system to the merchant's wallet to pay Miner Fee for the transaction of replenishing the merchant's wallet from the client's wallet if there are no funds on the merchant's wallet. After replenishing the merchant's wallet, the system will write off the previously provided funds.

4\)Added arrows for scrolling currencies in the payment widget.

![](../../.gitbook/assets/screenshot-app.cpay.world-2022.01.17-18\_57\_05.png)

**Fixed:**

1\)Improved system fault tolerance by using the latest exchange rate after stopping the conversion service.

2\)Fixed the existence of the JWT token after the user logs out.
