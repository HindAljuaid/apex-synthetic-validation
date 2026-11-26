
# Apex Synthetic API Validation

## Overview
This repository contains a synthetic test case for the Brief-to-Package Validation API.

The objective was to verify that the API correctly validates a project brief, generates a structured project package, and reports validation results.

## Test Case
- **Case ID:** SYN-HIND-001
- **Project:** AI Meeting Summary Assistant
- **Client:** Nova Digital Solutions (fictional)
- **Expected result:** PASS
- **Expected score:** 100

## API Tested
- **Health endpoint:** `GET /health`
- **Validation endpoint:** `POST /validate`
- **API documentation:** https://brief-validator-api.onrender.com/docs

## Test Results
- Actual status: PASS
- Actual score: 100
- HTTP status: 200
- Validation checks: 8/8 passed
- Errors: 0
- Warnings: 0

The actual result matched the expected result.

## Repository Structure

```text
apex-synthetic-validation/
├── test_data/
│   └── synthetic_input.json
├── results/
│   ├── expected_result.md
│   └── actual_output.json
├── evidence/
│   └── test_evidence.md
├── .gitignore
└── README.md
```

## Reproduction

Check API health:

```bash
curl -i https://brief-validator-api.onrender.com/health
```

Run the synthetic validation:

```bash
curl -sS -X POST \
  https://brief-validator-api.onrender.com/validate \
  -H "Content-Type: application/json" \
  --data-binary @test_data/synthetic_input.json \
  -o results/actual_output.json \
  -w "\nHTTP Status: %{http_code}\n"
```

## Scope and Safety
- Fictional test data only.
- No production data used.
- No changes made to the live API or its configuration.
- The test was performed against the existing live validation endpoint.

