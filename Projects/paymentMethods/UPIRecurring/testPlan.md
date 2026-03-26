# UPI Recurring – Test Plan

## Objective
Validate subscription lifecycle using UPI recurring payments.

## Scope
- QR Code Generation on Mobile and Web-Browswers
- Subscription creation
- Payment authorization
- Recurring billing
- Upgrades/Downgrades
- Refunds on initial orders and rebill orders
- Dunning and retry schedules


## Risks
- New Rebill engine integration
- Delayed payment confirmation
- Missing webhook updates
- Payment stuck in pending state

## Test Strategy
- Manual testing
- API validation
- Simulation of failed approvals

## Environments
- Sandbox

## Tools
- Postman
- Internal dashboard