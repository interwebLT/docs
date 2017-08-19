# Product Groups

## Product Group Object


```json
{
    "id": "ba6a15",
    "title": "Awesome Product Group",
    "product_ids": ["ac24a3"],
    "created_at": "2016-05-15T14:02:47.000Z",
    "updated_at": "2017-08-12T23:37:13.000Z"
}
```

### Attributes

<ul class="api-attributes">
    <li>
        <p class="api-attributes-label">id<span>string</span></p>
        <p class="api-attributes-description">Unique identifier for the product group</p>
    </li>
    <li>
        <p class="api-attributes-label">title<span>string</span></p>
        <p class="api-attributes-description">The title of the product group</p>
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


## Get All Product Groups

```ruby
Selly::ProductGroups.list
```

```shell
curl "https://selly.gg/api/product_groups"
  -H "Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk="
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": "ba6a15",
        "title": "Awesome Product Group",
        "product_ids": ["ac24a3"],
        "created_at": "2016-05-15T14:02:47.000Z",
        "updated_at": "2017-08-12T23:37:13.000Z"
    },
    {
       "id": "12abc3e",
       "title": "Another Product Group",
       "product_ids": ["ac24a3", "32156a"],
       "created_at": "2016-05-15T14:02:47.000Z",
       "updated_at": "2017-08-12T23:37:13.000Z"
    }
]
```

This endpoint retrieves all product groups.

### HTTP Request

`GET https://selly.gg/api/product_groups`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Used for pagination

## Get a Specific Product Group

```ruby
Selly::ProductGroups.get('ba6a15')
```

```shell
curl "https://selly.gg/api/product_groups/ba6a15"
  -H "Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk="
```

> The above command returns JSON structured like this:

```json
{
    "id": "ba6a15",
    "title": "Awesome Product Group",
    "product_ids": ["ac24a3"],
    "created_at": "2016-05-15T14:02:47.000Z",
    "updated_at": "2017-08-12T23:37:13.000Z"
}
```

This endpoint retrieves a specific product group.

### HTTP Request

<code>GET https://selly.gg/api/product_groups/<span class="url-paramater">:ID</span></code>

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the product group to retrieve