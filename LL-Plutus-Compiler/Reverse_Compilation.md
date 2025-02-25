
# Reverse Compiler (Plutus to Ladder Logic)

---

## Overview

The **Morley Reverse Compiler** is a tool that positions Morley as a bridge between industrial technology and blockchain technology. The MRC converts **Morley-Plutus scripts** back into **Ladder Logic**. This enables industrial automation engineers to **verify**, **audit**, and **validate** Plutus-based control logic using a familiar programming paradigm. By bridging the gap between blockchain-based smart contracts and traditional industrial automation systems, the Reverse Compiler empowers engineers to harness **decentralized trust** while maintaining operational reliability and safety.

### Vision and Intent
The primary purpose of the Reverse Compiler is to:
- Provide a **transparent and verifiable** way to audit Plutus smart contracts.
- Enable **bi-directional compatibility** between Ladder Logic and Plutus, ensuring full traceability of industrial automation logic.
- Support engineers in maintaining **compliance and safety standards** by verifying on-chain logic against known industrial control patterns.
- Allow **reverse engineering** of decentralized control systems for real-world automation use cases.

This innovation establishes Morley as the leader in **industrial automation auditing** on Cardano, setting the stage for **trustless automation systems** and **programmable supply chains**.

---

## Architecture

The reverse compilation process is divided into three key stages:

### 1. Plutus Script Parsing
- **Purpose:** Extracts logical conditions, state updates, arithmetic operations, bitwise operations, and control flow instructions from **Morley-specific Plutus scripts**.
- **Compatibility:** Supports **Plutus Haskell** scripts with complex logical expressions, validators, redeemers, and state transitions.
- **Design Philosophy:** Focuses on maintaining logical integrity while mapping advanced Plutus constructs to Ladder Logic elements.
- **Output:** Produces an **Intermediate Representation (IR)** of the extracted logic, preserving the logical flow and state transitions.

### 2. Intermediate Representation (IR) Extraction
- **Purpose:** Maps extracted Plutus logic to **LadderCore IR**, ensuring correct instruction mappings.
- **Validation Checks:** Ensures logical consistency and verifies conditions before conversion.
- **Design Philosophy:** Maintains strict adherence to **industrial control standards** while preserving blockchain-enforced constraints.
- **Output:** Structured IR JSON format that accurately represents the original Plutus logic.

### 3. Ladder Logic Code Generation
- **Purpose:** Converts **IR-based conditions and operations** into fully formatted **Ladder Logic (.ll) files** or **Structured Text (.st) files**.
- **Implementation:** Supports timers (`TON`, `TOF`), counters (`CTU`, `CTD`), bitwise operations (`SHL`, `SHR`), and control flow mechanisms (`JMP`, `LBL`, `MCR`).
- **Output:** Generates **Ladder Logic programs** compatible with **OpenPLC** and other industrial automation platforms.
- **Bidirectional Compatibility:** Ensures that compiled Ladder Logic can be transformed back into Plutus, enabling **full traceability and verification**.

---

## Core Components

### 1. Reverse Compiler (`reverse_compiler.py`)
- Parses **Plutus scripts**, extracting:
  - Logical conditions (`traceIfFalse`, boolean expressions)
  - Timers and counters (`TON`, `TOF` conversions)
  - Arithmetic and state updates (`MOV`, `ADD`, `SUB` operations)
  - Bitwise operations (`SHL`, `SHR`, etc.)
  - Control flow (`JMP`, `LBL`, `MCR` handling)
- Converts extracted logic into **LadderCore IR**, maintaining the logical flow.

### 2. Utility Functions (`utils.py`)
- `save_to_file`: Saves generated Ladder Logic into `.ll` files.
- `load_plutus_script`: Loads **Morley-specific Plutus scripts** from files.
- Ensures efficient file handling, preserving the structure and integrity of converted logic.

