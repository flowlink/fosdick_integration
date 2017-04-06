# Fosdick Endpoint

## Parameters

- **client** - The name of your fosdick account
- **fosdick_amazon_key** - Your S3 account's key
- **fosdick_amazon_secret_key** - Your S3 account's secret key

## Webhooks

### Add Shipment (/add_shipment)

The add shipment webhook sends a new shipment to Fosdick.

#### Request

```
{
  "request_id": "52f367367575e449c3000001",
  "shipment": {
    "id": "12836",
    "order_id": "R154085346",
    "email": "spree@example.com",
    "cost": 5,
    "status": "ready",
    "stock_location": "default",
    "shipping_method": "UPS Ground (USD)",
    "tracking": "12345678",
    "shipped_at": "2014-02-03T17:33:55.343Z",
    "shipping_address": {
      "firstname": "Joe",
      "lastname": "Smith",
      "address1": "1234 Awesome Street",
      "address2": "",
      "zipcode": "90210",
      "city": "Hollywood",
      "state": "California",
      "country": "US",
      "phone": "0000000000"
    },
    "items": [
      {
        "name": "Spree T-Shirt",
        "product_id": "SPREE-T-SHIRT",
        "quantity": 1,
        "price": 30,
        "options": {}
      }
    ]
  },
  "parameters": {
    "client": "yourclientname",
    "fosdick_amazon_key": "foobar",
    "fosdick_amazon_secret_key": "foobar"
  }
}
```

#### Error Response

**Status Code**: 500  
**Content-Type**: application/json

```
{
  "request_id": "52f367367575e449c3000001",
  "summary": "[{\"SuccessCode\"=>\"False\", \"ErrorCode\"=>\"Invalid\", \"Errors\"=>{\"Error\"=>\"Please enter a valid value for ClientCode\"}}, {\"SuccessCode\"=>\"False\", \"ErrorCode\"=>\"Failure\", \"Message\"=>\"Invalid ClientCode\"}]"
}
```

# About FlowLink

[FlowLink](http://flowlink.io/) allows you to connect to your own custom integrations.
Feel free to modify the source code and host your own version of the integration
or better yet, help to make the official integration better by submitting a pull request!

This integration is 100% open source an licensed under the terms of the New BSD License.

![FlowLink Logo](http://flowlink.io/wp-content/uploads/logo-1.png)
