# Orders

## Order Object

```json
{
    "id": "fd87d909-fbfc-466c-964a-5478d5bc066a",
    "product_id": "upgrade",
    "email": "alishia@yahoo.com",
    "ip_address": "88.96.129.5",
    "country_code": "US",
    "user_agent": "Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/43.0.2357.124 Safari/537.36",
    "value": "0.03",
    "currency": "USD",
    "gateway": "Bitcoin",
    "risk_level": 10,
    "status": 100,
    "delivered": "SERIAL-12345-12345",
    "crypto_value": null,
    "crypto_address": null,
    "referral": null,
    "usd_value": "0.03",
    "exchange_rate": "1.0",
    "custom": {
      "0": "SomeInput"
    },
    "created_at": "2016-11-27T14:20:34.000Z",
    "updated_at": "2016-12-05T21:31:15.000Z"
  }
```

### Attributes

<ul class="api-attributes">
    <li>
        <p class="api-attributes-label">id<span>string</span></p>
        <p class="api-attributes-description">Unique identifier for the order</p>
    </li>
    <li>
        <p class="api-attributes-label">product_id<span>string</span></p>
        <p class="api-attributes-description">Unique identifier of the product that the order belongs to</p>
    </li>
    <li>
        <p class="api-attributes-label">email<span>string</span></p>
        <p class="api-attributes-description">Email address of the customer that initiated the order</p>
    </li>
    <li>
        <p class="api-attributes-label">ip_address<span>string</span></p>
        <p class="api-attributes-description">IP address of the customer that initiated the order</p>
    </li>
    <li>
        <p class="api-attributes-label">country_code<span>string</span></p>
        <p class="api-attributes-description">2 letter country code of the customer that initiated the order</p>
    </li>
    <li>
        <p class="api-attributes-label">user_agent<span>string</span></p>
        <p class="api-attributes-description">Browser user agent of the customer that initiated the order</p>
    </li>
    <li>
        <p class="api-attributes-label">value<span>float/decimal</span></p>
        <p class="api-attributes-description">The value of the order in the specified <code>currency</code></p>
    </li>
    <li>
        <p class="api-attributes-label">currency<span>string</span></p>
        <p class="api-attributes-description">The ISO 4217 currency code used for this order</p>
    </li>
    <li>
        <p class="api-attributes-label">gateway<span>string</span></p>
        <p class="api-attributes-description">The gateway used for this order. <code>Bitcoin</code>, <code>PayPal</code>, <code>Ethereum</code>, etc.</p>
    </li>
    <li>
        <p class="api-attributes-label">risk_level<span>integer</span></p>
        <p class="api-attributes-description">The calculated risk of this level from 0-100 with 100 being extremely risky/fraudulent</p>
    </li>
    <li>
        <p class="api-attributes-label">status<span>integer</span></p>
        <p class="api-attributes-description">Status of the order. The status codes that are used can be found here</p>
    </li>
    <li>
        <p class="api-attributes-label">delivered<span>string</span></p>
        <p class="api-attributes-description">The purchased product that is delivered to the seller. Will be <code>null</code> if the <code>status</code> is not 100</p>
    </li>
    <li>
        <p class="api-attributes-label">crypto_address<span>string</span></p>
        <p class="api-attributes-description">The crypto currency address presented to the customer. Will be <code>null</code> if the <code>currency</code> is not a crypto currency</p>
    </li>
    <li>
        <p class="api-attributes-label">crypto_value<span>integer</span></p>
        <p class="api-attributes-description">The crypto value in satoshis that the customer is required to send. Will be <code>null</code> if the <code>currency</code> is not a crypto currency</p>
    </li>
    <li>
        <p class="api-attributes-label">referral<span>string</span></p>
        <p class="api-attributes-description">The HTTP referrer for the product page. Will be <code>null</code> if the HTTP referrer was not present/valid</p>
    </li>
    <li>
        <p class="api-attributes-label">usd_value<span>float/decimal</span></p>
        <p class="api-attributes-description">The value of the order in USD</p>
    </li>
    <li>
        <p class="api-attributes-label">exchange_rate<span>float/decimal</span></p>
        <p class="api-attributes-description">The exchange rate from <code>currency</code> to USD</p>
    </li>
    <li>
        <p class="api-attributes-label">custom<span>object</span></p>
        <p class="api-attributes-description">The custom inputs that the customer inputted. The keys represent the index of the custom input specified in the product</p>
    </li>
    <li>
        <p class="api-attributes-label">created_at<span>datetime</span></p>
        <p class="api-attributes-description">The date and time that the resource was created</p>
    </li>
    <li>
        <p class="api-attributes-label">updated_at<span>datetime</span></p>
        <p class="api-attributes-description">The date and time that the resource was last updated. If never updated, it will be equal to <code>created_at</code></p>
    </li>
