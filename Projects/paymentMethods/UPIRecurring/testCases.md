# Test Cases – UPI Recurring

## TC-01: Create Subscription (UPI)

**Steps:**

1. Select subscription product
2. Choose UPI as payment method
3. Confirm purchase

**Expected:**

* Payment QR Code - request generated
* Subscription status = Pending

## TC-02: Approve Payment

**Steps:**

1. Locate pending order
2. Approve payment via Razorpay API

**Expected:**

* Payment status = Success
* Subscription = Active
* Webhooks triggered
* CAPTURE Funds log successfull
* Sellers balance updated
* Buyer experience and notification successfull

## TC-03: Do Not Approve Payment

**Steps:**

1. Create subscription request
2. Do not approve payment
3. Wait for expiration

**Expected:**

* Payment expires after 24h
* Subscription not activated - transition to cancel status

---

## TC-04: Upgrade Subscription

**Steps:**

1. Active subscription
2. Upgrade plan
3. Approve proration

**Expected:**

* Prorated order goes into pending to pay status
* Subscription remains active
* Next billing cycle gets aproved with new amount

## TC-05: Recurring Payment Failure

**Steps:**

1. Active subscription
2. Do not approve next cycle

**Expected:**

* Retry based on dunning and retry schedule
* Subscription status updated correctly
