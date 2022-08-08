# Release 3.6

### **What's new:**

1\)Added the checkout 3rd type - Sale Token , which allows to sell currency

&#x20;\- Select the type

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-13\_01\_32.png)

&#x20;\- Fill the form

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-13\_03\_57.png)

**Payment methods** - choice of currencies in which the user wants to accept payments.

**Receive payment** - the currency the user wants to sell.

{% hint style="info" %}
The currency you selected in the "Receive payment" field is reset in the "Payment methods" field. Therefore, if you first selected one currency, and then selected another in the "Receive payment" field, then fill in the "Payment methods" field again.
{% endhint %}

**Merchant wallet** - wallet from which sales will be carried out.

**Min** - minimum sale amount.

**Max** - maximun sale amount.

**Max button** - button to receive the maximum possible amount for sale. When receiving the amount, MinerFee and System Fee are taken into account, as well as already created checkouts based on the selected merchant wallet.

{% hint style="info" %}
The amount of checkouts based on one merchant's wallet should not exceed its balance. For example, on your merchant wallet balance is 2000 TRX, you can create n number of checkouts, but their value in the max field in total should not exceed 2000 TPX.
{% endhint %}

{% hint style="info" %}
If you do not have the main currency on your account, that is, not enough to pay Miner Fee for at least one transaction, then when you receive the maximum amount for the token, you will receive 0.
{% endhint %}

**Fixed** - the user enters the currency price on their own.

**Market** - the price of the currency is taken from [CPAY Coin Price](https://coinprice.cpay.world/) - service for obtaining historical, statistical data on crypto pairs.

**Add token** - link to the form for adding your own currency.

**Enter price** - field for entering your own currency price. **The field is limited to 6 decimal places.**

**Expire time** - the time that the estimated selling price of your currency will be held.

&#x20;\- Payment widget

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-13\_50\_41.png)

**You send** - field for entering the amount and selecting the currency for which you want to purchase the currency indicated in the You Get field.

**Estimated Exchange Rate -** the exchange rate of your chosen currencies.

**You get** - field for entering the amount of currency you want to buy.

**Min amount** - the minimum allowable sale amount.

**Max amount** - the maximum allowable sale amount. This value is updated every 15 seconds and also when the user fills in the Recipient field.&#x20;

If the user did not use the MAX button and entered the entire balance of the wallet, then the max amount field will be recalculated and will contain the value from Miner Fee and System Fee.

If, based on the results of sales, the maximum amount is less than the minimum amount, then a corresponding message is displayed:

![](<../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-16\_59\_00 (1).png>)

**Price fixed for {n} minutes** - fixed price per amount and currency in the You get field. When the time passes, a form is displayed to update the price:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-16\_16\_52.png)

**Recipient** - the wallet to which the purchased funds are sent. When you enter it, the fixed price is also updated.

&#x20;\- Comfirm exchange

![](<../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-13\_54\_58 (1).png>)

&#x20;\- Customer details

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-13\_58\_10.png)

&#x20;\- Payment widget

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-14\_03\_18.png)

**Amount -** the price of the currency specified in the You get field.

**Address -** wallet address to which you want to send the amount specified in the Amount field.

{% hint style="info" %}
If the user sent an amount less than specified in the Amount field, then the purchase will be an amount less. But if the total amount sent in the equivalent is less than indicated in the min amount field, then the purchase will not be made.
{% endhint %}

{% hint style="info" %}
If the user sent an amount greater than the amount specified in the Amount field, then the purchase will be for an amount greater or close to it (depending on the merchant wallet from which the sale is made) in accordance with the established rate.
{% endhint %}

**Awaiting deposit** - waiting for replenishment of funds to the specified address.

**Confirming** - replenishment of funds to the specified address is completed.

**Exchanging -** there is an exchange of currencies, on the example of BNB for ETH.

**Sending to you** - sending funds to a recipient.

If exchange rate expired, then opens the payment widget.

&#x20;\- Payment successfull

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-14\_32\_32.png)

**Make an exchange** - return to payment widget.

****

### **Improved/Fixed:**

1\)Optimized the Swap section for more convenient use

&#x20;\- Added "Create new Swap" button on the form of swaps, in their absence:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-17\_10\_54.png)

&#x20;\- Added sorting of currencies in descending order in the You send and You get fields:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-17\_12\_02.png)

&#x20;\- Added hiding secondary wallets and replacing wallets by clicking on the text "Change":

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-17\_16\_52.png)

The first three steps and partner selection are combined into one page:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-17\_25\_04.png)

Added a "Update offers" button to get up-to-date data on partners:

![](../../.gitbook/assets/screenshot-nimbusweb.me-2022.08.05-17\_27\_08.png)

2\)Added observance of currency decimals in all sections of the platform, i.e. eliminated trimming and rounding of characters;

3\)Various fixes that improve platform performance.
