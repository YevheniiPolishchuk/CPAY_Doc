---
description: >-
  Accepting cryptocurrency payments with the CPAY Public API is fast and easy.
  After you've signed up you already can to create a charge to receive a
  payment.
---

# Using the Public API for checkout

Use the CPAY Public API for checkout creating. When you create a charge, we generate payment addresses on your behalf for each cryptocurrency that’s enabled and provide you with a hosted page you can send to customers to complete the payment.

### Login to merchant

You need to get api keys for your merchant and login to your merchant in order to get the token necessary for creating checkout and further actions on them.

{% swagger method="post" path="/api/public/auth" baseUrl="https://api.cpay.world" summary="Endpoint POST /public/auth" %}
{% swagger-description %}
Endpoint allows you to log in to the system under the merchant. publicKey and privateKey can be obtained from the merchant. There is a corresponding endpoint that generates these keys for the merchant.
{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="publicKey" type="string" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="privateKey " type="string" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "token": "string"
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="If request body parameters are empty or have incorrect type (not string)" %}
```javascript
{
    "status": "fail",
    "data": {
        "message": [
            "publicKey should not be empty",
            "privateKey should not be empty"
        ]
    }
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="If you use incorrect merchant token" %}
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

### Checkout(donation) creating

{% swagger method="post" path="/api/public/checkout/donation" baseUrl="https://api.cpay.world" summary="Endpoint POST /api/public/checkout/donation" %}
{% swagger-description %}
You need to log in to the merchant.
{% endswagger-description %}

{% swagger-parameter in="body" name="organizationName" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "data": {
    "identifier": "string",
    "merchant": {},
    "createdAt": "2021-10-04T14:20:37.949Z",
    "updatedAt": "2021-10-04T14:20:37.949Z",
    "organizationName": "string",
    "description": "string"
  }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="If request body parameters are empty or have incorrect type (not string)" %}
```javascript
{
    "status": "fail",
    "data": {
        "message": [
            "organizationName should not be empty",
            "description must be a string"
        ]
    }
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="If you use incorrect merchant token" %}
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

### Checkout(sale) creating

{% swagger method="post" path="/api​/public​/checkout​/sale" baseUrl="https://api.cpay.world" summary="Endpoint /api​/public​/checkout​/sale" %}
{% swagger-description %}
You need to log in to the merchant.
{% endswagger-description %}

{% swagger-parameter in="body" name="productName" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="price" type="number" required="true" %}
must not be less than 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fiatCurrency" type="string" required="true" %}
must be only USD
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "data": {
    "identifier": "string",
    "merchant": {},
    "createdAt": "2021-10-04T14:42:12.328Z",
    "updatedAt": "2021-10-04T14:42:12.328Z",
    "productName": "string",
    "description": "string",
    "price": 0,
    "fiatCurrency": "string"
  }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
    "status": "fail",
    "data": {
        "message": [
            "description should not be empty",
            "price must not be less than 1",
            "price must be a number conforming to the specified constraints",
            "fiatCurrency must be a valid enum value"
        ]
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

### Get all checkouts list

{% swagger baseUrl="https://api.cpay.world" path="/api​/public​/checkout" method="get" summary="Endpoint /api/public/checkout" %}
{% swagger-description %}
You need to log in to the merchant.
{% endswagger-description %}

{% swagger-parameter in="query" name="order" type="string" %}
Available values: ASC, DESC. Defaule value: ASC
{% endswagger-parameter %}

{% swagger-parameter in="query" name="page" type="number" %}
Default value: 1
{% endswagger-parameter %}

{% swagger-parameter in="query" name="limit" type="number" %}
Default value : 10
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "data": {
    "page": 0,
    "pages": 0,
    "countItems": 0,
    "entities": [
      {
        "identifier": "string",
        "merchant": {},
        "createdAt": "2021-10-04T14:50:27.706Z",
        "updatedAt": "2021-10-04T14:50:27.706Z"
      }
    ]
  }
}
```
{% endswagger-response %}

{% swagger-response status="401" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Unauthorized"
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Get a specific checkout

{% swagger baseUrl="https://api.cpay.world" path="/api/public/checkout/{checkoutId}" method="get" summary="Endpoint /api/public/checkout/{checkoutId}" %}
{% swagger-description %}
You need to log in to the merchant.
{% endswagger-description %}

{% swagger-parameter in="path" name="checkoutId" type="string" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "data": {
    "identifier": "string",
    "merchant": {},
    "createdAt": "2021-10-04T15:49:56.601Z",
    "updatedAt": "2021-10-04T15:49:56.601Z"
  }
}
```
{% endswagger-response %}

{% swagger-response status="401" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Unauthorized"
    }
}
```
{% endswagger-response %}

{% swagger-response status="404" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Checkout not found."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Checkout deleting

{% swagger baseUrl="https://api.cpay.world" path="/api/public/checkout{checkoutId}" method="delete" summary="Endpoint /api/public/checkout{checkoutId}" %}
{% swagger-description %}
You need to log in to the merchant.
{% endswagger-description %}

{% swagger-parameter in="path" name="checkoutId" type="string" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "data": true
}
```
{% endswagger-response %}

