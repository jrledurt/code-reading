# Code Reading Progress

Updated at the end of each session. This file is the memory — if it isn't written
here, it didn't happen.

## Current status

- **Stage:** 1 — One function, no I/O
- **Exit criteria:** predict exact output on 4 of 5 unseen functions, first try; explain each line in plain English; identify inputs, outputs, and state changes without prompting.
- **Current focus:** Trace assignments in order. Treat `=` as replacement; preserve a value copied into another variable. Distinguish `%` (remainder) from `//` (floor-division quotient). Recognize that a `def` only defines until called.
- **Next session:** Re-drill the saved-variable-after-reassignment drill (ended before it), then quotient/remainder tracing (`%` vs `//`), then state-change tracing. Mix in the Python-feature overlay deck (name binding, truthiness, loops) as fresh material. Reviews now scheduled via the local FSRS deck.

---

## Recurring misses

Anything that has come up three or more times across sessions. This is the real
curriculum — items here get drilled ahead of new material, and only come off the
list after three clean sessions.

- None yet.

---

## Session log

### 2026-09-07 (Hermes session)

- Switched the code-reading runtime to Hermes and wired in a local FSRS spaced-repetition
  scheduler (two decks: `code-reading` for reading-skill concepts, `python-reading-overlay`
  for Python language features activated in step with the current stage). Both decks seeded
  with Stage 1 concepts.
- Drilled "module top-level execution order": learner correctly identified that `def run():`
  only defines the function and, with no call, nothing executes — output is nothing.
- Drilled "copied value survives later reassignment of the source" (a prior miss): learner
  got `b = a; a = 7; return b` → `3` correct on first try.
- Both answered concepts logged Good in the FSRS deck.
- Tutor framing error: the first copied-value drill wrapped the code in an uncalled `def`,
  so it tested nothing; corrected and re-asked.
- Ended before the saved-variable and quotient/remainder drills.

### 2026-09-07

- Practiced sequential assignment and exact-output tracing.
- First-try misses: a copied value after the original variable was reassigned; a saved variable after later reassignment; and the combined result of `%` and `//`.
- Recovered the copied-value and saved-variable questions after re-tracing. Correctly identified that `17 % 4` is `1`, `17 // 4` is `4`, and the program prints `5`.
- Tutor feedback error: the learner's final numeric answer of `5` was correct, but it was initially marked incorrect because the variable labels in the explanation were reversed.
- Ended before the next quotient/remainder drill.
