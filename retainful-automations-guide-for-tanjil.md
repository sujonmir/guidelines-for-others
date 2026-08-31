# Retainful — 2 steps to go live

Tracking is already live & tested. Only these two dashboard clicks remain.

> ⚠️ Log in with the **owner / full-access** Retainful account first — the test login can't publish (needs **Edit & Publish Content** permission).

## 1. Turn on the Cart-abandoned emails

1. Automations → open **REST - Cart abandoned**.
2. Click the **Abandoned Cart** trigger → check **Customer filters**.
3. It should read **"No customer filters applied"** (the `Email contains retainful` test-gate is already removed). If the gate is still there → **Edit** → delete it → **Save**.
4. Top-right → **Publish Changes**. ✅

*Now real subscribers get the recovery email 30 min after add-to-cart — auto-stops if they check out or buy.*

## 2. Finish the Checkout-abandoned flow

1. Open **REST - Cart abandoned** → open **Email 1** → **Duplicate** it (keeps brand + recovery link).
2. Open **REST - Checkout abandoned** → after the `Wait 1 hour` step, add a **Send Email** node → paste the duplicated email.
3. Tweak wording to a "you were one step away at checkout" tone (copy below).
4. Top-right → **Publish Workflow**. ✅

**Subject:** You're one step away 👀
**Body:** Hi {{first_name|there}}, you made it all the way to checkout — your items are still saved. Pick up right where you left off. [ Complete my order → ] — Swiss Tides

---

✅ After both publish: tell Retainful support it's fixed so they can run their final test.
