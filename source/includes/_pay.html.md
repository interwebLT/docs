# Selly Pay

Selly Pay provides a method of implementing a realtime checkout experience for any e-commerce platform and supporting a range of payment methods in one place.

With Selly Pay there is no <code>Product</code> that the order bases some information off, which allows for complete access to our payment systems without having to create a unique <code>Product</code> for every alteration a <code>Payment</code> may have. This also means that Selly does not handle any delivery of the "product" purchased, we'll only send a [Webhook](#webhook).

For the <code>gateway</code> chosen in the <code>Payment</code>, you must have the correct information (e.g your Bitcoin address if the <code>gateway</code> is Bitcoin) set in your [settings](https://selly.gg/settings).

For each <code>Payment</code> a unique URL will be returned. The customer will have to be redirected to this URL in order to access the checkout page.

<aside class="alert">Selly Pay currently only supports crypto currencies out of the box, if you'd like to utilize gateways such as PayPal, please contact us.</aside>

## Create a Payment


```shell
curl -X POST "https://selly.gg/api/pay"
  -H "Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk="
  -d '{"title:"Selly Pay Example", "gateway":"Bitcoin", "email":"customer@email.com", "value":"10", "currency":"USD", "return_url":"https://website.com/return", "webhook_url":"https://website.com/webhook?secret=cEZMeEVlTz"}'
```

```ruby
Selly::Pay::Create(
  title: 'Selly Pay Example',
  gateway: 'Bitcoin',
  email: 'customer@email.com',
  value: 10.00,
  currency: 'USD',
  return_url: 'https://website.com/return',
  webhook_url: 'https://website.com/webhook?secret=cEZMeEVlTz'
)
```

> The above command returns JSON structured like this:

```json
{
    "url": "https://selly.gg/payments/a78b04cf0272a193baca53416db510b84feae099/OTZ6di92LytKcnRmY0pmVTdEV0h3S3BUM1Fnb0ZURFp6cytOUEhWcEZMeEVlTzBjZHFzZFVlRGxabmZvWUtSR2kybHhyc0FHeHdUaHhwOWEzN3A1eFE9PS0tRXhHdk5SWU5TM2NWQWlhZzAwc3FqQT09--acf55a4be40ad6336f9ce7f9fbc063785851720e"
}
```

> The customer should be redirected to this URL to activate the checkout experience

### Attributes

<ul class="api-attributes">
    <li>
        <p class="api-attributes-label">title<span>string</span></p>
        <p class="api-attributes-description">Title of the product shown on the checkout page</p>
    </li>
    <li>
        <p class="api-attributes-label">gateway<span>string</span></p>
        <p class="api-attributes-description">The gateway used for this payment. <br>
        Can be <code>Bitcoin</code>, <code>Ethereum</code>, <code>Litecoin</code>, <code>Dash</code> or <code>Bitcoin Cash</code></p>
    </li>
    <li>
        <p class="api-attributes-label">email<span>string</span></p>
        <p class="api-attributes-description">The email of the customer</p>
    </li>
    <li>
        <p class="api-attributes-label">value<span>decimal/float</span></p>
        <p class="api-attributes-description">The fiat value/price of the order</p>
    </li>
    <li>
        <p class="api-attributes-label">currency<span>string</span></p>
        <p class="api-attributes-description">The ISO 4217 currency code used for this payment</p>
    </li>
    <li>
        <p class="api-attributes-label">return_url<span>string</span></p>
        <p class="api-attributes-description">URL displayed to the customer after the payment is completed</p>
    </li>
    <li>
        <p class="api-attributes-label">webhook_url<span>string</span></p>
        <p class="api-attributes-description">Webhook URL used on payment completion</p>
    </li>
</ul>