# Using the Public API for transaction and currency

### Fee estimate

{% swagger method="post" path="/api/public/transaction/fee" baseUrl="https://api.cpay.world" summary="Endpoint POST /api/public/transaction/fee" %}
{% swagger-description %}
Endpoint, allows you to estimate transactions. You need to log in with the wallet in conjunction with the merchant.
{% endswagger-description %}

{% swagger-parameter in="body" name="to" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Number" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="priority" type="Boolean" %}
Parameter for defining the high priority of the transaction
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Example for currency" %}
```javascript
{
  "data": {
    "fee": 0
  }
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Example for token" %}
```javascript
{
  "data": {
    "fee": 0,
    "ethFee": 0
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
            "amount must be a number conforming to the specified constraints",
            "priority must be a boolean value"
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

### Merchant currency

{% swagger method="get" path="/api/public/currency" baseUrl="https://api.cpay.world" summary="Endpoint GET /api/public/currency" %}
{% swagger-description %}
The endpoint allows you to get all the currencies that the merchant supports. You need to log in to the merchant.
{% endswagger-description %}

{% swagger-parameter in="query" name="page" type="Nubmer" %}

{% endswagger-parameter %}

{% swagger-parameter in="query" name="limit" type="Number" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "data": {
    "page": 0,
    "pages": 0,
    "countItems": 0,
    "currencies": [
      {
        "_id": "string",
        "name": "string",
        "title": "string",
        "nodeType": "string",
        "currencyType": "string"
      }
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
