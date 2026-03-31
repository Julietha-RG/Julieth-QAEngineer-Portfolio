# Objective

After introducing Pix Automatico as new Payment Method to the Available payment methods in all checkout and storefront types, validate automatic recurring payments using Pix, focusing on asynchronous flows, delayed confirmations, and retry behavior. <br>
Country: Brazil <br>
Currency: BRL <br>

## Scope

### In Scope

* Subscription creation with Pix
* Payment request lifecycle
* Automatic rebilling behavior
* Payment approval via API (simulator)
* Handling of pending and expired states
* Refunds

## Key Risks

* Payment remains in pending indefinitely
* No failure simulation available
* Missing confirmation from provider
* Incorrect retry logic
* Subscription active without confirmed payment

## Test Strategy

* Manual testing
* API-driven approval simulation
* Time-based validation (waiting for expiration)
* Negative testing via non-approval

## Constraints

* No official failure simulation
* Long testing cycles (waiting for retries)

## Tools

* Postman
* Internal API
* Dashboard

## Success Criteria

* Payments transition correctly across states
* Retry logic behaves as expected
* No incorrect subscription activation
* Regression on pre existing payment methods. 
