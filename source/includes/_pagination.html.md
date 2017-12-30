# Pagination

> An example of paginating orders:

```shell
curl "https://selly.gg/api/v2/orders?page=10"
  -H "Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk="
```

```ruby
Selly::Orders::List(page: 10)
```

Selly offers the ability to paginate any `list` or `index` resource. The `X-Total-Pages` header returns the total number of pages for the resources at the specific endpoint you're using.

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Used for pagination
