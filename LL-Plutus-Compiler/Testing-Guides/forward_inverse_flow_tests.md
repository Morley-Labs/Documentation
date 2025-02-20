# Forward & Inverse Compilation Flow Test Guide

## Introduction
This guide provides step-by-step instructions for running and interpreting the `forward_inverse_flow_tests.py` test suite. This suite verifies the accuracy and consistency of the Morley compiler and reverse compiler by testing both standard and inverse compilation flows.

---

## Prerequisites
Before running the test suite, ensure you have:
- Python 3.8+ installed
- Required dependencies installed (via `pip install -r requirements.txt`)
- Properly structured Morley repository with:
  - `src/` containing `plutusladder_compiler.py`, `reverse_compiler.py`, `ir_converter.py`
  - `mappings/` containing `ladder_logic.json`, `structured_text.json`
  - `tests/` where the test file is located

---

## Test Suite Overview
### What is Being Tested?
This suite runs tests for both forward and inverse compilation:

### Standard Compilation Flow
1. Ladder Logic → IR → Plutus → Reverse Compile → Ladder Logic
2. Structured Text → IR → Plutus → Reverse Compile → Structured Text

### Inverse Compilation Flow
3. Plutus → IR → Ladder Logic → IR → Plutus
4. Plutus → IR → Structured Text → IR → Plutus

Each test ensures that no data is lost or corrupted during transformations.

---

## Running the Test Suite
### 1. Running All Tests
Navigate to the test directory and execute:
```sh
python -m unittest forward_inverse_flow_tests.py
```

### 2. Running a Specific Test
If you want to run a single test (e.g., Ladder Logic forward & back):
```sh
python -m unittest forward_inverse_flow_tests.TestMorleyCompilationFlow.test_ladder_logic_to_plutus_and_back
```

### 3. Running Tests with Verbose Output
For detailed output:
```sh
python -m unittest -v forward_inverse_flow_tests.py
```

---

## Interpreting Results
- ✅ **Pass**: The output matches the expected transformation.
- ❌ **Fail**: There is an inconsistency between input and output.
- ⚠️ **Error**: A problem occurred, possibly due to missing files or incorrect JSON formatting.

If a test fails, check:
1. Test Logs: Look for assertion errors.
2. Expected vs. Actual Output: Compare compiled results.
3. JSON Mappings: Ensure `ladder_logic.json` and `structured_text.json` contain required mappings.

---

## Next Steps
- Validate Against OpenPLC Outputs
- Expand Tests for Complex Scenarios
- Refactor and Optimize the Test Suite

For debugging issues, use:
```sh
python -m pdb forward_inverse_flow_tests.py
```
This will allow you to step through the test execution interactively.
