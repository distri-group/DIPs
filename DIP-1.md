## **DIP 001: Computing Power Market: Returns and refunds**

---
|DIP #   | Title  | Author  | Created  | Status  |
|---|---|---|---|---|
|001   | Computing Power Market: Returns and refunds  | Shaka  | 2-2-2024 | Approved and on the Roadmap  |
---

### Overview

Returns and refunds are an important part of the market where users defend user rights In the Distri.
AI network, on-demand equipment rental and flexible aborts reduce wasted arithmetic resources . 
Leasing flexibility will increase as a result.

**Motivation**

Distri.AI Computing Power Market is a decentralised arithmetic marketplace, and we note that in this leasing marketplace, when a user leases a device for a long period of time, he/she does not need to continue to use the device for a number of reasons and is unable to terminate the lease in advance, thus resulting in a
- Waste of Computing Power resources, the Computing Power that should have been used in production is wasted.
- Loss of economic costs, the user has to pay for the idle time.
- The equipment is disconnected and cannot be used even though it was purchased.

These are the reasons why 'returns and refunds' are necessary.From this we propose a set of criteria and refund calculations.

**Stakeholders**

This proposal impacts all members of the Distri.AI community.

### Implementation

Add `refund_order(ctx: Context<RefundOrder>)` instruction in [DistriAI-Core-Solana](https://github.com/distri-group/DistriAI-Core-Solana) (core Solana program for the DistriAI).

When a buyer wants a refund and calls this instruction, the following will happen:
- Calculate the order used duration, any part of an hour will be counted as one hour.
- Check that the order used duration must be less than the order duration.
- Calculate `order price * order used duration = order used amount`, and transfer `order used amount` DIST to the seller.
- Calculate `order amount - order used amount = order refund amount`, and transfer `order refund amount` DIST to the buyer.

### **Other Considerations**




## **Appendix**
