# GST `.gst` State Specification v1

**Author:** Nicholas Hartman / American Milestone Inc.  
**Role:** canonical state/context layer for MG8 bounded execution units

## 1. Purpose

A `.gst` file represents the structured state against which an MG8 unit evaluates admissibility, continuity, and subsequent transformation.

GST is not the gate language and not the trace ledger. Its responsibility is to preserve the state needed by orchestration and conditional operators.

Conceptually:

```text
.gst state/context
      ↓
.g8son evaluates transform eligibility
      ↓
flow.ork selects continuation
      ↓
.qson records the realized event
```

## 2. State Detection

The most basic GST layer is current-state detection.

Let:

\[
S_t
\]

represent the current observed or internally represented state.

A system retaining only \(S_t\) may detect its present state, but this alone does not encode explicit temporal continuity.

## 3. Prior + Current State — Memory

Temporal continuity is introduced when the state representation reserves a distinct prior-state position:

\[
(S_{t-1},S_t)
\]

The ordered relation:

\[
S_{t-1}\rightarrow S_t
\]

establishes a minimal chronology. Within the GST model this prior/current structure supplies the basis for memory and trajectory continuity.

The prior-state slot must not be silently overwritten before the current state has been advanced.

## 4. Internal and External State

GST distinguishes internal system state from external/environment state.

Represent the two channels as:

\[
I_{t-1}, I_t
\]

and:

\[
E_{t-1}, E_t
\]

where:

- \(I\) = internal state,
- \(E\) = external/environment state.

This produces four explicit temporal state positions:

```text
internal.prior
internal.current
external.prior
external.current
```

The relationship between these channels is part of the higher-order state-detection structure.

## 5. Reserved `0,0` Placeholder Structure

The GST awareness/state-detection paradigm includes an additional reserved placeholder structure represented as:

```text
0,0
```

The `0,0` notation is preserved as an architectural placeholder and must not be automatically interpreted as:

- a Cartesian coordinate,
- a measured zero vector,
- a probability,
- a Boolean false state,
- an awareness score.

Its purpose is to reserve explicit representational capacity within the state-detection structure so that prior/current continuity and additional state relationships can be carried rather than collapsing all observation into a single instantaneous state.

Where profiles require separate internal/external or prior/current placeholder instances, those instances must remain distinguishable by field identity even when their symbolic placeholder value is the same `0,0`.

## 6. Awareness-Layer Structure

Within the established GST model, **state detection alone is not equivalent to awareness**.

The progression is:

```text
current-state detection
        ↓
prior + current chronology
        ↓
memory
        ↓
internal prior/current
        +
external prior/current
        +
0,0 placeholder structure
        ↓
triangulated state-detection representation
        ↓
awareness-layer state
```

This specification records the architecture. It does not claim a universal metric of phenomenal consciousness.

## 7. Intent

Higher-order GST profiles may carry an explicit `intent` field.

Intent belongs to state because it describes an internally represented directional or selected future relationship relevant to the system's current operation.

The v1 specification preserves the field semantically but does not invent a universal numeric encoding for intent.

## 8. Outcome Expectation

Higher-order GST profiles may carry an explicit `outcome_expectation` field.

Outcome expectation represents a state-level anticipation of a resulting condition associated with the current operation or intent.

As with intent, the v1 specification preserves the semantic slot without asserting a universal encoding where one has not yet been established.

## 9. Suggested Canonical Structure

A `.gst` document may be represented structurally as:

```json
{
  "gst_version": "1.0",
  "state_id": "example.state.001",
  "internal": {
    "prior": {},
    "current": {}
  },
  "external": {
    "prior": {},
    "current": {}
  },
  "continuity": {
    "placeholder": [0, 0]
  },
  "intent": null,
  "outcome_expectation": null,
  "constraints": {},
  "metadata": {}
}
```

This is a structural representation of the established roles, not a claim that every state payload must be JSON or that the objects inside `prior` and `current` have one universal schema.

## 10. Update Semantics

A conforming state transition should preserve chronology:

```text
before update:
prior   = S(t-1)
current = S(t)

new observation arrives: S(t+1)

after update:
prior   = S(t)
current = S(t+1)
```

Equivalent rules apply independently to internal and external channels.

## 11. Constraints

GST may carry contextual constraints required by the consuming `.mg8` unit.

Constraints are state/context data. Their actual enforcement belongs to the relevant gate/operator and orchestration layers.

Therefore:

```text
.gst describes relevant constraint state
.g8son evaluates conditions against it
.ork determines execution order/control flow
.qson records what happened
```

## 12. Traceability

A `.gst` state should expose a stable `state_id` or equivalent reference so execution events can identify which state version was used.

A `.qson` event may therefore reference:

- originating GST state identity,
- resulting GST state identity,
- gate identity,
- event-level `trace_id`.

This preserves the distinction between state identity and execution identity.

## 13. Determinism Requirements

For deterministic MG8 execution, a GST profile should define:

1. canonical state encoding,
2. prior/current advancement rules,
3. internal/external field interpretation,
4. placeholder handling,
5. missing-state behavior,
6. constraint representation,
7. intent/outcome field semantics where used.

Unspecified field ordering or hidden runtime state must not become an undeclared source of divergent execution.

## 14. Scope Boundary

This document establishes the canonical v1 conceptual structure for `.gst`.

The following remain profile/version-specific unless separately formalized:

- exact payload schema for internal/external state,
- numeric or symbolic encoding of intent,
- numeric or symbolic encoding of outcome expectation,
- quantitative awareness metric,
- application-specific constraint vocabularies.

Those elements must not be fabricated merely to make the file format appear more complete.