{% swagger-response status="401" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Unauthorized"
    }
}
```
{% endswagger-response %}

{% swagger-response status="404" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Checkout not found."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Checkout(donation) editing

{% swagger baseUrl="https://api.cpay.world" path="/api/public/checkout/{checkoutId}/donation" method="patch" summary="Endpoint PATCH /api/public/checkout/{checkoutId}/donation" %}
{% swagger-description %}
You need to log in to the merchant.
{% endswagger-description %}

{% swagger-parameter in="path" name="checkoutId" type="string" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="organizationName" type="string" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="string" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "data": {
    "identifier": "string",
    "merchant": {},
    "createdAt": "2021-10-04T16:08:23.049Z",
    "updatedAt": "2021-10-04T16:08:23.049Z",
    "organizationName": "string",
    "description": "string"
  }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": [
            "organizationName should not be empty",
            "description must be a string"
        ]
    }
}
```
{% endswagger-response %}

{% swagger-response status="401" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Unauthorized"
    }
}
```
{% endswagger-response %}

{% swagger-response status="404" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Checkout not found."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Checkout(sale) editing

{% swagger baseUrl="https://api.cpay.world" path="/api/public/checkout/{checkoutId}/sale" method="patch" summary="Endpoint PATCH /api/public/checkout/{checkoutId}/sale" %}
{% swagger-description %}
You need to log in to the merchant.
{% endswagger-description %}

{% swagger-parameter in="path" name="checkoutId" type="string" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="productName" type="string" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="string" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="price" type="number" required="true" %}
must not be less than 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fiatCurrency" type="string" required="true" %}
must be only USD
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "data": {
    "identifier": "string",
    "merchant": {},
    "createdAt": "2021-10-04T16:18:44.588Z",
    "updatedAt": "2021-10-04T16:18:44.588Z",
    "productName": "string",
    "description": "string",
    "price": 0,
    "fiatCurrency": "string"
  }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": [
            "description should not be empty",
            "price must not be less than 1",
            "price must be a number conforming to the specified constraints",
            "fiatCurrency must be a valid enum value"
        ]
    }
}
```
{% endswagger-response %}

{% swagger-response status="401" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Unauthorized"
    }
}
```
{% endswagger-response %}

{% swagger-response status="404" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Checkout not found."
    }
}
```
{% endswagger-response %}
{% endswagger %}

A checkout object is returned with a URL to a hosted page where a customer can complete their charge. The customer is able to send any amount for donation or fixed amount for sale.

## Receive a payment

After creating a charge, Coinbase Commerce will continuously monitor each blockchain network for a payment. Since cryptocurrencies are push payments, we set an expiration time for the charge which is currently 1 hour after the creation date. If the customer does not make a payment within that timeframe, we consider the charge to be expired.

After the user opens the widget, two requests are sent: the first to receive the chargeId, and the second to receive all the information on the charge.

### Get the chargeId

{% swagger baseUrl="https://api.cpay.world" path="/api/checkout-client/{identifier}/charge" method="post" summary="Endpoint /api/checkout-client/{identifier}/charge" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="identifier" type="string" required="true" %}
checkout identifier
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "data": {
    "id": "string"
  }
}
```
{% endswagger-response %}

{% swagger-response status="404" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Checkout not found."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Get the charge

{% swagger baseUrl="https://api.cpay.world" path="​/api​/checkout-client​/{chargeId}​/charge" method="get" summary="Endpoint /api/checkout-client/{chargeId}/charge" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="chargeId" type="string" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "data": {
    "id": "string",
    "typeNetwork": "string",
    "expiredDate": "string",
    "systemStatus": "string",
    "checkout": {
      "type": "string",
      "organizationName": "string",
      "description": "string"
    },
    "wallets": [
      {
        "address": "string",
        "currency": {
          "name": "string",
          "title": "string",
          "nodeType": "string",
          "currencyType": "string"
        }
      }
    ],
    "replenish": {
      "price": 0,
      "currency": "string",
      "amount": {
        "value": 0,
        "usd": 0
      }
    }
  }
}
```
{% endswagger-response %}

{% swagger-response status="401" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Charge not found."
    }
}
```
{% endswagger-response %}
{% endswagger %}

Also you can get information about checkout by identifier

{% swagger baseUrl="https://api.cpay.world" path="/api​/checkout-client​/{identifier}" method="get" summary="Endpoint /api/checkout-client/{identifier}" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="identifier" type="string" required="true" %}
checkout identifier
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "data": {
    "type": "string",
    "organizationName": "string",
    "description": "string"
  }
}
```
{% endswagger-response %}

{% swagger-response status="404" description="" %}
```
{
    "status": "fail",
    "data": {
        "message": "Checkout not found."
    }
}
```
{% endswagger-response %}
{% endswagger %}

The user opens a charge with an available list of currencies and expired time. After selecting the currency, a unique client wallet is generated. In this case, the status of the charge is accepted as New. When the user sends funds to the selected wallet, the charge status is accepted as Pending. After successful payment, the status of the charge is accepted as Done. If the user has not paid for the charge at the specified time, then the status of the charge is accepted as Expired. If any error or failure has occurred in the network, then the status of the transaction is accepted as Failed. After successful replenishment, the user needs to click on the "Back" button to generate new wallets or replenish the previous wallet, but in this case the transaction will not be displayed in the widget.
