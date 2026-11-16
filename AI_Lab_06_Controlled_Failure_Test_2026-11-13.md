> **LAB 06 – Controlled failure test: All 15 invalid-model API errors were captured and reconciled. The all-failure scenario is validated; partial-failure handling remains untested.**

# AI Classification Evaluation Report

Evaluation date (UTC): 2026-11-13T22:05:15.912Z
Model: invalid-model-lab06-test (deliberately invalid; no successful predictions)
Workflow: AI Lab 06 - API Error Handling

## Overall Results

Expected test cases: 15
Completed predictions: 0
Correct predictions: 0
Incorrect predictions: 0
Accuracy: N/A (no completed predictions)

## Category Performance

| Category | Cases | Precision | Recall | F1 |
|---|---:|---:|---:|---:|
| Billing | 0 | N/A | N/A | N/A |
| Sales | 0 | N/A | N/A | N/A |
| Support | 0 | N/A | N/A | N/A |
| Other | 0 | N/A | N/A | N/A |


## Confusion Matrix

Rows = actual category; columns = predicted category.

| Actual | Billing | Sales | Support | Other |
|---|---:|---:|---:|---:|
| Billing | 0 | 0 | 0 | 0 |
| Sales | 0 | 0 | 0 | 0 |
| Support | 0 | 0 | 0 | 0 |
| Other | 0 | 0 | 0 | 0 |

## Failed Test Cases

No classifications were completed; classification accuracy cannot be evaluated.

## Evaluation Limitations

- Small, manually designed test dataset.
- Results do not guarantee production accuracy.
- Real-world customer messages require further testing.
- API reliability and latency are not evaluated.
- Future prompt or model changes require regression tests.

## Evaluation Coverage

Expected test cases: 15
Completed predictions: 0
Missing predictions: 15
Evaluation coverage: 0%
Coverage status: partial

Missing test IDs: 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15

Missing predictions require investigation.
They are not automatically classified as API failures.

## API Failure Analysis

Captured API failures: 15
Missing predictions: 15
Failures matching missing predictions: 15
Unexplained missing predictions: 0

### Failures by Category

| Category | Failures |
|---|---:|
| Billing | 6 |
| Sales | 3 |
| Support | 3 |
| Other | 3 |

Unknown categories: 0

### Affected Test Cases

- Test 1: Billing — The resource you are requesting could not be found
- Test 2: Billing — The resource you are requesting could not be found
- Test 3: Sales — The resource you are requesting could not be found
- Test 4: Sales — The resource you are requesting could not be found
- Test 5: Support — The resource you are requesting could not be found
- Test 6: Support — The resource you are requesting could not be found
- Test 7: Other — The resource you are requesting could not be found
- Test 8: Other — The resource you are requesting could not be found
- Test 9: Billing — The resource you are requesting could not be found
- Test 10: Billing — The resource you are requesting could not be found
- Test 11: Support — The resource you are requesting could not be found
- Test 12: Sales — The resource you are requesting could not be found
- Test 13: Billing — The resource you are requesting could not be found
- Test 14: Other — The resource you are requesting could not be found
- Test 15: Billing — The resource you are requesting could not be found

### Unexplained Missing Predictions

None

### Evaluation Interpretation

Classification accuracy: N/A (no completed predictions)
Evaluation coverage: 0%

No model predictions were completed. Classification accuracy is not applicable.
The evaluation uses 15 manually labeled test cases and does not establish production accuracy.
Controlled testing confirmed that all 15 invalid-model API errors were captured and reconciled. Partial-failure handling remains untested.
