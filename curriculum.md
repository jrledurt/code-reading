# The Reading Ladder

Ten stages. Each adds a kind of thing that has to be held in your head at once.
You move up when you hit the exit criteria on code you have not seen before, on
the first attempt.

Exit criteria are deliberately measurable. "Feels comfortable" is not an exit
criterion — comfort arrives well before competence and is the main way people
stall.

---

## Stage 1 — One function, no I/O

Local variables, loops, conditionals, a return. 10–25 lines. Nothing outside the
function.

Learning: holding variable state across iterations. Reassignment vs. mutation.
Where a function actually exits.

Drills: trace prediction, scrambled lines.

**Exit:** Predict exact output on 4 of 5 unseen functions, first try. Correctly
answer whether a list passed in was modified.

---

## Stage 2 — Data shape

Nested structures. Dict of lists, list of dicts, sets, tuples. Code that builds a
structure up across a loop.

Learning: predicting the *shape* of data, not just values. Most of understanding
a program is knowing what's in the containers.

Drills: trace prediction on structure state, decompression.

**Exit:** Draw the exact structure a function returns before running it, 4 of 5.
Convert a comprehension to a loop and back without help.

---

## Stage 3 — Multiple functions

Helpers, call stack, arguments and returns crossing boundaries. Exceptions raised
in one place and caught in another.

Learning: control leaving and returning. Where an exception lands and what state
you're in when it does.

Drills: trace prediction across calls, deletion test, why-this-not-that on why a
helper was extracted.

**Exit:** Given a raise deep in a call chain, say exactly which handler catches
it and what's been left half-done.

---

## Stage 4 — One complete program

A single file that does a real job. Entry point, argument parsing, reading a
file, writing output, handling failure. 100–200 lines.

Learning: orienting. Finding the entry point and following one path instead of
reading top to bottom.

Drills: bug injection, deletion test, explain-back of the whole flow.

**Exit:** Given an unfamiliar single-file program, describe what it does in five
sentences after two minutes — without reading every line.

---

## Stage 5 — Split into modules

The same program broken across files. Imports, namespaces, what's public and
what's internal.

Learning: why the split exists. Which module owns which responsibility, and what
would go wrong if you moved a function.

Drills: why-this-not-that on the boundaries, "where does this function live and
why."

**Exit:** Given a new function's purpose, say correctly which module it belongs
in and justify it.

---

## Stage 6 — Unknown dependencies

Code calling libraries you've never used.

Learning: reading by contract. You do not need to know what a library does
internally — you infer what it returns from how the result is used three lines
later. Highest-leverage reading skill there is, and it never stops paying.

Drills: contract reading, trace prediction where a library call is a black box.

**Exit:** Read code using an unfamiliar library and state what each call returns,
verified against the docs afterward, 4 of 5.

---

## Stage 7 — State that outlives the program

SQLite, then SQL through a layer. Where data goes when the process exits, and how
rows map to objects in code.

Learning: the schema is a second program running alongside the first. Reading one
without the other gets you nowhere.

Drills: given a schema and a query, predict the rows. Given code, predict what
lands in the table.

**Exit:** Reconstruct the table schema from reading application code alone.

---

## Stage 8 — Request lifecycle

A web backend. Route, handler, validation, database, serialization, response.
This is where "how the tools fit together" becomes concrete.

Learning: following one request end to end, and being able to say what runs, in
what order, on whose machine.

Drills: full-path trace prediction, deletion test on middleware, "where would you
put a log line to catch X."

**Exit:** Given an endpoint and a sample request, list every function that
executes in order, and name which ones touch the network or disk.

---

## Stage 9 — Things that don't run in source order

`async`/`await`, background tasks, callbacks. Code where reading top to bottom
gives you the wrong answer.

Learning: identifying suspension points, and what state can change while you're
awaiting.

Drills: ordering prediction, "what can change between these two lines."

**Exit:** Correctly order the output of an async program with three concurrent
tasks.

---

## Stage 10 — Unfamiliar repository

A real open-source project you've never seen. 50+ files.

Learning: strategic ignoring. Finding the entry point, following one path to the
end, and deliberately not reading 90% of the code. This is the terminal skill —
it's what "can read code" actually means in practice.

Drills: given a feature, find where it's implemented in under ten minutes. Given
a bug report, name the file it's probably in before looking.

**Exit:** Trace one complete feature through an unfamiliar repo and explain it,
including the wrong turns, in under thirty minutes.

---

## Pacing

No calendar deadlines — they push you to move up before the exit criteria are
met, which is the one failure that compounds. Stages 1–3 go fast. Stage 6 and
Stage 8 are where the real time goes. Sitting in each of those for a while is
correct, not slow.
