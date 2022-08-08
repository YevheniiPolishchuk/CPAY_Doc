---
description: >-
  You can integrate CPAY in your system as payment method. After you've signed
  up you should to create a merchant and get API keys for client(public) wallet
  creation in your system.
---

# Using the Public API for public wallet

### Client wallet creating

{% swagger method="post" path="/api​/public​/wallet​/{currencyId}" baseUrl="https://api.cpay.world" summary="Endpoint POST ​/api​/public​/wallet​/{currencyId}" %}
{% swagger-description %}
You need to log in to the merchant.
{% endswagger-description %}

{% swagger-parameter in="path" name="currencyId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "data": {
    "id": "string",
    "address": "string",
    "balance": 0,
    "balanceUSD": 0,
    "passphrase": "string"
  }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
    "message": "This currency is not supported."
}
```
{% endswagger-response %}

{% swagger-response status="401" description="" %}
```javascript
{
    "status": "fail",
    "data": {
        "message": "Unauthorized"
    }
}
```
{% endswagger-response %}
{% endswagger %}

You can login to wallet and get wallet access token necessary for witdrawal from wallet and for getting wallet ballance. You need to get api keys for your merchant, also you need wallet Id and wallet passphrase.

### Wallet login

{% swagger method="post" path="api/public/auth" baseUrl="https://api.cpay.world/" summary="Endpoint POST /api/public/auth" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="walletId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="passphrase" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="publicKey" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="privateKey" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "token": "string"
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
    "status": "fail",
    "data": {
        "message": [
            "publicKey should not be empty"
        ]
    }
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}
```javascript
{
    "status": "fail",
    "data": {
        "message": "Unauthorized"
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Withdrawal from public wallet

{% swagger method="post" path="​/api​/public​/withdrawal" baseUrl="https://api.cpay.world" summary="Endpoint POST ​/api​/public​/withdrawal" %}
{% swagger-description %}
Endpoint allows you to withdraw funds to another wallet outside the system. The header contains the Bearer token, which can be obtained upon authorization under the merchant in conjunction with the wallet. You need to log in with the wallet in conjunction with the merchant.
{% endswagger-description %}

{% swagger-parameter in="body" name="to" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Number" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "data": {
    "id": "string"
  }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
  "data": {
    "id": "string"
  }
}
```
{% endswagger-response %}

{% swagger-response status="401" description="" %}
```javascript
{
    "status": "fail",
    "data": {
        "message": "Unauthorized"
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Get wallet ballance

{% swagger method="get" path="/api/public/wallet" baseUrl="https://api.cpay.world" summary="Endpoint GET ​/api​/public​/wallet" %}
{% swagger-description %}
The endpoint allows you to get the current balance of the wallet. You need to log in with the wallet in conjunction with the merchant.
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "data": {
    "balance": 0,
    "balanceUSD": 0
  }
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}
```javascript
{
    "status": "fail",
    "data": {
        "message": "Unauthorized"
    }
}
```
{% endswagger-response %}
{% endswagger %}
