# Threads: Connections Across Parts

Within a Part, `SYNTHESIS.md` covers how its own chapters connect. This document is for the longer-range threads that span *multiple* Parts — the ones a reader would only notice if they'd read everything, which is exactly why they're worth writing down.

Each entry is only filled in with specifics once **both** ends of the thread actually exist as built content. Until then it's listed as planned, so this file never claims more than what's actually true yet.

---

### Convexity: Part I → Part IV
**Status:** planned (Part I built, Part IV not yet)
Chapter 1.1 introduces convexity via the chord test; 1.2 makes it precise via the Hessian. Part IV's quadratic programming (4.1) is where this pays off directly — quadratic forms are the cleanest possible case to check convexity on, and *why* Markowitz portfolio optimization is tractable comes straight from this.

### Local vs. global minima: Part I → Part III
**Status:** planned (Part I built, Part III not yet)
1.1's "blindfolded hiker" problem — local minima that aren't global — is exactly the failure mode Part III's simulated annealing (3.2) is built to escape. 1.2's gradient descent has no answer to this; 3.2 is the first tool in the curriculum that does.

### Binary variables: Part II → Part V
**Status:** planned (neither built yet)
2.4 introduces binary decision variables (0/1 knapsack, assignment). Part V's QUBO (5.1) uses exactly these same binary variables — the only new part is fusing them with a quadratic objective.

### Simulated annealing: Part III → Part V
**Status:** planned (neither built yet)
3.2 builds simulated annealing to solve combinatorial problems that resist exact methods. 5.3 is that exact same algorithm, applied to QUBO's matrix formulation instead of directly to the combinatorial structure — the solver doesn't change, only what it's solving.

### Quadratic forms + penalty methods: Part IV → Part V
**Status:** planned (neither built yet)
4.1's quadratic objective and 4.2's penalty-method trick are, combined, *literally* the QUBO formulation (5.1) — this is the single most direct thread in the whole curriculum. By the time Part V opens, QUBO should feel like a name for something already built, not a new topic.

---

*Update this file as each side of a thread lands — replace "planned" with the actual chapter numbers and a one-line note on how cleanly (or not) the connection worked out in practice.*
