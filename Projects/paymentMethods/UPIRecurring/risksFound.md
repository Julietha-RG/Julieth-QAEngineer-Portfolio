# Bugs Found – UPI Recurring
During my testing I registered around 116 areas of improvement

## Highlighted Risk areas
 * When subscription came from Credit Card and end-used changed payment method to UPI system was skipping to create rebill request order
 * QR Code creation did not expire at first and created duplicate payment on Bank App

There were other cosmetical issues reported and all of them were resolved during development. Some had to be resolved after initial release deployment.