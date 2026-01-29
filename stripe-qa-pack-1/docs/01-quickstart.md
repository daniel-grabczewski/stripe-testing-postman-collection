# Quickstart

## Import
1. Import:
   - Collection: `postman/collections/stripe-qa-pack-1.postman_collection.json`
   - Environment: `postman/environments/stripe-test.postman_environment.example.json`

## Create a local environment in Postman
1. In Postman, duplicate the imported environment.
2. Rename it: `Stripe Test (Local)`
3. Set:
   - `secretKey = sk_test_...` (your test secret key)
4. Select `Stripe Test (Local)` in the environment dropdown.

## Run order
Run sequentially:
TC-00 → TC-14

Reason:
- Some test cases depend on IDs saved from earlier requests (e.g. `pi_id`).
