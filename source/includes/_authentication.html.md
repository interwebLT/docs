# Authentication

> To authorize, use this code:

```shell
curl "https://selly.gg/api/"
  -H "Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk="
```

```ruby
require 'selly'

# This library will automatically handle the Authorization header and encoding it
Selly.api_key = 'your api key'
Selly.api_email = 'your account email'
```

> Make sure to use the correct API authentication attributes

Selly uses API keys via the `Authorization` header to allow access to the API. You can retrieve and receive a new Selly API key at your [settings page](https://selly.gg/settings).

The `Authorization` header is made up of your account's `email` and `API key` in the format `email:api_key` and then encoded via base64.

Selly expects a valid Authorization header to be included in all requests and that it looks like the following:

`Authorization: Basic eW91cmVtYWlsOnRoaXNpc3lvdXJBUElLZXk=`

In this example, if we decode the string we'll receive `youremail:thisisyourAPIKey` which when split would mean that the email provided is `youremail` and the API key is `thisisyourAPIKey`.

<aside class="alert">A useragent must be set. We recommend you set it to be something such as <code>Yourusername - website-using-api.com</code></aside>