### 3. Initialization (`__init__.py`)
- Exposes the `reverse_compile_plutus_to_ll` function for external use.
- Facilitates integration with other Morley components, including the **PlutusLadder Compiler** and **Morley Time Logic**.

---

## Timeline and Development Progress

### Initial Vision
The project originated from the need to **audit and verify** Plutus smart contracts within the context of **industrial automation**. The intent was to provide a **bi-directional compiler** that ensures logical correctness across both Ladder Logic and Plutus.

### Development Milestones
1. **Concept and Architecture Design:** Completed in mid-2024, defining the reverse compilation workflow and IR mapping strategy.
2. **Reverse Compiler:** Achieved successful extraction of logical conditions, state transitions, and arithmetic operations from Plutus scripts.
3. **Intermediate Representation (IR) Extraction:** Fully implemented, supporting complex conditions and nested logic.
4. **Ladder Logic Code Generation:** Functional but under optimization for:
    - Accurate timer and counter conversions
    - Complex bitwise operations and control flow mechanisms

### Challenges and Learning Curve
- **Nested Logic and State Machines:** Mapping deeply nested conditions and state transitions from Plutus to Ladder Logic.
- **Bi-Directional Compatibility:** Ensuring that Ladder Logic compiled to Plutus can be reverse compiled without loss of logical integrity.
- **Optimization and Performance:** Reducing conversion complexity and maintaining readability of generated Ladder Logic.

### Current Progress and Roadblocks
- **Reverse Compiler and IR Extraction:** Completed and fully functional.
- **Ladder Logic Code Generation:** Needs optimization for:
    - Complex state machines and advanced control flows
    - Maintaining readability while preserving logical constraints
- **Documentation and Testing:** Requires additional documentation and comprehensive testing scenarios.

---

## Usefulness and Impact

### Real-World Applications
- **Verification and Auditing:** Auditing Plutus-based automation logic for compliance, safety, and regulatory standards.
- **Bi-Directional Traceability:** Ensuring logical consistency between Ladder Logic and Plutus, enabling on-chain auditing.
- **Industrial Automation:** Verifying on-chain state transitions for industrial automation systems.
- **Security and Compliance:** Ensuring safety-critical systems comply with industry standards by verifying on-chain logic against known control patterns.

### Contributions to Morley Ecosystem
- Establishes Morley as the **gold standard** for **Industrial Automation Auditing on Cardano**.
- Ensures **bi-directional traceability** between traditional PLC programming and decentralized smart contracts.
- Lays the foundation for **Verifiable Automation Systems**, enabling trustless audits and regulatory compliance.

---

## Roadmap and Next Steps

### Short-Term Goals
- **Optimization of Ladder Logic Code Generation:** Improve performance for complex state machines and nested conditions.
- **Enhanced Error Handling and Debugging:** Implement detailed error reporting and validation logs.
- **Public Release and Community Feedback:** Open-source release on GitHub with comprehensive documentation.

### Long-Term Vision
- **Full Feature Parity with OpenPLC:** Achieve complete compatibility with industry-standard Ladder Logic instructions.
- **Integration with Morley Time Logic:** Support hybrid time enforcement for real-time and slot-based execution.
- **Community Collaboration and Open Innovation:** Foster community contributions, feature requests, and real-world use cases.

---

## Conclusion

The **Morley Reverse Compiler** is an innovative tool that bridges the gap between **blockchain-based smart contracts** and **traditional industrial automation systems**. By providing bi-directional compatibility and full traceability, it empowers engineers to **verify, audit, and validate** on-chain automation logic in a familiar Ladder Logic format. This enhances **security, compliance, and operational reliability**, paving the way for **trustless industrial automation** and **programmable supply chains**.

---

## References and Further Reading

- [Morley Project Overview](https://morleylang.org)
- [Plutus Documentation](https://plutus.iohk.io/)
- [OpenPLC Project](https://www.openplcproject.com/)
