# Optimization → QUBO: Master Curriculum Index

*A book-style index for the full learning arc — foundations of optimization through to an industry-grade QUBO capstone. Every notebook maps to an entry here. See [docs/SPEC.md](docs/SPEC.md) for the learning objectives this index is built to satisfy, and [docs/ROADMAP.md](docs/ROADMAP.md) for live build status.*

---

## How to read this index

| Symbol | Meaning |
|---|---|
| 🎯 | Why this Part matters for the QUBO end-goal (the thread) |
| 🔗 | Where to read how this Part's chapters connect to each other |
| 💻 | Code demonstrated and executed in the notebook |
| 📓 | The notebook this chapter lives in |
| ✍️ | Homework — small, single-concept exercise, with solution |
| 🔨 | Mini-project — integrates the whole Part, done at the Part's end |
| 📎 | **Complementary reading** — specific, tied to this exact chapter, read around this point |
| 📚 | **Supplementary reading** — broader, tied to the whole Part, read anytime (commute-friendly, not sequence-bound) |
| ⭐ CORE | Required for the shortest path to QUBO + capstone |
| ➕ STRETCH | Adds depth/breadth, skippable if short on time |

**Notebooks**: each chapter gets its own standalone notebook, named after its exact chapter number (`N.M_topic.ipynb`) — deep, self-contained, independently readable. Two layers carry the connections between them: each Part's `SYNTHESIS.md` narrates how that Part's own chapters build on one another, and the Part's mini-project notebook (`N_mini_project.ipynb`) is the hands-on version of that same synthesis — one problem that genuinely needs every chapter in the Part. The longer-range threads that span *multiple* Parts (Part I's convexity becoming Part IV's quadratic programs, Part III's simulated annealing becoming Part V's QUBO solver) live in [docs/THREADS.md](docs/THREADS.md), updated as each connection actually gets built.

*Exception:* `01-foundations/01_foundations.ipynb` (Chapters 1.1–1.2) predates this convention and stays as one cumulative file — not worth restructuring after the fact. Chapter 1.3 onward follows the standalone-notebook convention. The capstone (Part VI) is also intentionally one file — its five stages are steps of a single project, not separate lessons, so splitting them apart would work against the point.

**Pace, honestly**: 14 CORE concept-chapters + 1 STRETCH + a 5-session capstone = 19–20 total sessions. At 5–10 hrs/week (roughly 2–3 sessions), that's **~7–8 weeks** for a learner working through this solo — plan accordingly rather than assuming a strict four. Skip 3.3 (STRETCH) anytime to shorten the path without breaking the sequence.

**Capstone domain**: logistics / supply-chain optimization by default, finance woven through as a secondary thread. Final call locked in at the start of Part VI — Part V's mini-project is a natural pivot point if the finance thread pulls harder.

---

## PART I — Foundations & Continuous Optimization
🎯 Builds the vocabulary of "search for the best x," and the smooth, calculus-based way to do it — the frame everything else sits inside.

🔗 `01-foundations/SYNTHESIS.md`

📚 *Algorithms to Live By* (Christian & Griffiths) — optimization ideas in plain language, best read early, anytime during this Part.

### 1.1 — What Is Optimization? ⭐ CORE
Decision variables, objective functions, constraints, and the vocabulary that makes "best" precise.
- Topics: feasible region · local vs. global optima · maxima vs. minima · convex vs. non-convex sets/functions · why convexity matters
- 💻 Plotting 1D/2D functions, visually spotting minima/maxima, convex vs. non-convex examples
- 📓 `01-foundations/01_foundations.ipynb` (Section 1)
- ✍️ Homework: classify 6 given functions/plots as convex or not, explain why
- 📎 Boyd & Vandenberghe, Ch. 2–3 (Convex sets, Convex functions) — skim for the pictures, not the proofs yet

### 1.2 — Calculus Refresher & Gradient Descent From Scratch ⭐ CORE
The derivative-based way to search: derive gradient descent, then build it in numpy.
- Topics: derivatives · partial derivatives · gradient vector · Hessian · first/second-order conditions · GD update rule · batch vs. stochastic vs. mini-batch · learning rate & momentum
- 💻 `sympy` for symbolic derivatives, hand-derive the GD update rule, implement from scratch, plot descent path on a contour map
- 📓 `01-foundations/01_foundations.ipynb` (Section 2)
- ✍️ Homework: (a) run GD on a new function and explain a divergence case (b) fit a line via GD from scratch
- 📎 MIT OCW 15.093, Lecture 18 — "Optimality conditions and gradient methods"; Boyd & Vandenberghe Ch. 9 (Unconstrained minimization) — the descent/gradient sections

