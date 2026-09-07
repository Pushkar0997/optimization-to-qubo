# Project Spec

## What this is

A self-contained, from-scratch curriculum taking a learner from the basic vocabulary of optimization through to Quadratic Unconstrained Binary Optimization (QUBO) — the formulation used by quantum annealers and a growing set of classical heuristic solvers — culminating in an industry-grade capstone project.

## Who this is for

- Learners with some Python experience (comfortable writing functions, using `numpy`/`matplotlib`) but little to no background in optimization theory.
- No prior mastery of linear algebra or calculus is assumed — each is rebuilt from scratch, just-in-time, exactly where it's first needed.

## Learning objectives

By the end of this curriculum, a learner should be able to:

- Formulate a real-world decision problem as a formal optimization problem (decision variables, objective, constraints, feasible region).
- Implement gradient descent and Newton's method from scratch, and use `scipy.optimize` correctly — including the maximize/minimize sign-flip convention.
- Classify a function as convex, concave, or neither, and explain why convexity guarantees a local minimum is global.
- Formulate and solve linear and mixed-integer programs with `PuLP`/OR-Tools.
- Explain why combinatorial problems resist exact solving at scale, and implement simulated annealing from scratch.
- Explain quadratic programming and derive a penalty term that folds a constraint into an unconstrained objective.
- Formulate classic combinatorial problems (Max-Cut, 0/1 knapsack, graph coloring, number partitioning) as QUBO, and solve them with multiple solvers (brute force, simulated annealing, D-Wave's Ocean SDK).
- Scope, build, and benchmark an original QUBO-based project end-to-end, and communicate the results in writing.

## Scope / non-goals

- This curriculum focuses on QUBO and quantum *annealing*. It does not cover the gate-model / circuit-based quantum computing paradigm (Qiskit-style circuits, algorithms like Shor's or Grover's) — that's a different, only loosely related subfield.
- Proofs are motivated and sketched, not delivered with full mathematical rigor. The goal is working intuition and correct, executed code — not a pure-math treatment. Pointers to rigorous treatments (Boyd & Vandenberghe, MIT 15.093) are given throughout for anyone who wants to go deeper.
- Every plotted or printed claim in every notebook is verified computationally before being asserted — not just described in prose. Bugs get fixed, not hidden.

## Per-part acceptance criteria

One "you should now be able to..." checklist per Part. Full topic-by-topic breakdown lives in [CURRICULUM.md](../CURRICULUM.md).

- **Part I — Foundations & Continuous Optimization:** classify a function as convex/non-convex; implement gradient descent from scratch; use `scipy.optimize` correctly, including the sign-flip for maximization.
- **Part II — Linear & Integer Programming:** formulate an LP/MIP from a word problem and solve it with `PuLP`/OR-Tools; explain why integer constraints make a problem harder.
- **Part III — Combinatorial Optimization & Metaheuristics:** implement simulated annealing from scratch and explain how it escapes local minima that trap greedy search.
- **Part IV — Quadratic Optimization & The Bridge to QUBO:** solve a small quadratic program; derive a penalty term for a constraint and fold it into an unconstrained objective.
- **Part V — QUBO: Formulation & Solving:** build a QUBO matrix for a named combinatorial problem from scratch; solve it with at least two different solvers and compare results.
- **Part VI — Capstone:** ship an original, benchmarked, written-up QUBO project on a real-world-flavored problem.
