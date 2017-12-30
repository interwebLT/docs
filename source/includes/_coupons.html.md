# Coupons

## Coupon Object


```json
{
    "id": "ba6a15",
    "code": "25OFF",
    "discount": 25,
    "max_uses": null,
    "product_ids": ["ac24a3"],
    "uses": 0,
    "created_at": "2016-05-15T14:02:47.000Z",
    "updated_at": "2017-08-12T23:37:13.000Z"
}
```

### Attributes

<ul class="api-attributes">
    <li>
        <p class="api-attributes-label">id<span>string</span></p>
        <p class="api-attributes-description">Unique identifier for the coupon</p>
    </li>
    <li>
        <p class="api-attributes-label">coupon<span>string</span></p>
        <p class="api-attributes-description">Unique code for the coupon</p>
    </li>
    <li>
        <p class="api-attributes-label">discount<span>integer</span></p>
        <p class="api-attributes-description">The discount as a percentage</p>
    </li>
    <li>
        <p class="api-attributes-label">max_uses<span>integer</span></p>
        <p class="api-attributes-description">The max number of times the coupon can be used</p>
    </li>    
    <li>
         <p class="api-attributes-label">uses<span>integer</span></p>
         <p class="api-attributes-description">The number of times the coupon has been used</p>
     </li>
    <li>
        <p class="api-attributes-label">product_ids<span>array</span></p>
        <p class="api-attributes-description">The product ids that this group is made up of</p>
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


## Get All Coupons

```shell
curl "https://selly.gg/api/v2/coupons"
  -H "Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk="
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": "ba6a15",
        "title": "Awesome Product Group",
        "discount": 25,
        "max_uses": null,
        "product_ids": ["ac24a3"],
        "uses": 0,
        "created_at": "2016-05-15T14:02:47.000Z",
        "updated_at": "2017-08-12T23:37:13.000Z"
    },
    {
        "id": "12abc3e",
        "title": "Another Product Group",
        "discount": 25,
        "max_uses": null,
        "product_ids": ["ac24a3"],
        "uses": 0,
        "created_at": "2016-05-15T14:02:47.000Z",
        "updated_at": "2017-08-12T23:37:13.000Z"
    }
]
```

This endpoint retrieves all coupons.

### HTTP Request

`GET https://selly.gg/api/v2/coupons`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Used for pagination

## Get a Specific Coupon

```shell
curl "https://selly.gg/api/v2/coupon/ba6a15"
  -H "Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk="
```

> The above command returns JSON structured like this:

```json
{
    "id": "ba6a15",
    "code": "25OFF",
    "discount": 25,
    "max_uses": null,
    "product_ids": ["ac24a3"],
    "created_at": "2016-05-15T14:02:47.000Z",
    "updated_at": "2017-08-12T23:37:13.000Z"
}
```

This endpoint retrieves a specific coupon.

### HTTP Request

<code>GET https://selly.gg/api/v2/coupon/<span class="url-paramater">:ID</span></code>

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the coupon to retrieve