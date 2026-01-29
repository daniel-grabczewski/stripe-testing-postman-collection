# Stripe QA Pack #1 (Postman)
API verification suite for Stripe **PaymentIntents**, **Refunds**, and **Idempotency** using **Stripe test mode**.

This repo is designed as a portfolio artifact: structured, documented, and runnable in Postman without any extra tooling.

## What this covers
- PaymentIntents lifecycle: create → confirm → success/declines → SCA branch
- Manual capture: requires_capture → capture → succeeded
- Refund integrity: full + partial + over-refund protection
- Idempotency: safe retry + mismatch rejection

## Repo layout
- `postman/collections/` → Postman collection JSON
- `postman/environments/` → Example environment template (no real secrets)
- `docs/` → Test cases, conventions, coverage, redaction, known issues

## Quick start (Postman)
1. Import the collection:
   - `postman/collections/stripe-qa-pack-1.postman_collection.json`
2. Import the environment template:
   - `postman/environments/stripe-test.postman_environment.example.json`
3. Duplicate the imported environment inside Postman:
   - Rename it to: `Stripe Test (Local)`
4. Set the environment variable:
   - `secretKey` → your Stripe test secret key (`sk_test_...`)
5. Select the environment in the top-right dropdown.
6. Run the test cases in order:
   - TC-00 → TC-14 (see screenshots in the evidence folder to help guide you with parameters and headers)

## Environment defaults
The template includes:
- `baseUrl = https://api.stripe.com`
- `amount = 2000`
- `currency = nzd`
- Stripe test PaymentMethod tokens (e.g. `pm_card_visa`)

## Evidence + redaction
See:
- `docs/03-evidence-and-redaction.md`
