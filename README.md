# GST / `.gst`

**GST** is Nicholas Hartman / American Milestone Inc.'s Gestalt State representation layer for the MG8 file family.

A `.gst` file carries the structured state, temporal continuity, state-detection context, and higher-order state fields that a bounded `.mg8` unit evaluates through orchestration and gate logic.

## Role inside MG8

```text
.mg8 unit
   ↓
flow.ork
   ↓
.gst state/context
   ↓
.g8son gate / transform eligibility
   ↓
.qson execution trace
```

`.gst` is the **state layer**. It is intentionally separate from `.g8son` gate logic and `.qson` trace output.

## Core state progression

The established GST state-detection model distinguishes:

```text
current state only
    ↓
state detection

prior state + current state
    ↓
linear chronology / memory

internal prior/current
        +
external prior/current
        +
reserved 0,0 continuity placeholders
    ↓
triangulated state-detection structure
    ↓
awareness-layer representation
```

The `0,0` structure is preserved as a reserved placeholder mechanism in the state-detection paradigm. It is **not** treated here as a conventional Cartesian coordinate or arbitrary numeric score.

## Memory

A system that retains only the present state can detect state but does not yet possess explicit temporal continuity in this model.

The introduction of a prior-state slot produces:

```text
S(t-1) → S(t)
```

and therefore an ordered history sufficient to represent memory and trajectory continuity.

## Internal and external state

GST distinguishes the system's internal state from the state of its external environment. Prior/current pairs can therefore be represented on both sides:

```text
Internal:  I(t-1), I(t)
External:  E(t-1), E(t)
```

Their coupled comparison supplies the state-detection geometry used by higher-order GST profiles.

## Intent and outcome expectation

Higher-order `.gst` profiles may include **intent** and **outcome expectation** as explicit state fields. These are part of the state representation, not hidden runtime assumptions.

This repository does not invent a universal mathematical encoding for intent or outcome expectation where one has not yet been specified; the fields are preserved as named semantic slots for versioned profiles.

## Repository structure

- [`spec/gst_v1.md`](spec/gst_v1.md) — canonical GST v1 state specification
- [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) — state-detection and continuity architecture
- [`docs/STATE_DETECTION.md`](docs/STATE_DETECTION.md) — prior/current, internal/external, and `0,0` semantics
- [`docs/PROVENANCE.md`](docs/PROVENANCE.md) — provenance and scope boundary
- [`examples/basic.gst`](examples/basic.gst) — minimal structured example

## Status

GST is being formalized as the canonical state/context layer of MG8. The repository distinguishes established concepts from fields whose precise quantitative encoding remains an open versioned-specification task.
