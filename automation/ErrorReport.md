# Source discrepancies

The source remains unchanged. Discrepancies and their resolutions are recorded below.

## 2026-10-09T03:18:14.0759945-04:00

Equivalent proof route for lem:absolute, line 390: retain the source's one-coordinate and opposite two-coordinate perturbations, but use Mathlib's Krein–Milman theorem and closedness of a finite convex hull instead of writing the finite recursive decomposition explicitly. The statement is generalized to any finite number of coordinates and any natural-number sum cap; the source is the case four and two. Resolution 2026-10-09T03:19:36.5033979-04:00: Auto.reciprocalExponentPolytope_eq_convexHull passes the full build and standard-axiom audit.

## 2026-10-09T02:37:08.7719375-04:00

Blueprint lem:lattice-box, lines 329–342: the planned equivalent proof uses the uniform reduced-basis estimate `‖b_i‖ |n_i| ≤ 8^d ‖v‖`. Choose the printed floored side lengths for every basis vector and retain exactly those with positive length. The small-radius numerical bound then directly forces every other integer coordinate to vanish. This avoids the auxiliary Gram–Schmidt cutoff and its projection argument while preserving the requested part of a lattice basis, radius, box bound, and partial-sum assertion. This route is in progress. Euclidean balls here are formalized as closed balls, consistent with the source's compact unit ball and its explicit “norm at most” and `≤ 1/4` statements.

Resolution 2026-10-09T02:46:06.8602077-04:00: the complete full-lattice coefficient-box theorem, its exact radius, every partial coordinate sum, and the empty-box identity pass the full build and standard-axiom audit.

## 2026-10-09T02:28:44.5547395-04:00

Blueprint lem:transference, line 307: the Euclidean upper-bound proof uses the coarser but sufficient radius estimates `2^d a_j` for the primal prefix and `8^d/a_j` for the dual suffix. Their product is exactly the printed `16^d`. Both follow from the fully proved reduced-basis estimates; the full-lattice Euclidean transference theorem passes the full build and standard-axiom audit. No hypothesis or final constant changes.

## 2026-10-09T01:59:33.1650998-04:00

Blueprint lem:integer-basis, lines 257–263: primitive-vector extension and saturated subgroup bases use the equivalent splitting of free modules over the PID of integers. Blueprint lem:reduced-basis, lines 287–292: forward substitution and a geometric prefix estimate prove the inverse triangular coefficient bound; the dual norm estimate then uses the coordinate functional and Riesz duality, with an ℓ1 bound instead of the printed sum-of-squares argument. The exact stated constants and the assembled reduced-basis theorem pass the full build and standard-axiom audit.

## 2026-10-09T01:49:45.1986603-04:00

Blueprint lem:reduced-basis, lines 287–290: inverse upper triangular entries are represented by coordinates of the Gram–Schmidt vectors in the original basis. Forward substitution and a geometric prefix-sum induction replace the printed path-count/binomial expansion and prove the identical bound `1/2 * (3/2)^(j-i-1)`. The full build and standard-axiom audit pass. The dual norm bound is still in progress.

## 2026-10-09T01:00:16.2290272-04:00

Blueprint lem:integer-basis, lines 257–263: the primitive-vector proof uses the coordinate unit ideal to obtain a linear functional taking value one, then splits off its kernel over the PID of integers. This replaces the printed sequence of Bezout matrices and proves the same basis-extension statement. The full build and standard-axiom audit pass. The saturated-subgroup proof is proceeding via a torsion-free free quotient and its splitting; that part remains in progress.

Resolution 2026-10-09T01:03:57.7910860-04:00: the saturated-subgroup assertion is proved via a split free quotient and a product basis, reindexed so that the subgroup occupies the initial coordinates. Both the adapted-basis statement and quotient freeness pass the full build and standard-axiom audit. This replaces the source's dimension induction without changing its conclusion.

## 2026-10-08T22:03:12.7915330-04:00

Blueprint lem:gevrey, line 114: the implementation uses a factorial coefficient majorant and the exponential-series monomial bound instead of the sharper coefficient sum and exact maximization in the printed proof. This yields explicit Gevrey order four for expNegInvGlue, preserving the lemma's requirement of some fixed order. Its recurrence, degree bound, coefficient bound, and global derivative bound have passed direct Lean checking; full build and axiom audit are next. The original source is unchanged.

