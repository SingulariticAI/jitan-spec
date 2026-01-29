# JITAN Conformance Requirements (v0.1)

This document defines the minimum requirements for a system to claim
**JITAN-Core compliance**.



## 1. Intent Handling

A compliant implementation MUST:

- Accept action intents containing:
  - action namespace + operation
  - immutable parameters
  - originator identity
- Canonicalize intents deterministically
- Produce a stable content hash for each intent
- Reject mutation of intents after creation

  ### Intent Hashing

An implementation MUST reproduce the exact `expected_hash` value for each published test vector.

Failure to do so indicates a non-conformant implementation.

## 2. Authorization Semantics

A compliant implementation MUST:

- Enforce **default-deny** behavior
- Require explicit authorization before execution
- Support quorum-based approval (N-of-M or role-based)
- Prevent execution without a valid authorization outcome


## 3. Notarization & Attestation

A compliant implementation MUST:

- Produce a tamper-evident authorization record
- Bind authorization to the exact intent hash
- Record:
  - signers
  - decision
  - timestamps
- Ensure attestations are immutable once finalized


## 4. Execution Seals

A compliant implementation MUST:

- Issue a **one-time execution seal** after authorization
- Bind the seal to:
  - the intent
  - the authorization decision
- Prevent seal reuse (replay protection)
- Reject expired or already-used seals


## 5. Auditability

A compliant implementation MUST:

- Preserve authorization records
- Allow independent verification of decisions
- Detect tampering or record alteration


## 6. Explicit Non-Requirements

JITAN does NOT require:

- Agent orchestration
- AI model execution
- Workflow engines
- Observability tooling
- Post-hoc monitoring


## Compliance Claim

An implementation MAY claim:

> “JITAN-Core compliant (v0.1)”

only if all MUST-level requirements above are satisfied.
