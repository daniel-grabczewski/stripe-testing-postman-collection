# Evidence conventions + redaction

## Evidence naming (recommended)
Request evidence:
- `TC-XX-RY-auth.png` (Auth tab)
- `TC-XX-RY-body.png` (Body tab)
- `TC-XX-RY-header.png` (Headers tab; used for idempotency)
- `TC-XX-RY-script.png` (Tests / Pre-request script)

Response evidence:
- `TC-XX-RESY-body.png`
- `...-part1.png / ...-part2.png` when response doesn’t fit
- `...-first-attempt.png / ...-second-attempt.png` for resend proofs

## Redaction policy
- Stripe secret key: fully redact
- Other Stripe IDs: partial redact (keep last 5 chars for comparisons)
- Any user/customer info: remove entirely

Rationale:
- Makes comparisons possible without leaking secrets.