### 1.3 — Newton's Method, `scipy.optimize`, and a First Look at Constraints ⭐ CORE
The faster, curvature-aware alternative to GD; the solver you'd actually use; constraints previewed for Part II.
- Topics: Newton's method · quasi-Newton/BFGS intuition · `scipy.optimize.minimize` · Lagrange multipliers (conceptual) · KKT conditions (conceptual)
- 💻 Newton's method from scratch, benchmark vs. GD vs. `scipy.optimize`, a first Lagrange-multiplier toy example by hand
- 📓 `01-foundations/1.3_newtons_method_scipy_constraints.ipynb` — first notebook under the new convention
- ✍️ Homework: solve one constrained toy problem two ways — by hand (Lagrange) and via `scipy.optimize`
- 📎 MIT OCW 15.093, Lecture 19 — "Line searches and Newton's method"; Boyd & Vandenberghe Ch. 9 — the Newton's-method section

🔨 **Part I Mini-Project**: Calibrate a small nonlinear model (e.g., a sensor-response curve) using GD, Newton, and `scipy.optimize` side by side — compare convergence speed and stability.
- 📓 `01-foundations/1_mini_project.ipynb`

---

## PART II — Linear & Integer Programming
🎯 Introduces two ingredients QUBO can't live without — hard constraints and binary/integer variables — still solved the "classical OR" way, separately from the objective.

🔗 `02-linear-integer-programming/SYNTHESIS.md`

📚 Hamdy Taha, *Operations Research: An Introduction* — the LP/IP chapters, as a gentler second explanation of anything below, anytime.

### 2.1 — Linear Programming: Formulation & Geometry ⭐ CORE
What an LP looks like, and why solutions live at the corners of the feasible region.
- Topics: standard form · feasible region as a polytope · vertices & why optima sit there · 2D geometric intuition
- 💻 Plot a 2D feasible region, visually locate the optimum
- 📓 `02-linear-integer-programming/2.1_lp_formulation_geometry.ipynb`
- ✍️ Homework: formulate a resource-allocation word problem as an LP by hand
- 📎 MIT OCW 15.093, Lectures 1–2 — "Applications of linear optimization," "Geometry of linear optimization"

### 2.2 — Solving LPs: Simplex Intuition + Python Solvers ⭐ CORE
What a solver is actually doing, then using one properly.
- Topics: simplex method (high-level walkthrough, not full proof) · `scipy.optimize.linprog` · `PuLP` syntax · diet/blending/transportation problems
- 💻 Diet problem solved via `linprog` and `PuLP`, side by side
- 📓 `02-linear-integer-programming/2.2_simplex_python_solvers.ipynb`
- ✍️ Homework: solve a blending/production-mix problem in `PuLP`
- 📎 MIT OCW 15.093, Lectures 3–4 — "Simplex method"

### 2.3 — Integer & Mixed-Integer Programming ⭐ CORE
Why integrality changes everything, and how solvers cope.
- Topics: LP relaxation · NP-hardness (first honest look) · branch and bound (small worked example) · MIP in `PuLP`/OR-Tools
- 💻 Trace branch-and-bound by hand on a tiny example, then solve via `PuLP`
- 📓 `02-linear-integer-programming/2.3_integer_mixed_integer_programming.ipynb`
- ✍️ Homework: solve a small scheduling/assignment MIP
- 📎 MIT OCW 15.093, Lectures 12–13 — "Applications of discrete optimization," "Branch and bound and cutting planes"

### 2.4 — Binary Variables: Knapsack & Assignment ⭐ CORE
Binary decisions and combinatorial structure — the direct setup for QUBO's binary variables.
- Topics: 0/1 knapsack formulation · assignment problem · binary variables as "yes/no" decisions
- 💻 0/1 knapsack solved via `PuLP` and OR-Tools CP-SAT, compared
- 📓 `02-linear-integer-programming/2.4_binary_knapsack_assignment.ipynb`
- ✍️ Homework: formulate and solve a facility-location or assignment problem
- 📎 Google OR-Tools documentation — MIP and CP-SAT sections

🔨 **Part II Mini-Project**: Workforce or delivery-truck assignment problem — formulate, solve, and write a short justification of the optimal plan (practice for presenting this to a manager).
- 📓 `02-linear-integer-programming/2_mini_project.ipynb`

---

## PART III — Combinatorial Optimization & Metaheuristics
🎯 What we reach for once exact methods explode — specifically, the heuristic (simulated annealing) that QUBO solvers actually run underneath.

🔗 `03-combinatorial-metaheuristics/SYNTHESIS.md`

