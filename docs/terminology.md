# Terminology  
GMIS Identity Governance Substrate  
Liverion Corp

This document defines the core terminology used throughout the GMIS Identity Governance Substrate documentation suite. Terms are defined conceptually and semantically, independent of any implementation detail, cryptographic mechanism, or vendor‑specific system. These definitions provide a stable, interoperable vocabulary for partners, auditors, and standards bodies.

---

## 1. Identity Object

A minimal, immutable governance object that establishes a machine’s existence, provenance, and lifecycle state. The identity object is independent of cryptographic material and serves as the foundational anchor for all higher‑order identity and attestation constructs.

---

## 2. Identity Asset

A governance‑issued representation of a machine’s identity, consisting of required elements (identifier, authority, timestamp, lifecycle state) and optional metadata. The identity asset is the conceptual form of the identity object.

---

## 3. Governance Authority

The entity responsible for issuing, maintaining, suspending, or revoking identity objects. Governance authorities operate within explicit authority boundaries and may delegate limited powers to subordinate entities.

---

## 4. Authority Boundary

The defined scope within which a governance authority may perform identity‑related actions. Authority boundaries determine which entities may issue identities, modify lifecycle state, or perform revocation.

---

## 5. Delegated Authority

A scoped, explicit grant of governance capability from one authority to another. Delegation is bounded, traceable, and governed by explicit rules. No implicit delegation is permitted.

---

## 6. Subordinate Identity

An identity object that inherits governance constraints from a parent identity. Subordinate identities operate within the authority and lifecycle boundaries defined by the parent.

---

## 7. Lifecycle State

A governed state representing the identity’s position within its lifecycle. Canonical states include:

- **Issued** — Identity has been created under a recognized authority.  
- **Active** — Identity is valid and permitted to participate in governed operations.  
- **Suspended** — Identity is temporarily restricted but not revoked.  
- **Revoked** — Identity is permanently invalidated.  
- **Retired** — Identity has reached end‑of‑life but was not revoked.

Lifecycle states are selected from a finite, governed state machine.

---

## 8. Lifecycle Transition

A permissible change from one lifecycle state to another, governed by explicit rules defining:

- allowed transitions,  
- required metadata,  
- initiating authority,  
- and jurisdictional constraints.

Transitions must be deterministic, auditable, and authority‑bounded.

---

## 9. Provenance

The temporal and authority‑based history of an identity object, including its creation timestamp, issuing authority, and lifecycle transitions. Provenance ensures traceability and governance integrity.

---

## 10. Optional Metadata

Additional, non‑semantic metadata that may accompany an identity object, such as:

- machine‑class metadata,  
- jurisdictional metadata,  
- delegation metadata.

Optional metadata must not alter the identity’s core meaning or lifecycle semantics.

---

## 11. Cryptographic Material (Referenced, Not Included)

Keys, certificates, or attestation artifacts that may be bound to an identity object but do not define it. Cryptographic material is logically and semantically separate from the identity object.

---

## 12. Interoperability

The ability of identity objects and governance semantics to operate consistently across heterogeneous vendors, jurisdictions, and deployment environments. Interoperability is a core requirement of the GMIS architecture.

---

## 13. Governance Rules

Explicit, machine‑readable rules defining:

- identity issuance,  
- lifecycle transitions,  
- authority boundaries,  
- delegation constraints,  
- and inheritance semantics.

Governance rules ensure consistent behavior across domains.

---

## 14. Jurisdictional Context

Metadata or governance constraints derived from legal, regulatory, or organizational jurisdictions. Jurisdictional context informs authority boundaries and lifecycle semantics.

---

## 15. GMIS (Global Machine Identity Standard)

The standards architecture under which the identity object, governance semantics, lifecycle rules, and interoperability requirements are defined. GMIS provides the conceptual and governance framework for machine identity at global scale.

---

## 16. Scope of This Document

This terminology defines conceptual semantics only.  
It does **not** include:

- implementation details,  
- cryptographic workflows,  
- attestation logic,  
- or substrate code.

All implementation work is governed separately.

