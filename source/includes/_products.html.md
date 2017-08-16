# Products

## Product Object


```json
{
    "id": "ac24a3",
    "title": "Awesome Product",
    "description": "My description",
    "stock": 2094,
    "price": "0.5",
    "currency": "EUR",
    "product_type": 2,
    "bitcoin": true,
    "paypal": true,
    "stripe": true,
    "litecoin": true,
    "dash": true,
    "ethereum": true,
    "perfect_money": true,
    "private": false,
    "unlisted": true,
    "seller_note": "Thanks for buying my product",
    "maximum_quantity": null,
    "minimum_quantity": 1,
    "custom": {},
    "created_at": "2016-05-15T14:02:47.000Z",
    "updated_at": "2017-08-12T23:37:13.000Z"
}
```

### Attributes

<ul class="api-attributes">
    <li>
        <p class="api-attributes-label">id<span>string</span></p>
        <p class="api-attributes-description">Unique identifier for the order</p>
    </li>
    <li>
        <p class="api-attributes-label">title<span>string</span></p>
        <p class="api-attributes-description">The title of the product</p>
    </li>
    <li>
        <p class="api-attributes-label">description<span>string</span></p>
        <p class="api-attributes-description">The raw markdown description of the product</p>
    </li>
    <li>
        <p class="api-attributes-label">stock<span>integer/string</span></p>
        <p class="api-attributes-description">The current stock count. Will return <code>∞</code> unless <code>product_type</code> is 2</p>
    </li>
   <li>
        <p class="api-attributes-label">stock<span>decimal/float</span></p>
        <p class="api-attributes-description">The price of the product for 1 quantity</p>
    </li>
    <li>
        <p class="api-attributes-label">currency<span>string</span></p>
        <p class="api-attributes-description">The ISO 4217 currency code used</p>
    </li>
    <li>
        <p class="api-attributes-label">product_type<span>integer</span></p>
        <p class="api-attributes-description">The product type. Determines the stock</p>
    </li>
    <li>
        <p class="api-attributes-label">bitcoin<span>boolean</span></p>
        <p class="api-attributes-description">Whether Bitcoin is accepted on this product</p>
    </li>
    <li>
        <p class="api-attributes-label">paypal<span>boolean</span></p>
        <p class="api-attributes-description">Whether PayPal is accepted on this product</p>
    </li> 
    <li>
        <p class="api-attributes-label">stripe<span>boolean</span></p>
        <p class="api-attributes-description">Whether Stripe is accepted on this product</p>
    </li>
    <li>
        <p class="api-attributes-label">litecoin<span>boolean</span></p>
        <p class="api-attributes-description">Whether Litecoin is accepted on this product</p>
    </li>
    <li>
        <p class="api-attributes-label">dash<span>boolean</span></p>
        <p class="api-attributes-description">Whether Dash is accepted on this product</p>
    </li> 
    <li>
        <p class="api-attributes-label">ethereum<span>boolean</span></p>
        <p class="api-attributes-description">Whether Ethereum is accepted on this product</p>
    </li>
    <li>
        <p class="api-attributes-label">perfect_money<span>boolean</span></p>
        <p class="api-attributes-description">Whether Perfect Money is accepted on this product</p>
    </li>
    <li>
        <p class="api-attributes-label">custom<span>object</span></p>
        <p class="api-attributes-description">The custom inputs that the customer can input. The keys represent the index.</p>
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


## Get All Products

```ruby
Selly::Products.list
```

```shell
curl "https://selly.gg/api/products"
  -H "Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk="
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": "ac24a3",
        "title": "Awesome Product",
        "description": "My description",
        "stock": 2094,
        "price": "0.5",
        "currency": "EUR",
        "product_type": 2,
        "bitcoin": true,
        "paypal": true,
        "stripe": true,
        "litecoin": true,
        "dash": true,
        "ethereum": true,
        "perfect_money": true,
        "private": false,
        "unlisted": true,
        "seller_note": "Thanks for buying my product",
        "maximum_quantity": null,
        "minimum_quantity": 1,
        "custom": {},
        "created_at": "2016-05-15T14:02:47.000Z",
        "updated_at": "2017-08-12T23:37:13.000Z"
    },
    {
        "id": "d8b3cdb7",
        "title": "Dynamic E-book",
        "description": "Testing the description",
        "stock": "∞",
        "price": "1.0",
        "currency": "USD",
        "product_type": 3,
        "bitcoin": true,
        "paypal": true,
        "stripe": true,
        "litecoin": false,
        "dash": false,
        "ethereum": false,
        "perfect_money": false,
        "private": true,
        "unlisted": true,
        "seller_note": "",
        "maximum_quantity": null,
        "minimum_quantity": 1,
        "custom": {},
        "created_at": "2017-03-25T20:12:20.000Z",
        "updated_at": "2017-03-25T20:14:14.000Z"
    }
    
]
```

This endpoint retrieves all products.

### HTTP Request

`GET https://selly.gg/api/products`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Used for pagination

## Get a Specific Product

```ruby
Selly::Products.get('ac24a3')
```

```shell
curl "https://selly.gg/api/products/ac24a3"
  -H "Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk="
```

> The above command returns JSON structured like this:

```json
{
    "id": "ac24a3",
    "title": "Awesome Product",
    "description": "My description",
    "stock": 2094,
    "price": "0.5",
    "currency": "EUR",
    "product_type": 2,
    "bitcoin": true,
    "paypal": true,
    "stripe": true,
    "litecoin": true,
    "dash": true,
    "ethereum": true,
    "perfect_money": true,
    "private": false,
    "unlisted": true,
    "seller_note": "Thanks for buying my product",
    "maximum_quantity": null,
    "minimum_quantity": 1,
    "custom": {},
    "created_at": "2016-05-15T14:02:47.000Z",
    "updated_at": "2017-08-12T23:37:13.000Z"
}
```

This endpoint retrieves a specific product.

### HTTP Request

<code>GET https://selly.gg/api/products/<span class="url-paramater">:ID</span></code>

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the product to retrieve