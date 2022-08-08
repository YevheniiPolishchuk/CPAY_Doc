# Release 3.3.2

**What's new:**

1\) Added sending webhooks in all transaction statuses. Previously, the webhook sent the status of only a completed transaction - "Done", now all statuses are sent, namely "New", "Pending" and "Failed".

2\) Added the ability to select the checkout expire time

For donation:

![](<../../.gitbook/assets/screenshot-app.cpay.world-2022.01.25-14\_13\_17 (1).png>)

For sale:

![](../../.gitbook/assets/screenshot-app.cpay.world-2022.01.25-14\_15\_11.png)

3\) Added display and ability to copy merchant wallets in currency balance block

![](../../.gitbook/assets/screenshot-app.cpay.world-2022.01.25-14\_18\_06.png)

4\) Added donation creation after registration

![](<../../.gitbook/assets/screenshot-app.cpay.world-2022.01.25-14\_21\_41 (1).png>)

**Fixed:**

1\)Fixed caching of content accessed via HTTPS

2\)Fixed an error in the transactions of replenishing the merchant's wallet from the client's wallet, if there are funds on the client's wallet to pay for the Miner Fee
