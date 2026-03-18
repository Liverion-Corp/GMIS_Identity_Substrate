# Lifecycle Concepts  
GMIS Identity Governance Substrate  
Liverion Corp

Lifecycle governance defines the permissible states and transitions of a machine identity within the GMIS standards architecture. These lifecycle semantics ensure consistent, jurisdiction‑aware behavior across heterogeneous environments and establish the authority boundaries under which identity issuance, maintenance, suspension, and revocation occur.

This document provides a conceptual overview of lifecycle states, transition rules, and governance semantics. It is intentionally non‑implementation‑specific and suitable for public, partner, and standards‑body review.

---

## 1. Purpose of Lifecycle Governance

Lifecycle governance ensures that every machine identity:

- exists under a defined authority,  
- transitions only through permissible states,  
- maintains a verifiable provenance,  
- and can be suspended or revoked under explicit governance rules.

Lifecycle semantics provide the temporal and operational structure required for consistent identity behavior across vendors, jurisdictions, and deployment environments.

---

## 2. Lifecycle States

The GMIS identity object includes a **lifecycle state** selected from a finite, governed state machine. While specific implementations may extend or refine these states, the conceptual model includes the following canonical categories:

### **2.1 Issued**  
The identity has been created under a recognized governance authority and assigned a globally unique identifier.

### **2.2 Active**  
The identity is valid, recognized, and permitted to participate in governed operations.

### **2.3 Suspended**  
The identity remains valid but is temporarily restricted from participating in governed operations.  
Suspension is reversible and governed by explicit authority rules.

### **2.4 Revoked**  
The identity is permanently invalidated under governance authority.  
Revocation is a terminal state.

### **2.5 Retired**  
The identity is no longer active due to lifecycle completion, decommissioning, or end‑of‑life processes.  
Retirement is terminal but distinct from revocation.

These states form the conceptual backbone of the lifecycle state machine.

---

## 3. Permissible Transitions

Lifecycle transitions are governed by explicit rules that define:

- which transitions are allowed,  
- which authorities may initiate them,  
- what metadata is required,  
- and what conditions must be satisfied.

Examples of permissible transitions include:

- **Issued → Active**  
- **Active → Suspended**  
- **Suspended → Active**  
- **Active → Revoked**  
- **Active → Retired**

Transitions such as **Revoked → Active** are not permissible under any circumstances.

All transitions must be:

- deterministic,  
- auditable,  
- authority‑bounded,  
- and machine‑readable.

---

## 4. Governance Authority Boundaries

Lifecycle transitions occur under the control of defined governance authorities.  
Authority boundaries specify:

- which entities may issue identities,  
- which entities may suspend or revoke them,  
- how delegated authority is inherited or constrained,  
- and how subordinate identities behave under parent transitions.

These boundaries ensure consistent, jurisdiction‑aware lifecycle behavior.

---

## 5. Metadata Requirements

Lifecycle transitions may require additional metadata, such as:

- timestamps,  
- authority identifiers,  
- jurisdictional context,  
- suspension or revocation reasons,  
- delegation references.

Metadata must be:

- explicit,  
- verifiable,  
- and semantically consistent across vendors and environments.

---

## 6. Separation from Cryptographic Material

Lifecycle semantics govern the identity object itself, not its cryptographic bindings.

- Cryptographic keys may be rotated without altering lifecycle state.  
- Certificates may expire independently of identity validity.  
- Attestations may reference identity state but do not define it.

This separation ensures long‑term stability and interoperability.

---

## 7. Interoperability Across Domains

Lifecycle semantics are designed to operate consistently across:

- cloud and edge environments,  
- heterogeneous vendors,  
- multi‑jurisdictional deployments,  
- supply‑chain and operational lifecycles.

This cross‑domain consistency is essential for global machine identity governance.

---

## 8. Scope of This Document

This document defines lifecycle concepts at a conceptual level.  
It does **not** include:

- implementation details,  
- state machine code,  
- cryptographic workflows,  
- attestation logic,  
- or operational substrate artifacts.

All implementation work is governed separately.