📚 *In Pursuit of the Traveling Salesman* (William J. Cook) — narrative history of TSP and combinatorial optimization, zero equations, anytime.

### 3.1 — NP-Hardness, Concretely ⭐ CORE
Why brute force dies past ~20 items, using problems we'll reuse for QUBO.
- Topics: TSP · graph coloring · Max-Cut · combinatorial explosion, made visceral with a runtime plot
- 💻 Brute-force TSP for n = 5..12, plot the runtime explosion
- 📓 `03-combinatorial-metaheuristics/3.1_np_hardness.ipynb`
- ✍️ Homework: estimate brute-force runtime for a 20-city TSP, explain why it's infeasible
- 📎 Lucas (2014) — introduction/motivation section, on why these problems need heuristic or QUBO treatment

### 3.2 — Simulated Annealing From Scratch ⭐ CORE
The workhorse heuristic — derive and build it, solving a real combinatorial problem.
- Topics: local search · temperature schedules · acceptance probability · explore vs. exploit · cooling schedules
- 💻 SA built from scratch on TSP or graph coloring, cost-over-time plotted
- 📓 `03-combinatorial-metaheuristics/3.2_simulated_annealing.ipynb`
- ✍️ Homework: tune the cooling schedule, compare 3 schedules on solution quality
- 📎 MIT OCW 15.093, Lecture 15 — "Heuristics and approximation algorithms"

### 3.3 — Genetic Algorithms & Tabu Search ➕ STRETCH
Two more metaheuristics, lighter treatment — good breadth, not required for the QUBO path.
- Topics: genetic algorithms (selection/crossover/mutation) · tabu search (memory-based local search)
- 💻 A short GA or tabu-search implementation on the same instance as 3.2
- 📓 `03-combinatorial-metaheuristics/3.3_genetic_algorithms_tabu_search.ipynb` (optional)
- ✍️ Homework: compare GA/tabu vs. SA on solution quality and runtime

🔨 **Part III Mini-Project**: A small vehicle-routing problem (a handful of delivery stops), solved via simulated annealing — visualize the route before/after optimization.
- 📓 `03-combinatorial-metaheuristics/3_mini_project.ipynb`

---

## PART IV — Quadratic Optimization & The Bridge to QUBO
🎯 Deliberately the shortest Part — it exists only to hand over the two remaining QUBO ingredients: a quadratic objective, and the penalty trick that dissolves constraints into it.

🔗 `04-quadratic-penalty/SYNTHESIS.md`

📚 Boyd & Vandenberghe, Ch. 1–5 (the full theory of convexity and duality) — now that you've used these ideas practically a few times, this is a good point to read the fuller theoretical picture, anytime.

### 4.1 — Quadratic Forms & Quadratic Programming ⭐ CORE
What "quadratic" buys us, and the industry-classic example that uses it.
- Topics: quadratic form $x^TQx$ · positive semi-definiteness & convexity of quadratics · QP via `cvxpy` · Markowitz mean-variance portfolio optimization
- 💻 Markowitz portfolio optimization in `cvxpy` on a small basket of assets
- 📓 `04-quadratic-penalty/4.1_quadratic_programming.ipynb`
- ✍️ Homework: add a cardinality constraint (max k assets) to the portfolio problem, observe how a plain QP struggles with it
- 📎 Boyd & Vandenberghe, Ch. 4 (Convex optimization problems — quadratic program section)

### 4.2 — Penalty Methods: Dissolving Constraints ⭐ CORE
The single idea that makes QUBO possible: constraints become squared-penalty terms in the objective.
- Topics: penalty-method derivation · choosing penalty weights · "minimize f(x) s.t. g(x)=0" → "minimize f(x) + λ·g(x)²" · trade-offs of too-small vs. too-large λ
- 💻 Rewrite the Part II knapsack (constrained) as an unconstrained penalized quadratic, solve both ways, compare
- 📓 `04-quadratic-penalty/4.2_penalty_methods.ipynb`
- ✍️ Homework: pick a new constraint, derive its penalty term, tune λ until it's respected
- 📎 MIT OCW 15.093, Lecture 14 — "Lagrangean methods" (the theoretical cousin of penalty methods)

🔨 **Part IV Mini-Project**: Take the cardinality-constrained portfolio problem from 4.1 and solve it via the penalty method instead of a constraint-aware solver — this project *is* a QUBO in disguise, one step before we name it as one.
- 📓 `04-quadratic-penalty/4_mini_project.ipynb`

---

## PART V — QUBO: Formulation & Solving
🎯 Everything converges: binary (Part II) + quadratic (Part IV) + constraints-as-penalties (Part IV), solved by simulated annealing (Part III).

