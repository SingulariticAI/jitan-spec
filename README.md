# jitan-spec
This specification defines JITAN (Just-In-Time Authorization & Notarization), a protocol for multi-signature authorization of actions performed by autonomous systems including AI agents, automated workflows, and robotic systems.

## JITAN provides:
-	Multi-signature authorization requiring approval from multiple parties before action execution
-	Cryptographic proof of authorization using digital signatures
-	Policy-driven decision making with configurable thresholds and quorums
-	Immutable audit trails with append-only attestation records
-	Replay protection via one-time execution tokens
-	Budget and rate limiting to prevent abuse
The protocol is designed to prevent unauthorized actions while maintaining operational efficiency through sub-second authorization decisions.


## Status

**JITAN is an open, draft specification (v0.1).**

- This repository defines the **protocol and requirements**
- Reference implementations are forthcoming
- Feedback and independent implementations are encouraged

This spec uses **RFC 2119** normative language (MUST / SHOULD / MAY).

## Conceptual Model

JITAN treats authorization as a **notarial act**:

- An action is proposed
- Independent parties attest to its validity
- A cryptographic record is produced
- Execution is permitted exactly once

JITAN is to AI actions what a notary is to legal documents.

## **Quick Orientation**

## Repository Structure

- **README.md** — Overview and scope
- **SPEC.md** — Full normative specification
- **CONFORMANCE.md** — What an implementation MUST support
- **schemas/** — Canonical JSON schemas
- **test-vectors/** — Validation examples

If you want to implement JITAN, start with **CONFORMANCE.md**.
