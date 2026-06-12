### Test Plan Organized in Modules - Jira
<img width="777" height="415" alt="CashApp Test Plan" src="https://github.com/user-attachments/assets/293eb5fd-648a-446e-8264-cd5545e1f755" />


# Test Cases
### Module 1: Checkout & Initial Charge
## 🛒 CashApp Display at Checkout

* [ ] CashApp is displayed as a selectable payment option when enabled for the store.
* [ ] CashApp does not appear on non-US storefronts.
* [ ] CashApp does not appear when the cart currency is not USD.

---

## 💳 Customer Can Complete a Purchase

* [ ] Customer selects CashApp and successfully completes the authorization flow.
* [ ] Order is created successfully.
* [ ] Customer receives an order confirmation.
* [ ] Order status in the FastSpring dashboard shows **Completed**.
* [ ] Payment status shows **Captured** (not Pending or Failed).

---

## 🔄 Payment Method Storage

* [ ] When store setting is **Do Not Allow** or **Allow Opt-Out**, the customer's Cashtag and Customer ID are stored.
* [ ] When store setting is **Allow Opt-In** or the purchase is a one-time product, the payment method is not stored.

---

## 📊 Sumo Logic Validation

* [ ] Log entry confirms CashApp was selected and routed successfully.
* [ ] No routing failures or unknown payment method warnings are present.

---

## 📡 Webhook Validation

* [ ] An `order.completed` event is triggered.
* [ ] The merchant endpoint successfully receives the webhook.
* [ ] The webhook payload contains:

```json
{
  "payment": {
    "type": "cashapp"
  }
}
```

---

## ⚠️ Edge Cases

### Customer Cancels Authorization

* [ ] Buyer cancels from the CashApp authorization screen.
* [ ] Order is not completed.
* [ ] Buyer is returned to checkout.
* [ ] No charge occurs.

### Browser Closed After Approval

* [ ] Buyer approves payment in CashApp.
* [ ] Buyer closes the browser before returning to checkout.
* [ ] Order still completes within a few minutes.
* [ ] Webhook recovery successfully finalizes the transaction.
* [ ] Final status is verified in the FastSpring dashboard.

---

## 🚫 Out of Scope

* Recurring Payments & Rebills
* Refunds, Partial Refunds & Disputes
* Account Management Portal Display
* Dunning
