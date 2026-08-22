# GST Provenance and Scope

**Author:** Nicholas Hartman / American Milestone Inc.

This document records the current canonical baseline for the `.gst` state/context format within the MG8 file family.

## Established concepts represented in this baseline

- `.gst` as the Gestalt State layer of MG8
- present-state detection
- explicit prior-state retention
- prior/current chronology as the basis of memory
- distinct internal and external state channels
- prior/current state for both internal and external channels
- reserved `0,0` placeholder structure in the state-detection paradigm
- triangulation/coupling of those state channels as the higher-order awareness-layer structure
- explicit intent field
- explicit outcome-expectation field
- contextual constraints carried as state/context rather than hidden gate logic
- stable state identity for traceability into `.qson`

## Important semantic boundary

The `0,0` notation is preserved as a symbolic architectural placeholder. This repository does not reinterpret it as a coordinate, vector, probability, Boolean value, or awareness score.

Likewise, the repository does not fabricate a universal mathematical encoding for intent, outcome expectation, or awareness where one has not yet been established by the author.

## Relationship to MG8

The canonical role is:

```text
.mg8 bounded unit
   ↓
flow.ork
   ↓
.gst state/context
   ↓
.g8son admissibility / gate evaluation
   ↓
.qson realized execution trace
```

## Repository correction note

Earlier placeholder material described `.gst` generically as data, metadata, and configuration components. That description did not capture the established GST state-detection and continuity architecture and has been replaced by this versioned baseline.

## Scope boundary

This repository defines the `.gst` state layer and its established conceptual fields. Application-specific payload grammars and quantitative encodings should be introduced only through later explicit versioned profiles.
