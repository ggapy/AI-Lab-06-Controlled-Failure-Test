# AI Lab 06 — Controlled API Failure Handling with n8n

## Overview

This project demonstrates how to detect, capture, reconcile, and report AI API failures using **n8n, OpenAI, and JavaScript**.

Rather than testing only successful AI responses, this lab deliberately triggers real OpenAI API errors and verifies that the workflow handles them without losing track of the affected test cases.

The goal is to demonstrate a key capability required in business AI automation: **reliable error handling and transparent evaluation reporting**.

## Technologies

- **n8n** — Workflow orchestration
- **OpenAI API** — AI model integration and controlled error generation
- **JavaScript** — Validation, error processing, metrics, and reporting
- **JSON** — Structured workflow and test data
- **Markdown** — Evaluation report generation

## Workflow Architecture

The workflow contains 15 n8n nodes.

The main processing sequence is:

1. **Manual Trigger** — Starts the evaluation.
2. **15 Test Cases** — Generates labeled customer messages.
3. **Message a model** — Calls the OpenAI API.
4. **Capture API Failures** — Records genuine API errors and associates them with test cases.
5. **API Failure Summary** — Aggregates errors by category.
6. **Evaluate Predictions** — Evaluates successfully completed classifications, if any.
7. **Category Metrics / Confusion Matrix** — Calculates classification metrics.
8. **Evaluation Coverage** — Detects missing predictions and calculates coverage.
9. **Merge Evaluation Results** — Combines evaluation and error information.
10. **Unified Evaluation Report** — Reconciles missing predictions with captured API errors.
11. **Export Evaluation Report** — Generates a downloadable Markdown report.

Additional simulation nodes are included for testing and development.

## Controlled Failure Methodology

The OpenAI node is deliberately configured with an invalid model identifier:

`invalid-model-lab06-test`

This causes the OpenAI API to return an actual model-not-found error.

The workflow is configured to continue processing those errors instead of terminating the entire evaluation.

For every failed request, the workflow attempts to preserve the original test case ID, expected classification, error message, and capture timestamp.

The final report reconciles captured API failures against missing predictions.

## Verified Test Results

**Test date:** November 13, 2026

| Metric | Result |
|---|---:|
| Expected test cases | 15 |
| Successful predictions | 0 |
| Captured API failures | 15 |
| Failures matched to missing predictions | 15 |
| Unexplained missing predictions | 0 |
| Evaluation coverage | 0% |
| Classification accuracy | N/A |

### Failures by Category

| Category | API Failures |
|---|---:|
| Billing | 6 |
| Sales | 3 |
| Support | 3 |
| Other | 3 |
| **Total** | **15** |

**Result:** All 15 deliberately triggered API errors were captured and reconciled with their missing predictions.

Because no classifications completed, classification accuracy cannot be evaluated. The 0% coverage result is expected in this controlled all-failure scenario.

## What This Project Demonstrates

- Detection of genuine API errors
- Continued workflow execution after API failures
- Preservation of test-case context
- Structured error collection and aggregation
- Identification of missing AI predictions
- Reconciliation of missing predictions with API failures
- Accurate reporting when classification accuracy is unavailable
- Automated Markdown report generation

## How to Reproduce

1. Import `AI_Lab_06_Controlled_Failure_Test_PUBLIC.json` into n8n.
2. Configure your own OpenAI API credentials.
3. Retain the deliberately invalid model identifier.
4. Verify that the OpenAI node is configured to continue on error.
5. Execute the workflow manually.
6. Inspect the API failure summary and unified evaluation report.
7. Download the generated Markdown report.

**Note:** The intentionally invalid model is part of the test. Replace it with an accessible, valid model only when adapting the workflow for successful classification tests.

## Limitations

- The dataset contains only 15 manually designed test cases.
- Only the controlled all-failure scenario is validated in this lab.
- Partial-failure handling remains untested in this workflow.
- The test exercises a model-not-found API error, not every possible API failure type.
- API reliability, latency, and production performance were not evaluated.
- The results do not establish production readiness.

## Workflow Export

The repository includes a sanitized n8n workflow JSON file.

The public export excludes credential objects and pinned execution data. Users must configure their own credentials after importing.

## Portfolio Context

This project is part of a hands-on **AI Generalist learning portfolio** focused on building, integrating, evaluating, and maintaining practical AI automation solutions.

It emphasizes engineering practices beyond prompt design, particularly **failure handling, observability, data integrity, and trustworthy evaluation**.
