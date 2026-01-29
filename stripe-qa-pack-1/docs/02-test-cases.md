# Test Cases (Summary)

Legend:
- P1 = core path / suite gatekeepers
- P2 = edge cases

| TC    | Priority | Area                         | What it validates |
|------:|:--------:|------------------------------|------------------|
| TC-00 | P1       | Auth + reachability          | Stripe responds; PaymentIntent returned with id + status |
| TC-01 | P1       | PaymentIntent happy path     | Create + Confirm succeeds; status = succeeded |
| TC-02 | P1       | Decline (negative)           | Declined PM fails cleanly; PI ends requires_payment_method or equivalent error |
| TC-03 | P2       | Decline variant              | Insufficient funds decline behavior |
| TC-04 | P2       | SCA / auth required          | requires_action + next_action present |
| TC-05 | P1       | Input validation (amount)    | amount 0/negative rejected |
| TC-06 | P2       | Input validation (currency)  | invalid currency rejected |
| TC-07 | P1       | Manual capture lifecycle     | requires_capture → capture → succeeded |
| TC-08 | P1       | Invalid transition           | capture disallowed if not in requires_capture |
| TC-09 | P1       | Refund full                  | full refund succeeds |
| TC-10 | P1       | Refund partial correctness   | partial refund amount correct |
| TC-11 | P1       | Refund rule enforcement      | over-refund rejected |
| TC-12 | P2       | Refund input validation      | invalid refund amounts rejected |
| TC-13 | P1       | Idempotency (same request)   | same key + same request returns same result |
| TC-14 | P1       | Idempotency (mismatch)       | same key + different params rejected |
