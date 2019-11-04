# Niu Pay

Your Api Key : `xxxxxxxxxxxx`

To issue a payment you need to request the following Knet URL `https://niupay.me/api/requestKnet` with method `post` using the following parameters:

```json
{
    "apikey": "xxxxxxxxxxxx",
    "type":  "Accepts either 1 or 2, 1 for testing and 2 for live",
    "trackid": "Accept alphanumeric value with maxlength 255",
    "amount": "the amount in kwd",
    "language": "Accepts either 1 or 2, 1 for English and 2 for Arabic",
    "responseUrl": "url where the response data will be send",
    "successUrl": "url to be called when the payment goes through", 
    "errorUrl": "url to be called if the payment is invalid",
}
```
The response for the request will be:
```json
{
    "status": true,
    "message": "Proceed to Knet",
    "paymentID": "6555084431783610",
    "paymentLink": "https://www.knetpaytest.com.kw:443/CGW302/hppaction?formAction=com.aciworldwide.commerce.gateway.payment.action.HostedPaymentPageAction&?PaymentID=6555084431783610"
}
```
__You have to save the paymentID and redirect the user to paymentLink.__

The `responseUrl` will be called by a `post` with the following information
```json
{
    "paymentID": "4573662301983620",
    "trackid": "1", 
    "tranid": "4002208311983620",
    "ref": "836219980163",
    "niutrack": "1621113831112408"
}

```
and then after that either the `successUrl` or the `errorUrl` url will be called via a `get` call with the following as a parameter `paymentID`

you can test using the following cards for KNET.

Bank Name | Card Number | date | pin | result
----------|-------------|------|-----|--------
Knet Test Card | 888888 0000000001 | anything | anything | SUCCESSFUL
Knet Test Card | 888888 0000000002 | anything | anything | UNSUCCESSFUL

you can check a live example using postman using the following link
https://documenter.getpostman.com/view/1197088/Rzn9u21K
