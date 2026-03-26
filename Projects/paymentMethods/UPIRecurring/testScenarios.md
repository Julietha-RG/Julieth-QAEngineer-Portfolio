# Test Scenarios – UPI Recurring

## Subscription Creation

* User creates subscription with UPI
* Payment request is generated correctly
* Subscription enters pending state

## Payment Approval Flow

* Payment approved within valid window - on User Bank App
* Subscription becomes active
* Webhooks get triggered
* Buyer facing experience with notification emails is fullfilled

## Payment Not Approved

* Payment request expires - Validate expiration window 24h
* System retries (when applicable)
* When initial order not approved changes to "Canceled" status
* When Subscription renewal order fails dunning and retry logic runs

## Recurring Billing

* System generates next payment request
* Bank approves, existing funds → success
* Bank does not approve → retry up to failure schedule

## Changes
### Upgrade

* Change plan while subscription is active
* Correct amount charged when --proration:true--
* Next billing cycle with new pricing gets payment authorized 

### Downgrade
* Change plan
* If proration applicable refund initiated
* Lower amount applied correctly upon next billing cycle

## API Validation

* Available functions in UI are valid fuctions in API
* Subscription status is consistent across systems
