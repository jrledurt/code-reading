# Code Reading Progress

Updated at the end of each session. This file is the memory — if it isn't written
here, it didn't happen.

## Current status

- **Stage:** 1 — One function, no I/O
- **Exit criteria:** predict exact output on 4 of 5 unseen functions, first try; explain each line in plain English; identify inputs, outputs, and state changes without prompting.
- **Current focus:** Trace assignments in order. Treat `=` as replacement; a reassignment inside a loop is a rebind (builds a new value), never an in-place fill — mutation happens only via `.append()` etc. Where a function exits (early `return` fires the moment the condition is met, not after the scan). Container truthiness is decided by empty-vs-non-empty, not by contents (`[0]` and `[None]` are truthy; `[]`, `""`, `0`, `None` are falsy).
- **Next session:** FSRS will resurface two concepts rated weak this session — early-return exit location and container truthiness — drill those first with fresh code. Then continue string-accumulation-by-reassignment (understanding clicked, untested by a committed answer) and mix in the overlay deck (for-loop vs range, name binding) as they come due.

---

## Recurring misses

Anything that has come up three or more times across sessions. This is the real
curriculum — items here get drilled ahead of new material, and only come off the
list after three clean sessions.

- None yet.

---

## Session log

### 2026-09-08 (Hermes session)

- Continued Stage 1. All copying/reassignment mechanisms from the prior miss set were now first-try correct: saved-variable-persists-after-reassignment (100 → 100), copied-value-survives (implicit in later drills), state-change tracing across a,b,c (0,2,2).
- Quotient/remainder solid: `47 // 5` = 9, `47 % 5` = 2, tuple (9,2) correct first try.
- Mutation-of-shared-list correct first try: `backup = scores; scores.append(40); scores = [1,2]` → backup is `[10,20,30,40]`. Learner distinguished mutation (both names see it) from rebinding (only one name).
- MISS (rated Again, recovered): return-exit location. On `for n in nums: if n==4: return n`, learner answered `2` (counting the 4s) instead of `4` (the value returned). Wrong assumption: that `return n` returns a match-count rather than the value of `n`. Re-drill on early `return` inside a loop was correct first try; concept rated Good after.
- MISS (rated Again twice, then resolved): container truthiness. First answer wrong on counting truthy in `[0,"",[],5,None,"hi"]` (guessed 5, answer 2). Re-drill counted `[0]` as falsy (said 3,4; answer 4,3). Root confusion: believed truthiness of a container depended on its contents. Tutor taught container rule directly (non-empty container is truthy regardless of contents; falsy set is `[]`,`""`,`0`,`None`). Third drill correct in mechanism; learner wrote `[None]` meaning `[0]` (keyboard limitation, no zero glyph available) — clarified, mechanism confirmed. Concept rated Good.
- Name binding correct first try: `x=[1,2,3]; y=x; x.append(99)` → y is `[1,2,3,99]` (mutation through shared reference).
- if/elif/else + short-circuit correct first try on both classify(-5/0/7) and `dict.get() or "guest"`.
- String accumulation by reassignment (`total = total + letters[i]` from `""`): learner did not commit an answer, asked to understand the mechanism. Explained `=`-is-rebind vs in-place mutation; strings immutable, `+` builds a new string. The trap was `""` visually resembling a fillable container like `[]`; rule offered: `=` means rebind, only `.append()`-style calls mutate. Not logged to FSRS (no committed answer).
- Reviews logged to FSRS in real time for every committed answer.

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
