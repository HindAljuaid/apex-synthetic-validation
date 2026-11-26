# Synthetic Validation Test Evidence

## Test Information
- Case ID: SYN-HIND-001
- Project: AI Meeting Summary Assistant
- Date: 26 November 2026
- Endpoint: POST /validate
- API URL: https://brief-validator-api.onrender.com/validate

## Test Objective
Verify that the Brief-to-Package Validation API
correctly validates a synthetic project brief and
generates a structured project package.

## Synthetic Input
File: test_data/synthetic_input.json

All client and project information is fictional.

## Expected Result
- Expected status: PASS
- Expected score: 100

## Actual Result
- Actual status: PASS
- Actual score: 100
- HTTP status: 200
- Validation checks: 8 passed out of 8
- Errors: 0
- Warnings: 0

## Health Check
- Endpoint: GET /health
- HTTP status: 200
- Response: {"status":"healthy"}

## Evidence Files
- test_data/synthetic_input.json
- results/actual_output.json
- evidence/test_evidence.md

## Reproduction Commands

Health check:

curl -i https://brief-validator-api.onrender.com/health

Validation:

curl -sS -X POST \
  https://brief-validator-api.onrender.com/validate \
  -H "Content-Type: application/json" \
  --data-binary @test_data/synthetic_input.json \
  -o results/actual_output.json \
  -w "\nHTTP Status: %{http_code}\n"

## Conclusion
The synthetic validation test completed successfully.
The actual result matched the expected PASS result,
with a score of 100 and all eight checks passing.
No production data or live-system changes were used.
