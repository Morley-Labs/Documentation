# Forward & Inverse Compilation Flow Tests Specification

## Overview
This document serves as a guide for the **forward_inverse_flow_tests.py** test suite. The test suite ensures that the Morley compiler and reverse compiler maintain functional equivalence across all transformations, covering both **standard** and **inverse** compilation flows.

## Objectives
The primary objectives of these tests are:
- To validate that **Ladder Logic (LL) and Structured Text (ST) compile to IR correctly**
- To confirm that **IR translates properly to Plutus smart contracts**
- To ensure that **Plutus can be reverse compiled back into LL and ST accurately**
- To verify that the **inverse flow (Plutus → IR → LL/ST → IR → Plutus) is consistent**

---

## Test Categories

### 1. **Standard Compilation Flow Tests**
- **Ladder Logic → IR → Plutus → Reverse Compile → Ladder Logic**
- **Structured Text → IR → Plutus → Reverse Compile → Structured Text**

### 2. **Inverse Compilation Flow Tests**
- **Plutus → IR → Ladder Logic → IR → Plutus**
- **Plutus → IR → Structured Text → IR → Plutus**

Each test ensures that the transformation process is **lossless**, meaning that compiling and reversing the process results in the original input.

---

## Test Methodology

### **1. Ladder Logic → IR → Plutus → Reverse Compile → Ladder Logic**
- Convert a **Ladder Logic instruction set** into IR.
- Use the Morley compiler to generate Plutus smart contract code.
- Reverse compile the Plutus contract back into **Ladder Logic**.
- Compare the final Ladder Logic output with the original input to check for **consistency**.

### **2. Structured Text → IR → Plutus → Reverse Compile → Structured Text**
- Convert a **Structured Text program** into IR.
- Compile IR into Plutus.
- Reverse compile Plutus back into **Structured Text**.
- Ensure the result matches the original input.

### **3. Plutus → IR → Ladder Logic → IR → Plutus**
- Start with a Plutus smart contract.
- Convert it into IR using the **reverse compiler**.
- Translate IR into Ladder Logic.
- Recompile Ladder Logic into IR.
- Compile the IR back into Plutus and check if the output is **identical** to the original Plutus contract.

### **4. Plutus → IR → Structured Text → IR → Plutus**
- Convert a Plutus smart contract to IR.
- Translate IR into Structured Text.
- Convert Structured Text back into IR.
- Recompile IR into Plutus.
- Compare with the original Plutus contract.

---

## Test Assertions
Each test case performs the following checks:
1. **Correct JSON Structure:** Ensures the IR and Plutus outputs maintain the expected structure.
2. **Consistency Check:** The final output must match the original input.
3. **Error Handling:** The test should fail gracefully if an invalid transformation occurs.
4. **Edge Cases:** Nested logic, timers, counters, arithmetic operations, and comparison operators are tested.

---

## Running the Tests
To execute the test suite, navigate to the test directory and run:
```sh
python -m unittest forward_inverse_flow_tests.py
```

If specific tests need to be run individually:
```sh
python -m unittest forward_inverse_flow_tests.TestMorleyCompilationFlow.test_ladder_logic_to_plutus_and_back
```

---

## Next Steps
- **Validation Against OpenPLC Output:** Compare outputs with OpenPLC-generated equivalents.
- **Expand Test Cases:** Add more complex logic scenarios.
- **Refactor if needed:** Improve modularity and performance.

This guide serves as a reference for debugging, expanding, and maintaining the Morley compilation test suite.

