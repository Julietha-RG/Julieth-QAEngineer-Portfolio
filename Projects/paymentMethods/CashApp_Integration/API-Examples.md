### API Examples - Postman

## Create Payment with CashApp Cashtag already saved into account 

### Request

POST /orders

{
"account": "{{account-id}}",
    "items": [
        {
            "product": "digital-product-download-fee-1",
            "quantity": 3
        }
    ]
}