🔗 `05-qubo/SYNTHESIS.md`

📚 D-Wave's Ocean SDK documentation and blog — browse once we're here, not before (it won't make much sense in isolation).

### 5.1 — QUBO Defined, and the Ising Connection ⭐ CORE
The formal object, and why physics/quantum hardware cares about it.
- Topics: $\min_{x \in \{0,1\}^n} x^TQx$ · building a Q matrix by hand from a small example · Ising model equivalence (spins ±1 ↔ bits 0/1) · why this matters for quantum annealing
- 💻 Hand-build a 4-variable Q matrix from a toy problem, verify it by brute-force evaluation
- 📓 `05-qubo/5.1_qubo_defined_ising_connection.ipynb`
- ✍️ Homework: convert a given Ising Hamiltonian into QUBO form and vice versa
- 📎 Lucas (2014) — introduction and Ising–QUBO equivalence section

### 5.2 — Formulating Classic Problems as QUBO ⭐ CORE
Turning Part III's problems into Q matrices, using Part IV's penalty trick.
- Topics: Max-Cut (naturally quadratic) · number partitioning · 0/1 knapsack-as-QUBO (full penalty derivation) · graph coloring
- 💻 Build Q matrices for Max-Cut and knapsack, both by hand and with `qubovert`/`PyQUBO`
- 📓 `05-qubo/5.2_formulating_classic_problems_as_qubo.ipynb`
- ✍️ Homework: formulate graph coloring as QUBO from scratch
- 📎 Lucas (2014) — Max-Cut / Number Partitioning / Knapsack sections (find by name — section numbers vary slightly across versions)

### 5.3 — Solving QUBO & Benchmarking ⭐ CORE
Multiple solvers, compared honestly as problems grow.
- Topics: brute force (ground truth, small n) · simulated annealing via `dimod` + `dwave.samplers` · tabu search · runtime/quality trade-offs as n grows
- 💻 Solve the 5.2 QUBOs with brute force vs. SA vs. tabu, plot solution quality vs. problem size
- 📓 `05-qubo/5.3_solving_qubo_benchmarking.ipynb`
- ✍️ Homework: tune penalty coefficients until the SA solver stops returning infeasible solutions
- 📎 D-Wave Ocean SDK docs — `dimod` and `dwave.samplers` reference pages

🔨 **Part V Mini-Project**: A constrained scheduling or routing problem (5–8 tasks/stops), formulated and solved as QUBO end-to-end — a dry run for the capstone, at smaller scale.
- 📓 `05-qubo/5_mini_project.ipynb`

---

## PART VI — Capstone Project
🎯 An industry-grade, end-to-end QUBO pipeline: problem statement → formulation → implementation → benchmarking → writeup, scoped and delivered the way it would be in an OR/data-science role.

Domain: **logistics / supply-chain optimization** (vehicle routing or workforce/delivery scheduling) by default — genuinely fine to pivot to the finance thread instead if Part V's mini-project pulls you that way; the pipeline is identical either way.

One notebook by design (see the exception note at the top) — `06-capstone/6_capstone.ipynb`, gaining a section per stage below.

### 6.1 — Problem Scoping ⭐ CORE
Pick the exact sub-problem, define scale and success metric, survey how real companies frame it.
- 📓 Section 1 (problem statement)
- ✍️ Deliverable: one-page problem statement + success metric

### 6.2 — Mathematical Formulation & QUBO Construction ⭐ CORE
Turn the scoped problem into an explicit Q matrix, constraints folded in as penalties.
- 💻 Full formulation coded up, Q matrix built and validated on a tiny instance
- 📓 Section 2

### 6.3 — Implementation: The Solving Pipeline ⭐ CORE
Multiple solvers wired up, ready to compare.
- 💻 Brute force (small instance) + SA + tabu, all running on the same problem
- 📓 Section 3

### 6.4 — Benchmarking, Analysis & Visualization ⭐ CORE
Does it actually work, and how do you know?
- 💻 Solution-quality and runtime comparisons, visualized, at increasing problem size
- 📓 Section 4

### 6.5 — Writeup & Portfolio Packaging ⭐ CORE
Package it so it's actually pitchable — to your portfolio site, an internship application, or a recruiter.
- 📓 Section 5 (final polished notebook) + a short standalone README-style writeup
- ✍️ Deliverable: the finished capstone, ready to link from pushkarkumar.me

---

Live build status and the checklist view of every chapter above: [docs/ROADMAP.md](docs/ROADMAP.md). Cross-Part connections: [docs/THREADS.md](docs/THREADS.md).
