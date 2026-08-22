# GST Architecture

**Nicholas Hartman / American Milestone Inc.**

## 1. Position in the MG8 file family

```text
.mg8
  ↓
flow.ork
  ↓
.gst state/context
  ↓
.g8son conditional eligibility
  ↓
.qson realized execution trace
```

GST is the state substrate. It represents what the system/environment state is, what it was immediately prior to the current state, and which contextual fields are available to later execution layers.

## 2. Minimal chronology

A single present state provides state detection:

\[
S_t
\]

Adding the immediately prior state produces:

\[
S_{t-1}\rightarrow S_t
\]

This ordered relation is the minimum temporal structure used by GST to represent memory/continuity.

## 3. Dual observation domains

GST separates internal and external state:

```text
internal.prior   I(t-1)
internal.current I(t)

external.prior   E(t-1)
external.current E(t)
```

This prevents an external environmental change from being conflated with an internal system-state change.

## 4. Reserved placeholder structure

The established GST state-detection architecture reserves a `0,0` placeholder structure in addition to ordinary state values.

```text
prior/current state
       +
internal/external distinction
       +
reserved 0,0 placeholder structure
       ↓
higher-order state-detection geometry
```

`0,0` is treated as an architectural placeholder designation, not automatically as a physical coordinate, score, or Boolean state.

## 5. Awareness-layer progression

The framework distinguishes several stages:

```text
present-state detection
       ↓
prior/current continuity
       ↓
memory / chronology
       ↓
internal + external state comparison
       ↓
reserved placeholder capacity
       ↓
triangulated state-detection representation
       ↓
awareness-layer state
```

This is an operational/system-state definition within the GST architecture. It is not presented as a universal theory of subjective consciousness.

## 6. Intent and outcome expectation

Intent and outcome expectation are higher-order state fields that may be present in a GST profile.

They belong in GST because they characterize the represented state against which future gates and transforms are evaluated.

They should not be inferred implicitly from gate execution. If a profile uses them, they should be explicit and inspectable.

## 7. State advancement

For each channel:

```text
prior <- current
current <- new observation/state
```

Internal and external channels advance independently but can be compared jointly by downstream state-detection logic.

## 8. Relationship to gates

GST provides state; `.g8son` evaluates conditions against that state.

```text
GST: what is / what was / contextual state
G8SON: is this transform or route admissible?
ORK: what executes next?
QSON: what actually happened?
```

This separation is deliberate and should be preserved across the MG8 family.
