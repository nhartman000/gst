# GST State Detection and Continuity

**Nicholas Hartman / American Milestone Inc.**

## 1. State detection is the base layer

GST begins with the distinction between detecting a state and retaining continuity across states.

Current-state detection is:

\[
S_t
\]

This answers only: **what is the state now?**

## 2. Memory requires chronology

Adding a prior-state slot creates:

\[
S_{t-1}\rightarrow S_t
\]

This is the minimum explicit chronology used by GST to represent memory.

The distinction is architectural:

```text
state detection = current state
memory = prior state + current state
```

## 3. Internal and external state channels

GST tracks state on two sides of the system boundary:

```text
Internal
  prior   I(t-1)
  current I(t)

External
  prior   E(t-1)
  current E(t)
```

This makes it possible to distinguish a change originating inside the system from a change originating in the external environment.

## 4. `0,0` placeholder

The state-detection paradigm reserves an additional symbolic placeholder represented as:

```text
0,0
```

It marks reserved representational capacity in the continuity/state-detection structure.

The notation is deliberately preserved without converting it into another conventional construct. In particular, `0,0` is not defined here as a Cartesian position, a zero-valued measurement, or an awareness score.

## 5. Triangulated state detection

The higher-order structure combines:

```text
internal prior/current
        +
external prior/current
        +
0,0 placeholder capacity
```

The result is a richer state-detection structure than instantaneous observation alone.

In the established GST framing, this combined continuity and cross-boundary comparison forms the fundamental architecture from which the awareness layer emerges.

## 6. Intent and outcome expectation

GST can carry two additional explicit state concepts:

- `intent`
- `outcome_expectation`

These belong to the state representation because they describe an internally represented directional condition and an anticipated result against which subsequent transforms can be evaluated.

The repository does not currently define a universal scalar/vector encoding for either field. Profiles that use them must define their representation explicitly.

## 7. Update invariant

A valid temporal update preserves the old current value before advancing:

```text
prior <- current
current <- new
```

This rule applies separately to internal and external channels.

If the prior slot is overwritten or omitted, chronology is lost and the state collapses back toward instantaneous detection.
