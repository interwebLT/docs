# Errors

> Errors are returned in a JSON structured like this:

```json
{
  "message": "Order not found",
}
```

> Validation errors also have an `errors` attribute

```json
{
  "message": "Validation failed",
  "errors": {
    "title": ["must be present"] 
  }
}
```

> The `errors` attribute may also be a array if there are multiple errors stacked

The Selly API uses the following error codes:

Status Code | Meaning
---------- | -------
400 | Bad Request - Invalid parameters
401 | Unauthorized - Unable to authenticate
403 | Forbidden - The request is not allowed
404 | Not Found - The specified resource could not be found.
406 | Not Acceptable - You requested a format that isn't json.
429 | Too Many Requests - You have reached the rate limit
500 | Internal Server Error - We had a problem with our server. Try again later. These are rare.
503 | Service Unavailable - We're temporarily offline for maintenance. Please try again later.