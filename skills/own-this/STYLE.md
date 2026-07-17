# The study-guide style contract

The guide teaches ownership, not completeness. Every section exists to answer a
question a reviewer or interviewer would actually ask.

## Section order (fixed)

1. **Context, with an analogy.** What the system is and why the subject matters.
   Pick ONE everyday analogy (library catalog, thermostat, postal service…) and
   carry it through the whole document — never mix analogies. State the single
   load-bearing fact the entire solution depends on in a highlighted box (e.g.
   "the index is derived data — the files are the truth"). Tell how the problem
   arises as a NUMBERED STORY (steps a user actually lived), not as an abstract
   description.

2. **The concept in one idea.** The fix/design in ONE sentence inside a green
   box. Then "why that's right" as a short bullet list (newer wins / it's
   derived / it follows precedent…). Then the key distinction the design rests
   on as a small 2–3 row table (e.g. divergence vs structural failure; what we
   do for each).

3. **The twist.** The hardest subtlety, told as a story: the naive version, a
   red "why that's poisonous" box showing the concrete bad outcome, then a green
   "the rule" box with the repair. If a reviewer caught a flaw, credit that
   honestly — it makes the story stronger, not weaker.

4. **Reading the actual code.** 3–5 blocks of the FINAL shipped code (never
   pseudocode), each block followed by a **"Plain English:"** one-liner
   translating it. Annotate inside the code with short comments pointing at the
   load-bearing lines ("← this WHERE clause is the section-3 repair"). Explain
   ordering constraints (why X must happen before Y). Narrate tests as
   arrange / act / assert, and mention the evidence trick if used (test fails on
   unpatched code with the exact production error).

5. **Mini-glossary.** Collapsible `<details>` entries. ONLY terms actually used
   above. 1–2 sentences each, in plain words ("'Insert this row; if one with the
   same key exists, silently skip it'").

6. **The 30-second version.** A single quoted paragraph the user can speak
   verbatim when asked "tell me about this work". Problem → policy → subtlety →
   proof, in that order.

7. **Status footer** (optional): current state of the PR/work in one line.

## Simplicity rules (the default register)

- Short sentences. One idea per paragraph.
- Analogy over jargon; jargon only when the glossary defines it.
- Every code block earns its "Plain English:" line — no exceptions.
- Numbered stories over diagrams; tables over prose for comparisons.
- Cut anything that doesn't change what the reader would say or do.
- If a section can't be explained simply, the understanding isn't done yet —
  go back to the code, don't hide behind vocabulary.

## Visual vocabulary (classes exist in template.html)

- `.box.good` (green) — the rule / the fix / the safe fact.
- `.box.bad` (red) — the failure mode / why it's poisonous.
- `.box` (blue) — neutral emphasis (the load-bearing fact, status).
- Tables for any either/or comparison.
- `<details class="qa">` for glossary and Q&A entries.
- Code coloring spans: `.k` keyword, `.s` string, `.c` comment, `.f` function.
