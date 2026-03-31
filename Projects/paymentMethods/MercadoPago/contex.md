# MercadoPago Context 
## Introducing Argentina
Paymenth Platform already supports MercadoPago for Latam Markets
- Chile
- Brazil
- Mexico

We are going to introduce Argentina support, meaning MercadoPago will be introduced as a Visible and actionable PM(Payment Method) for Argentinan buyers limited to ARS currency.
This payment method supports One Time Purchases only. 

## QA Goals for the Project
- Validate MercadoPago displays for One Time Purhcases products
- Validate MercadoPago does not display on storefronts set to accept recurring payment methods unless is a perpetual product
- Validate Buyers get redirected to MercadoPago interface and are sent back to "Confirmation" page within our platform
- Validate payment Lifecycle by using Logs, statuses and webhooks
