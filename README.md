# Optimization → QUBO

*A from-scratch, hands-on path from classical optimization to Quadratic Unconstrained Binary Optimization (QUBO) — the formulation behind quantum annealing and a growing set of classical combinatorial solvers.*

> 🚧 **Status: in progress.** Part I is live; Parts II–VI are actively being built. See [docs/ROADMAP.md](docs/ROADMAP.md) for exactly what's done.

## What this is

Six parts, each built directly on the last, going from "what is an optimization problem" to formulating and solving real combinatorial problems as QUBO — finishing with an original, benchmarked capstone project. Full chapter-by-chapter breakdown: [CURRICULUM.md](CURRICULUM.md).

No prior optimization background assumed. Comfort with basic Python (functions, `numpy`) is enough to start — the calculus and linear algebra needed are rebuilt from scratch, exactly where they're needed. See [docs/SPEC.md](docs/SPEC.md) for the full learning objectives and scope.

## Structure

| Part | Topic | Status |
|---|---|---|
| I | Foundations & Continuous Optimization | ✅ Chapter 1.1 live |
| II | Linear & Integer Programming | 🚧 planned |
| III | Combinatorial Optimization & Metaheuristics | 🚧 planned |
| IV | Quadratic Optimization & The Bridge to QUBO | 🚧 planned |
| V | QUBO: Formulation & Solving | 🚧 planned |
| VI | Capstone Project | 🚧 planned |

Each part is one cumulative Jupyter notebook: markdown explanations, runnable code with real (executed, not just described) outputs, and exercises with worked solutions.

## Getting started

```bash
git clone https://github.com/pushkar0997/optimization-to-qubo.git
cd optimization-to-qubo
pip install -r requirements.txt
jupyter notebook 01-foundations/01_foundations.ipynb
```

Or skip local setup entirely — every notebook has an "Open in Colab" badge at the top.

## Repo layout

```
optimization-to-qubo/
├── CURRICULUM.md          full book-style index of every chapter
├── docs/
│   ├── SPEC.md             learning objectives, audience, scope, acceptance criteria
│   ├── STYLE_GUIDE.md      conventions every notebook follows
│   └── ROADMAP.md          build status
├── 01-foundations/
├── 02-linear-integer-programming/
├── 03-combinatorial-metaheuristics/
├── 04-quadratic-penalty/
├── 05-qubo/
├── 06-capstone/
└── resources/
    └── READING_LIST.md    complementary + supplementary reading, by part
```

## Contributing

This is primarily a personal learning project built in public, so the roadmap is fixed, but corrections are genuinely welcome — if a proof is wrong, a plot is misleading, or code has a bug, please open an issue. See [docs/STYLE_GUIDE.md](docs/STYLE_GUIDE.md) for the conventions any change should follow.

## License

Code and content are MIT-licensed — see [LICENSE](LICENSE). Use it, fork it, teach with it.

## Acknowledgments

This curriculum leans on several open resources throughout, including MIT's *15.093J Optimization Methods*, Boyd & Vandenberghe's *Convex Optimization*, and Andrew Lucas's *"Ising formulations of many NP problems"* — full attribution in [resources/READING_LIST.md](resources/READING_LIST.md).
