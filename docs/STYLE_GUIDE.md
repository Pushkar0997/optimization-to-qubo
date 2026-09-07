# Style Guide

Conventions every notebook and doc in this repo follows. The point is consistency — a learner working through Part IV should never have to re-learn how the material is organized.

## Notebook shape

Every notebook is one cumulative file per Part, with sections added chapter by chapter. Each chapter section follows the same pattern:

1. **Concept** — a markdown cell introducing the idea, always closing with a one- or two-line "why this matters for QUBO" thread-back to the end goal.
2. **Code** — one or more code cells making the concept concrete, always executed with real (not fabricated) outputs embedded.
3. **Exercise** — a markdown cell posing a small, single-concept problem.
4. **Solution** — a markdown cell with worked reasoning, followed by a code cell that verifies the reasoning computationally wherever possible (see "Verification ethos" below).

## Verification ethos

No claim in any notebook is asserted without being checked in code first. If a hand-derivation and a computed result disagree, the notebook is wrong until it's fixed — not the other way around. Concretely:

- Numeric claims ("the minimum is at x=3") are computed, never just stated.
- Classifications (convex/non-convex, feasible/infeasible) are verified against a direct computational test, not asserted from memory of the theory.
- If a cheap approximate method (e.g. a grid search) and an exact method (e.g. solving analytically) disagree, prefer the exact method and say so — don't quietly average them or hide the discrepancy.

## Code conventions

- Standard library and the smallest reasonable dependency set — no unnecessary abstraction.
- Comments explain *why*, not *what* (the code already says what; comments earn their place by adding reasoning, a gotcha, or a connection to the theory above).
- Functions over copy-pasted blocks once a pattern repeats twice.
- Loosely PEP8. Cell-level reproducibility matters more than strict linting.

## Markdown & math conventions

- Inline math: `$...$`. Display math: `$$...$$`.
- Headers in sentence case (`## Local vs. global optima`, not `## Local Vs Global Optima`).
- Bold for defined terms on first use (`**convex set**`), not for general emphasis.

## Naming

- Notebooks: `NN_topic.ipynb`, numbered to match the folder.
- Folders: `NN-topic-with-hyphens`, numbered to match [CURRICULUM.md](../CURRICULUM.md)'s Part ordering.

## Reading-list tiers

Every reading recommendation in [resources/READING_LIST.md](../resources/READING_LIST.md) is tagged one of two ways, and both tags are kept distinct on purpose:

- **Complementary** — specific, tied to one exact chapter, meant to be read around that point in the sequence.
- **Supplementary** — broader, tied to a whole Part, not sequence-bound, safe to read anytime (including well before or after the relevant Part).
