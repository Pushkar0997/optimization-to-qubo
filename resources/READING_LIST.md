# Reading List

Every external reading referenced in [CURRICULUM.md](../CURRICULUM.md), consolidated here. Two tiers, kept deliberately distinct:

- **Complementary** — specific, tied to one exact chapter, best read around that point in the sequence.
- **Supplementary** — broader, tied to a whole Part, not sequence-bound — good commute or "whenever" reading.

## Core references (used throughout)

- **Andrew Lucas (2014), ["Ising formulations of many NP problems"](https://arxiv.org/abs/1302.5843)** — arXiv, free. Short and conceptual; the master reference for turning classic combinatorial problems into QUBO/Ising form. Referenced repeatedly in Part III and Part V.
- **Boyd & Vandenberghe, [*Convex Optimization*](https://stanford.edu/~boyd/cvxbook/)** — the field's standard textbook, hosted free by the authors. Referenced in Parts I and IV.
- **MIT OpenCourseWare, [15.093J / 6.255J — Optimization Methods](https://ocw.mit.edu/courses/15-093j-optimization-methods-fall-2009/)** (Dimitris Bertsimas) — free lecture notes covering nearly this entire curriculum, in a different order. Referenced across Parts I, II, III, and IV.
- **Google [OR-Tools documentation](https://developers.google.com/optimization)** — open-source LP/MIP/CP-SAT/routing suite used from Part II onward.
- **D-Wave [Ocean SDK documentation](https://docs.dwavequantum.com/en/latest/)** — `dimod` and `dwave.samplers` reference, used in Part V.

## Part I — Foundations & Continuous Optimization

**Supplementary:** *Algorithms to Live By* — Brian Christian & Tom Griffiths. Pop-science; optimization ideas (optimal stopping, explore/exploit) through everyday decisions. No math required.

**Complementary, by chapter:**
- 1.1 — Boyd & Vandenberghe, Ch. 2–3 (Convex sets, Convex functions) — skim for the pictures, not the proofs yet.
- 1.2 — MIT OCW 15.093, Lecture 18 ("Optimality conditions and gradient methods"); Boyd & Vandenberghe Ch. 9 — the descent/gradient sections.
- 1.3 — MIT OCW 15.093, Lecture 19 ("Line searches and Newton's method"); Boyd & Vandenberghe Ch. 9 — the Newton's-method section.

## Part II — Linear & Integer Programming

**Supplementary:** Hamdy Taha, *Operations Research: An Introduction* — a gentler, more applied second explanation of anything in this Part.

**Complementary, by chapter:**
- 2.1 — MIT OCW 15.093, Lectures 1–2 ("Applications of linear optimization," "Geometry of linear optimization").
- 2.2 — MIT OCW 15.093, Lectures 3–4 ("Simplex method").
- 2.3 — MIT OCW 15.093, Lectures 12–13 ("Applications of discrete optimization," "Branch and bound and cutting planes").
- 2.4 — Google OR-Tools documentation, MIP and CP-SAT sections.

## Part III — Combinatorial Optimization & Metaheuristics

**Supplementary:** *In Pursuit of the Traveling Salesman* — William J. Cook. A genuinely fun narrative history of the TSP and combinatorial optimization, zero equations.

**Complementary, by chapter:**
- 3.1 — Lucas (2014), introduction/motivation section.
- 3.2 — MIT OCW 15.093, Lecture 15 ("Heuristics and approximation algorithms").

## Part IV — Quadratic Optimization & The Bridge to QUBO

**Supplementary:** Boyd & Vandenberghe, Ch. 1–5 (the full theory of convexity and duality) — a good point to read the fuller theoretical picture, now that these ideas have shown up practically a few times.

**Complementary, by chapter:**
- 4.1 — Boyd & Vandenberghe, Ch. 4 (Convex optimization problems — quadratic program section).
- 4.2 — MIT OCW 15.093, Lecture 14 ("Lagrangean methods" — the theoretical cousin of penalty methods).

## Part V — QUBO: Formulation & Solving

**Supplementary:** D-Wave's Ocean SDK documentation and blog — browse once you're here, not before; it won't make much sense in isolation.

**Complementary, by chapter:**
- 5.1 — Lucas (2014), introduction and Ising–QUBO equivalence section.
- 5.2 — Lucas (2014), Max-Cut / Number Partitioning / Knapsack sections (find by name — section numbers vary slightly across versions of the paper).
- 5.3 — D-Wave Ocean SDK docs, `dimod` and `dwave.samplers` reference pages.