</ul>

## Get All Orders

```ruby
Selly::Orders.list
```

```shell
curl "https://selly.gg/api/orders"
  -H "Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk="
```

> The above command returns JSON structured like this:

```json
[
    {
    "id": "89ac7499-efc3-4f5b-a2fd-c00fec6aa480",
    "product_id": "ac24a3",
    "email": "john@gmail.com",
    "ip_address": "132.26.9.4",
    "country_code": "US",
    "user_agent": "Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/53.0.2357.124 Safari/537.36",
    "value": "0.03",
    "currency": "USD",
    "gateway": "Bitcoin",
    "risk_level": 9,
    "status": 0,
    "delivered": null,
    "crypto_value": null,
    "crypto_address": null,
    "referral": null,
    "usd_value": "0.03",
    "exchange_rate": "1.0",
    "custom": {
      "0": "MyUsername"
    },
    "created_at": "2015-06-11T18:32:01.000Z",
    "updated_at": "2017-02-14T17:47:27.000Z"
  },
  {
    "id": "fd87d909-fbfc-466c-964a-5478d5bc066a",
    "product_id": "upgrade",
    "email": "alishia@yahoo.com",
    "ip_address": "88.96.129.5",
    "country_code": "US",
    "user_agent": "Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/43.0.2357.124 Safari/537.36",
    "value": "0.03",
    "currency": "USD",
    "gateway": "Bitcoin",
    "risk_level": 10,
    "status": 100,
    "delivered": "SERIAL-12345-12345",
    "crypto_value": null,
    "crypto_address": null,
    "referral": null,
    "usd_value": "0.03",
    "exchange_rate": "1.0",
    "custom": {
      "0": "SomeInput"
    },
    "created_at": "2016-11-27T14:20:34.000Z",
    "updated_at": "2016-12-05T21:31:15.000Z"
  }
]
```

This endpoint retrieves all orders.

### HTTP Request

`GET https://selly.gg/api/orders`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Used for pagination

## Get a Specific Order

```ruby
Selly::Orders.get('fd87d909-fbfc-466c-964a-5478d5bc066a')
```

```shell
curl "https://selly.gg/api/orders/fd87d909-fbfc-466c-964a-5478d5bc066a"
  -H "Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk="
```

> The above command returns JSON structured like this:

```json
{
    "id": "fd87d909-fbfc-466c-964a-5478d5bc066a",
    "product_id": "upgrade",
    "email": "alishia@yahoo.com",
    "ip_address": "88.96.129.5",
    "country_code": "US",
    "user_agent": "Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/43.0.2357.124 Safari/537.36",
    "value": "0.03",
    "currency": "USD",
    "gateway": "Bitcoin",
    "risk_level": 10,
    "status": 100,
    "delivered": "SERIAL-12345-12345",
    "crypto_value": null,
    "crypto_address": null,
    "referral": null,
    "usd_value": "0.03",
    "exchange_rate": "1.0",
    "custom": {
      "0": "SomeInput"
    },
    "created_at": "2016-11-27T14:20:34.000Z",
    "updated_at": "2016-12-05T21:31:15.000Z"
  }
```

This endpoint retrieves a specific order.

### HTTP Request

<code>GET https://selly.gg/api/orders/<span class="url-paramater">:ID</span></code>

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the order to retrieve