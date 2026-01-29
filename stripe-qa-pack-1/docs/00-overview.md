# Overview

This QA pack validates core Stripe API behaviors in **test mode** using Postman:
- PaymentIntents: success + failure modes + SCA branch
- Manual capture: correct state transitions
- Refunds: full, partial, and guardrails (over-refund)
- Idempotency: safe retry vs mismatch rejection

Why this matters:
- These are high-risk money paths.
- The suite is designed to prove state correctness, error handling, and retry safety.

Key outputs:
- Postman collection + environment
- Execution guide
- Evidence + redaction rules
- Coverage map
