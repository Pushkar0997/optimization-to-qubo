# Part I Synthesis: How the Chapters Connect

*Covers 1.1–1.2 so far. Extend this once 1.3 lands.*

**1.1 → 1.2, directly.** 1.1 ends by defining convexity through the chord test — a purely geometric, visual check. 1.2 doesn't introduce a new idea here so much as give the *same* idea a precise, computable form: the Hessian's eigenvalues. "Does every chord stay on or below the curve" and "is the Hessian positive semi-definite everywhere" are the same fact, one visual and one you can actually run on a function with more than two variables (where drawing chords stops being practical).

**The critical-points thread.** 1.1's cell 5 finds a function's local minima by solving $g'(x)=0$ and checking $g''(x)$'s sign — done by hand, one variable at a time, using `numpy.roots` on a polynomial. 1.2 doesn't repeat this exercise (see the notebook's own note about that); instead it generalizes it: the same "solve derivative = 0, check second-derivative sign" logic becomes "solve $\nabla f(x)=0$, check the Hessian's eigenvalue signs" for functions of several variables. The one-variable version was never wrong, just a special case.

**Where this leaves 1.3.** Newton's method (1.3) uses the Hessian for something new: not just classifying a critical point after the fact, but using curvature *during* the search itself to jump straight toward the minimum, rather than crawling there gradient-descent-style. That's the throughline for this whole Part — vocabulary (1.1) → the tool that searches using only slope (1.2) → the tool that searches using slope *and* curvature (1.3).

**Where this feeds forward, briefly.** The convexity idea from 1.1–1.2 resurfaces properly in Part IV, once there's a genuine multi-variable quadratic objective to test it on. See [docs/THREADS.md](../docs/THREADS.md) for that and the other cross-Part connections.
