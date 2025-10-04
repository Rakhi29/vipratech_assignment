# Preventing double charges — implementation notes

- Create Order (status=pending) before creating Stripe Checkout session.
- Use Stripe idempotency key derived from order id when creating sessions.
- Finalize order only when webhook confirms payment.
- Unique DB constraint on stripe_session_id to prevent duplicates.
- Client disables Buy button after click to prevent double-submit.
