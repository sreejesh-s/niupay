## Niupay FCC SMS

Sends an SMS message via the Niupay FCC SMS gateway.

### Authentication

This endpoint requires a **Bearer Token** for authorization. Include the token in the `Authorization` header:

```
Authorization: Bearer <your_token>
```

### Request

**Method:** `POST`  
**URL:** `https://sms.niupay.me/fcc`  
**Body Type:** `form-data`

### Body Parameters

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| `phone` | text | Yes | The recipient's phone number |
| `message` | text | Yes | The SMS message content to be sent |
