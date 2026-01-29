# Coverage map

## PaymentIntents
Endpoints:
- `POST /v1/payment_intents` (create)
- `POST /v1/payment_intents/{pi_id}/confirm` (confirm)
- `POST /v1/payment_intents/{pi_id}/capture` (capture)

Validated:
- success path (succeeded)
- decline paths (4xx / requires_payment_method)
- SCA branch (requires_action + next_action)
- manual capture correctness
- invalid transition rejection

## Refunds
Endpoint:
- `POST /v1/refunds` (refund by payment_intent)

Validated:
- full refund success
- partial refund success + amount correctness
- over-refund rejected
- invalid amount rejected

## Idempotency
Validated:
- safe retry returns same result
- mismatch returns idempotency error
