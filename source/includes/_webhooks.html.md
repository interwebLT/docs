# Webhooks

> A example webhook notification on a paid order event

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
    "custom": {},
    "webhook_type": 1,
    "created_at": "2016-11-27T14:20:34.000Z",
    "updated_at": "2016-12-05T21:31:15.000Z"
  }
```

Webhooks are a HTTP callback event that is sent to the Webhook URL specified for the affected order. All webhook requests are sent as a `POST` request and are handled independently from the event, asynchronously.

The content sent in the webhook is a JSON object of the resource that the webhook is related to. If it was a order webhook, a [order object](#order-object) will be sent.

Each webhook request contains a `webhook_type` parameter

Webhook Type | Meaning
---------- | -------
1 | Order paid
2 | Order chargeback/reversal
3 | Dynamic product
4 | Product out of stock
5 | Product reached stock warning level

