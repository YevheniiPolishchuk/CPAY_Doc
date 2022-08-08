# Release 3.4

**What's New:**

1\)Added e-mail and user name of the user to the checkout:

&#x20;\- Selecting these options by checkout creating:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-12\_39\_36.png)

&#x20;\- Filling in these parameters in the charge

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-12\_49\_50.png)

2\)Added registration and authorization by phone number

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-13\_25\_32.png)

3\)Added search by name and duplication of checkouts:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-13\_31\_10.png)

4\)New design of system letters

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-13\_33\_14.png)

5\)Email onboarding. Includes letters that come after the following events: \
\- 15 minutes after registration; \
\- receipt of the first funds; \
\- 3 days without profile activity; \
\- 7 days without profile activity.

6\)Added a new Start Now block on the Home page, which redirects to the checkouts page:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-13\_53\_05.png)

7\)Added Profile section to the profile menu:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-13\_58\_05.png)

8\)Reworked the logic of changing E-mail'a for greater security. The user needs to confirm the new E-mail by clicking on the link in the letter, otherwise the user will not be able to log in after logging out.

9\)Added display of the sale price in the list of checkouts

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-14\_14\_09.png)

10\)Added the ability to add an image in the checkout via the link

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-14\_18\_09.png)

11\)New currency icons:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-14\_29\_15.png)

12\)Added links to network scans:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-14\_40\_25.png)

13\)Two new transaction filters: Error - all transactions that were processed with an error and Refund - a transaction to return funds to a SystemFee wallet if this wallet sent funds to a client wallet to send funds to a merchant's wallet:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-14\_44\_55.png)

14\)New transaction status Wait for funds, such a transaction occurs if the user has no funds to pay for MinerFee on the merchant's wallet and the SystemFee wallet also has no funds, under the transaction there is a message about which wallet the user needs to replenish and for what amount:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-15\_01\_45.png)

15\)Added new query parameter resetStatus=true for payment link. If it is added to the checkout link, then a new payment will be generated after the page is reloaded if the current payment status is completed.

16\)All currencies with a zero balance are displayed at the bottom of the page:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-19\_39\_39.png)

17\)Added the ability to select a specific currency in the checkout in which the user wants to accept payment:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-19\_41\_52.png)

18\)Added an Apply button on the Wallets page in the Currency filter, clicking on which sends a request to filter wallets by currency:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-19\_46\_02.png)

19\)Added offer to receive the first crypto payment in a transaction block if the user has no transactions:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-20\_45\_36.png)

**Improved/Fixed:**

1\)Improved Energy Estimation for TRC-20. Merchant's TRX wallet now sends a fixed amount of TRX needed to send USDT TRC-20 from client's wallet to merchant's wallet.

2\)Expanded clickable checkout area in the checkouts list:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-20\_21\_37.png)

3\)Validation is set for the clickId field. Now, of the special characters available for input, only "-" and "\_" are available:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-20\_25\_27.png)

4\)Fixed a bug related to the deformation of the image that is added to the checkout. The image now retains its original aspect ratio.

5\)Wallet addresses in the Balance block are now truncated in the middle:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.03.07-20\_31\_16.png)

6\)Now the scroll always goes to the top of the page when filtering transactions by currency.

7\)After login in the header, the merchant that was selected when exiting is selected.

8\)The "Show all transactions" component is hidden if the transaction filter by currency is not applied.

9\)The "Hide zero balances" component has been redesigned into a checkbox that is selected by default, but not if all balances are zero.