Resolution 2026-10-08T22:24:10-04:00: the complete cutoff construction, partition identity, local finiteness, rescaling identity, and mixed product derivative bounds pass `lake build` and use only the standard three axioms. The partition is expressed as a difference of two cumulative bump integrals, equivalently the convolution in the printed proof; its translate identity is proved by telescoping.

## 2026-10-08T22:24:10-04:00

Blueprint lem:fourier-foundation, line 134: the shell `T ≤ 1 + ‖n‖ < 2T` includes `n = 0` when `T = 1`, whereas the preceding derivative estimate explicitly excludes zero. For a nonzero constant function and positive derivative order, `A_m = 0`, so the printed shell bound fails. The high-frequency argument applies to nonzero modes; the constant mode must be accounted for separately using a zeroth-order bound. This is a low-frequency omission, with no proposed change to the main theorem. The formal shell and convergence obligations remain open.

Resolution 2026-10-08T22:44:53-04:00: `frequencyShell` explicitly excludes zero and `frequencyTruncationSet` always retains zero. The nonzero shell estimate, absolute convergence, uniform Fourier reconstruction, and uniform truncation error pass the full build and standard-axiom audit. The printed shell estimate including zero remains false; only this explicit low-frequency correction is adopted, with no change to the main theorem.

## 2026-10-08T23:05:08-04:00

Equivalent proof of lem:fourier-foundation, lines 148–152: the Gram envelope is `(1 + u²)⁻¹`, and its separated row sum is bounded by packing disjoint half-spacing intervals toward the row center. Integrating that envelope gives `1 + 2π/(rδ)`, hence the same absolute `C(r + δ⁻¹)` bound as the source's ordered-frequency argument. The actual interval estimate and multiplier consequence pass build and axiom audit. No statement is weakened.

## 2026-10-09T03:53:42.8404363-04:00

Source-fidelity audit for line 67 and lem:vector-maximal: the source explicitly uses the uncentered maximal operator, while the existing Auto.maximalQ and Auto.oneMixedNorm specialize the proved centered maximal theorem. The centered result remains valid, but does not by itself close the named source item. Add the standard pointwise domination of the uncentered operator by twice the centered operator and repair the source-facing specialization before using it for lem:finite-CN. No main theorem statement changes; this is a correction to an incomplete translation. Resolution 2026-10-09T04:05:46.4062726-04:00: maximalQ and oneMixedNorm now use the uncentered operator; the centered statements are preserved under explicit centered names. The factor-two comparison, full build and standard-axiom audit pass.

## 2026-10-09T03:52:31.5611636-04:00

Equivalent treatment of zero and infinite norms in lem:absolute, line 392: positive interpolation is performed directly in the extended nonnegative reals. Single-slot endpoint bounds imply null-set preservation, allowing essential-supremum bounds to be pulled back. This replaces the printed truncation argument without restricting the exponent range or assuming finite nonzero norms. Auto.positivePairwise_eLpNorm_bound passes the full build and standard-axiom audit; the final three geometric specializations and complex local-form bound passed the full build and standard-axiom audits at 2026-10-09T03:55:09.8722956-04:00.
## 2026-10-09T07:59:32.7934472-04:00

Equivalent proof organization for lem:prefix, lines 529–534: product differences are telescoped in the finite row Hilbert norm. The triangle inequality after each Bessel/prefix estimate gives the stronger sum-of-powers bound, then the source's exact m-squared L_T^(2(m-1)) constant. This reorganizes the printed pointwise Cauchy–Schwarz step without a commutation assumption or statement change. nestedProjectionProduct_successive_jumps passes the full build and standard-axiom audit.

## 2026-10-09T13:37:25.5127427-04:00

Equivalent derivative representation for def:chart, lines 632-635: coordinateWordDerivative indexes mixed derivatives by ordered coordinate words rather than exponent multi-indices. For the required C-infinity cutoff, mixed partials commute, and word length equals total derivative order; quantifying over all words therefore expresses the same source bound. The zeroth-order identity and exact complexity fields are checked. No analyticity or real-phase size restriction is imposed.

## 2026-10-09T17:33:29.322435-04:00

Equivalent proof organization for lem:local-frequency, line 887: instead of counting representatives of each finite cyclic image, choose a multiple of a nonzero circle element with norm at least one quarter. The strict one-eighth test set is disjoint from its translate by this multiple, so its cardinality is at most half the ambient group. The exact source statement is unchanged, and the full build and standard-axiom audit pass. The subsequent independent-test existence argument will be expressed by repeated finite-counting halving.
