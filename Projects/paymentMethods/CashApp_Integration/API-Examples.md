# Payment API Testing Examples

### Create Payment with CashApp Cashtag already saved into account 

| Test Case | Expected Result | Actual Result | Status |
|:---|:---|:---|---|
| Create Payment - Valid Account | Order is created successfully using the previously <br> saved CashApp account | - Order created successfully <br> - Response returned HTTP 200 <br>  - Payment type returned as "cashapp" | PASS ✅ |
| Create Payment - Invalid Account | Order does not get created <br> Correct error message displayed | - Order does not get created <br> - Response returned HTTP 400 - Bad Request <br>  - "account not found" error message displayed | PASS ✅ |

### Requests
```
POST /orders

{
"account": "{{account-id}}",
    "items": [{
            "product": "digital-product-download-fee-1",
            "quantity": 3
        }
    ]
}
```
```

POST /orders

{
  "account": "invalid-account-id",
  "items": [
    {
      "product": "digital-product-download-fee-1",
      "quantity": 3
    }
  ]
}
```
### Responses 
```
200 Code

{
    "order": "IbD18rSUSW-o0WqmrDYkjw",
    "id": "IbD18rSUSW-o0WqmrDYkjw",
    "reference": "SEP260612-3131-17123",
    "buyerReference": null,
    "ipAddress": null,
    "completed": true,
    "orderLevelCouponApplied": false,
    "changed": 1781224913313,
    "changedValue": 1781224913313,
    "changedInSeconds": 1781224913,
    "changedDisplay": "6/12/26",
    "changedDisplayISO8601": "2026-06-12",
    "changedDisplayEmailEnhancements": "Jun 12, 2026",
    "changedDisplayEmailEnhancementsWithTime": "Jun 12, 2026 12:41:53 AM",
    "language": "en",
    "live": true,
    "currency": "USD",
    "payoutCurrency": "USD",
    "payment": {
        "type": "cashapp"
    }
    ]
}
```
```
400 Bad Request

{
    "message": "required",
    "params": [
        "account not found"
    ]
}
```


