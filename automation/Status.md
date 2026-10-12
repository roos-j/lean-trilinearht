# Main theorem overview

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
not started | 2026-10-11 13:53:48 ET | thm:main, lines 2934–2941 | Uniform L3 THT estimate: proved given prop:normalized (tht_main_of_uniform); prop:normalized open
complete | 2026-10-11 11:29:42 ET | thm:main, lines 2984–2992 | Pointwise principal value on Schwartz inputs (Auto.thtTruncated_tendsto)
complete | 2026-10-11 11:35:58 ET | thm:main, lines 2999–3009 | Unique bounded L3 extension given the bound (Auto.schwartz_L3_unique_extension)

# Quantitative quadratic chart calculus prerequisite

The locally quadratic chart lemma needs the substantial general calculus of compactly supported quadratic lattice-sum charts: finite summation, normalization, conjugation, products, affine changes and uniform Gevrey complexity. Pinned Mathlib has no matching quadratic chart theorem; its calculus and Fourier primitives underlie the already-proved general development. Extract that complete development into TrilinearHT/Auto/QuadraticCharts.lean under the reusable-prerequisite exception, not a machine-blueprint section split. Move the primitive logarithmic-size and quasipolynomial-bound definitions with it. Use a primitive local rational height definition, definitionally equal to the existing one, so every statement and local definition depends only on Mathlib and the same module. RationalLinearAlgebra may be imported for proof reuse only. A declaration-reference scan found no other external project dependencies. Verified source: def:chart, lines 625-637, lem:chart-operations, lines 642-660, and the several-variable chart formula. Recorded before creation at 2026-10-09 19:20:45 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 19:24:17 ET | def:chart and lem:chart-operations, lines 625-660 | Independent quantitative quadratic chart calculus

# Quantitative Gevrey cutoff prerequisite

The Fourier localization needs compact cutoffs and a locally finite integer partition with uniform all-orders Gevrey bounds. Pinned Mathlib supplies smooth expNegInvGlue and smooth transitions but no quantitative Gevrey derivative or partition theorem; the repository's already-proved construction supplies this substantial classical calculus prerequisite. Move that entire independent development, without duplicating or changing its proofs, into TrilinearHT/Auto/GevreyCutoffs.lean. Its general interval, affine-rescaling and finite-product statements use only Mathlib and local definitions. This is the reusable-prerequisite exception, not a machine-blueprint section split. Verified references: blueprint lem:gevrey, lines 107–126, and Mathlib.Analysis.SpecialFunctions.SmoothTransition. Recorded before module creation at 2026-10-09 09:58:48 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-08 22:14:53 ET | lem:gevrey, lines 110–114 | Quantitative derivative bounds for expNegInvGlue
complete | 2026-10-08 22:24:10 ET | lem:gevrey, lines 116–117 | Normalized compact bump and interval cutoffs
complete | 2026-10-08 22:24:10 ET | lem:gevrey, lines 117–125 | Locally finite partition of unity
complete | 2026-10-08 22:24:10 ET | lem:gevrey, line 126 | Rescaling and multidimensional products

# Quantitative Fourier approximation prerequisite

The chart development and later Fourier splitting use the general derivative-to-Fourier-decay, absolute convergence and quantitative uniform truncation theorem on finite-dimensional tori. Pinned Mathlib has Fourier completeness and summability interfaces, but searches found no matching explicit derivative-order, dimension and tail estimate. This is a substantial classical Fourier-analysis prerequisite. Move the entire already-proved 702-line independent development, without changing its mathematics, into TrilinearHT/Auto/FourierApproximation.lean. A declaration-reference scan found no external project dependencies; its statements and local definitions use only Mathlib. This invokes the reusable-prerequisite exception, not a source-section split. Verified references: blueprint lem:fourier-foundation, lines 130-146, and Mathlib.Analysis.Fourier.AddCircleMulti. Preserve the existing attribution to ../lean-dfr. Recorded before creation at 2026-10-09 13:27:14 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-08 22:44:53 ET | lem:fourier-foundation, lines 130–146 | Coordinate Fourier coefficient decay
complete | 2026-10-08 22:44:53 ET | lem:fourier-foundation, lines 134–146 | Nonzero shell counting, tails, and uniform convergence
complete | 2026-10-09 13:30:19 ET | lem:fourier-foundation, lines 130-146 | Independent Fourier approximation module verification
complete | 2026-10-10 11:41:13 ET | lem:separation, line 1409 | Convolution forms bounded by the kernel's Fourier supremum (Mathlib-only statement)

# Balog-Szemeredi-Gowers prerequisite

The finite inverse argument needs the classical Balog-Szemeredi-Gowers energy-to-small-difference theorem and its dense bipartite four-path prerequisite. Pinned Mathlib supplies Finset.addEnergy and basic finite inequalities, but direct searches found no quantitative BSG or dependent-random-choice four-path theorem; searches of ../lean-spherical, ../lean-dfr and ../lean-variationalsw found no adequate replacement. This substantial textbook additive-combinatorics theorem qualifies for the reusable-prerequisite exception. Develop exactly one independent module, TrilinearHT/Auto/BalogSzemerediGowers.lean, with general finite bipartite relations and finite subsets of arbitrary abelian groups. Its statements and supporting definitions use only Mathlib and that module, including Mathlib additive energy. Verified reference: blueprint lem:four-paths, lines 668-680, and lem:BSG, lines 683-698. Recorded before module creation at 2026-10-09 14:47:46 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 14:52:20 ET | lem:four-paths, lines 670-674 | Neighborhood/codegree double counting and first/second moments
complete | 2026-10-09 14:57:13 ET | lem:four-paths, lines 670-674 | Bad-pair averaging and selection of a dense neighborhood
complete | 2026-10-09 15:01:48 ET | lem:four-paths, line 675 | Deletion bound and retained vertex-set size
complete | 2026-10-09 15:08:14 ET | lem:four-paths, lines 675-679 | Common middle vertices and four-step path lower bound
complete | 2026-10-09 15:11:08 ET | lem:four-paths, lines 668 and 679-680 | Dense four-path theorem and proper-color path recovery
complete | 2026-10-09 15:14:54 ET | lem:BSG, lines 685-692 | Popular sums and the dense properly colored graph
complete | 2026-10-09 15:18:18 ET | lem:BSG, lines 693-697 | Injective path-color encoding of differences
complete | 2026-10-09 15:20:55 ET | lem:BSG, lines 683-698 | Energy-to-small-difference theorem with exponent ten

# Chang spectrum and Bohr cardinality prerequisite

The finite inverse theorem and dense Bogolyubov argument need Chang's quantitative spectrum-generating theorem and the Bohr-set cardinality estimate. Pinned Mathlib has AddDissociated, maximal dissociated span, and AddDissociated.randomisation (the Riesz-product mean identity), but direct searches found no quantitative spectrum cardinality bound or Bohr-set pigeonhole estimate; searches of ../lean-spherical, ../lean-dfr and ../lean-variationalsw found no replacement. This is a substantial classical finite harmonic-analysis theorem. Create exactly one independent module, TrilinearHT/Auto/ChangSpectrum.lean, using only Mathlib and local definitions for finite abelian groups, additive characters, and circle-valued homomorphisms. Reuse the existing randomisation and dissociation proofs. The source cyclic statement will be connected to the project's normalized Fourier transform in the main file. This is the reusable-prerequisite exception, not a blueprint-section split. Verified reference: blueprint lem:Chang, lines 730-764. Recorded before creation at 2026-10-09 15:25:46 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 15:30:40 ET | lem:Chang, lines 735-748 | Circle partition and large Bohr-set fiber
complete | 2026-10-09 15:34:22 ET | lem:Chang, lines 749-757 | Phase alignment and positive Riesz-product mean
complete | 2026-10-09 15:42:35 ET | lem:Chang, lines 758-763 | Logarithmic lower bound and Jensen cardinality estimate
complete | 2026-10-09 15:49:08 ET | lem:Chang, lines 739-764 | Spectrum generation, cyclic Fourier bridge and full-density case

# Khintchine and empirical sampling prerequisite

The later almost-period and signed-stack arguments need the general Khintchine upper inequality and its empirical-sampling consequence. Searches of pinned Mathlib Probability and Analysis found no Khintchine or symmetrization/sampling moment theorem; the repository already contains a complete proof adapted from ../lean-variationalsw. Extract that substantial textbook probability prerequisite, unchanged, into TrilinearHT/Auto/KhintchineSampling.lean. Include all sign, independent-copy, finite-mean, finite-Lp and convolution definitions it uses. A declaration-reference scan found only finiteAverage and finiteConvolution as outside dependencies; move those definitions too, so all statements depend only on Mathlib and local definitions. This invokes the reusable-prerequisite exception, not a blueprint section split. Extend this same independent empirical-sampling module with the Croot-Sisask almost-period consequence, blueprint lem:almostperiods, lines 766-784, using its existing probability norms and sampling theorem. No additional module is needed. Verified reference: blueprint lem:finite-fourier, lines 177-209; preserve sibling attribution. Recorded before creation at 2026-10-09 13:58:52 ET. Consolidation recorded at 2026-10-09 21:22:18 ET: move the already-proved finite Fourier foundations from main into this module, beside their local finiteAverage, finiteConvolution and uniformMean primitives; add the trilinear Fourier selection estimate needed for finite-inverse lines 1148-1157. The unchanged foundation statements depend only on Mathlib and this module.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-08 23:38:00 ET | lem:finite-fourier, lines 177–200 | Signs with constant 2 sqrt(p) and double randomization
complete | 2026-10-08 23:38:00 ET | lem:finite-fourier, lines 183–209 | Independent-copy symmetrization and sampling convolution bound with constant 4
complete | 2026-10-09 14:01:38 ET | lem:finite-fourier, lines 177-209 | Independent Khintchine and sampling module verification
complete | 2026-10-09 15:53:14 ET | lem:almostperiods, lines 766-783 | Finite probability Lp triangle and translation laws
complete | 2026-10-09 15:56:41 ET | lem:almostperiods, lines 777-781 | Markov bound and at least half good sample tuples
complete | 2026-10-09 16:01:15 ET | lem:almostperiods, lines 781-783 | Diagonal tuple fibers and a large parameter set
complete | 2026-10-09 16:05:17 ET | lem:almostperiods, lines 766-783 | Translation difference bound and exact sample-size density
complete | 2026-10-09 16:10:28 ET | lem:almostperiods, lines 775 and 783 | Iterated sum-difference almost periods

# Dense Bogolyubov prerequisite

The finite inverse argument needs the classical quasipolynomial dense Bogolyubov theorem: for every nonempty subset A of a finite cyclic group, 2A-2A contains a Bohr set with rank O(log^4(1/alpha)), reciprocal radius O(alpha^(-1) log^4(1/alpha)), and density exp(-O(log^5(1/alpha))). Searches of pinned Mathlib additive combinatorics/Fourier and ../lean-spherical, ../lean-dfr and ../lean-variationalsw found no such theorem. This substantial named theorem qualifies for the reusable-prerequisite exception. Create exactly one module, TrilinearHT/Auto/DenseBogolyubov.lean, general over all positive cyclic moduli and arbitrary finite subsets. Its theorem statements and local definitions use Mathlib/local vocabulary; proofs may reuse the already-verified KhintchineSampling and ChangSpectrum modules, as explicitly permitted by the skill. Do not import the main proof module or create a cycle. The main module has 9489 lines, but mathematical substance, not file length, justifies this split. Verified reference: blueprint lem:dense-Bohr, lines 786-820. Recorded before creation at 2026-10-09 16:10:28 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 16:16:13 ET | lem:dense-Bohr, lines 794-795 | Positive convolution witness, value at zero and difference-set support
complete | 2026-10-09 16:23:23 ET | lem:dense-Bohr, lines 796-805 | Sampling parameters and convolution amplification of almost periods
complete | 2026-10-09 16:30:47 ET | lem:dense-Bohr, lines 806-812 | Iterated averaging measure and Fourier multiplier
complete | 2026-10-09 16:39:28 ET | lem:dense-Bohr, lines 813-817 | Spectrum split and uniform Fourier translation estimate
complete | 2026-10-09 16:47:09 ET | lem:dense-Bohr, lines 786-820 | Quasipolynomial rank, radius, containment and density


# Hilbert-space atomic decomposition prerequisite

The decomposition in lem:inverse, lines 1218-1239, requires a substantial general Hilbert-space separation theorem for finite atomic sums and two seminorm balls, together with probability-L2 dual bounds. Mathlib supplies Hahn--Banach, Riesz representation and convex hulls but no matching quantitative atomic decomposition theorem; the sibling lean-spherical convex-duality module concerns scalar convex functions. Develop TrilinearHT/Auto/HilbertAtomicDecomposition.lean under the reusable-prerequisite exception, using only Mathlib and definitions local to that module in its statements. The general result will take an independently stated inverse-correlation hypothesis; the main file must discharge it using continuous_inverse. This is not a split along machine-blueprint sections. Recorded before creation at 2026-10-10 00:38:41 ET.

# Gowers–Cauchy–Schwarz and cube continuity prerequisite

The mixed cube estimates used by lem:cube-foundation and later local von Neumann arguments require the classical Gowers–Cauchy–Schwarz inequality, its U3 seminorm, and eight-input L2 continuity. A search of pinned Mathlib found no Gowers development; Haar integration and Holder provide only its ingredients. Move the already-proved general Haar-probability construction and its supporting cube definitions, without duplication, into TrilinearHT/Auto/GowersCauchySchwarz.lean. The inspected statements use only Mathlib and local definitions, and a declaration-dependency scan found no remaining main-file dependencies. This substantial general additive-combinatorial theorem qualifies for the reusable-prerequisite exception; it is not a machine-blueprint section split. Verified source: blueprint cube-definition, lines 162–175, and lem:cube-foundation, lines 216–237. Recorded before creation at 2026-10-09 10:55:13 ET. Extension recorded at 2026-10-09 21:49:19 ET: the continuous inverse requires finite-to-continuous convergence of cell-averaged cube integrals (lines 1183-1189). Searches of pinned Mathlib and sibling repositories found no ready Gowers discretization theorem. Develop the general cube discretization in this existing module, using Mathlib integration and approximation. Move the normalized finite Haar definition and its two basic instances from main here so all new statements use Mathlib/local definitions; retain source-specific chart applications in main.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-08 23:24:00 ET | cube-definition, lines 162–175 | Mixed cubes, squared-face identity, positivity and nonnegative roots
complete | 2026-10-08 23:55:00 ET | lem:cube-foundation, lines 216–231 | Coordinate reflection Cauchy–Schwarz and mixed cube bound
complete | 2026-10-09 00:00:00 ET | lem:cube-foundation, lines 218–232 | Homogeneity, triangle inequality, and bundled U3 seminorm
complete | 2026-10-09 00:15:00 ET | eq:cube-L2, lines 223–237 | Independent vertex halves and eight L2 bounds
complete | 2026-10-09 00:24:23 ET | lem:cube-foundation, lines 227–237 | Continuous extension to eight L2 inputs

# Fefferman–Stein maximal inequality prerequisite

The mixed maximal estimate in lem:vector-maximal needs the general vector Hardy–Littlewood theorem, absent from pinned Mathlib; the textbook Fefferman–Stein theorem is a substantial reusable prerequisite, developed for general exponents and finite inner measure spaces in TrilinearHT/Auto/FeffermanStein.lean, adapting the finite Hilbert-family proof in ../lean-variationalsw.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 00:27:15 ET | ../lean-variationalsw/VariationalSW/Auto/MarcinkiewiczInterpolation.lean, lines 692–914 | Weak-type interpolation and scalar maximal foundations
complete | 2026-10-09 00:30:18 ET | ../lean-variationalsw/VariationalSW/Auto/FeffermanSteinInequality.lean, lines 829–953 | Weighted maximal inequality, exponents above one
complete | 2026-10-09 00:36:18 ET | ../lean-variationalsw/VariationalSW/Auto/FeffermanSteinInequality.lean, lines 955–1114 | Mixed norm duality, outer exponent above inner
complete | 2026-10-09 00:41:08 ET | lem:vector-maximal, lines 248–250, permitted vector maximal theorem | Mixed Hölder and dual testing
complete | 2026-10-09 00:48:15 ET | lem:vector-maximal, lines 248–250, permitted vector maximal theorem | Remaining exponent range and truncation on finite inner measure spaces

# Lattice transference principle prerequisite

The successive-minima transference principle is needed by lem:transference and lem:lattice-box; pinned Mathlib supplies dual lattices and Minkowski's first theorem but no adequate successive-minima product bound. This is a substantial classical geometry-of-numbers theorem, here for arbitrary finite-dimensional real inner-product spaces, full lattices and compact symmetric convex bodies, with constants independent of the lattice and body. Its statement and all supporting definitions depend only on Mathlib and the dedicated TrilinearHT/Auto/LatticeTransference.lean. The already-proved integer-basis, reduced-basis and transference development is moved together before the main file reaches its 10000-line limit; the coefficient-box application remains in the main file. Verified references are blueprint lem:integer-basis, lem:reduced-basis and lem:transference, and pinned Mathlib.MeasureTheory.Group.GeometryOfNumbers and Mathlib.LinearAlgebra.BilinearForm.DualLattice.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 01:00:16 ET | lem:integer-basis, lines 257–263 | Primitive integer vector extends to a basis
complete | 2026-10-09 01:03:57 ET | lem:integer-basis, lines 257–263 | Saturated subgroup adapted basis and free quotient
complete | 2026-10-09 01:05:29 ET | lem:integer-basis, line 263 | Rational subspace integer intersection is saturated
complete | 2026-10-09 01:07:12 ET | lem:reduced-basis, line 279 | Finite bounded lattice intersections and shortest nonzero vector
complete | 2026-10-09 01:09:47 ET | lem:reduced-basis, line 279 | Shortest vector primitive and extendible to a lattice basis
complete | 2026-10-09 01:16:56 ET | lem:reduced-basis, line 279 | Remaining basis projects to a full lattice in the perpendicular space
complete | 2026-10-09 01:27:54 ET | lem:reduced-basis, line 279 | Induction on projected lattices and lifting the basis
complete | 2026-10-09 01:35:04 ET | lem:reduced-basis, line 279 | Descending integer size reduction preserves later projections
complete | 2026-10-09 01:40:07 ET | lem:reduced-basis, line 281 | Adjacent Gram–Schmidt length inequality
complete | 2026-10-09 01:44:45 ET | lem:reduced-basis, lines 281–286 | Geometric prefix sum and primal basis norm bound
complete | 2026-10-09 01:49:45 ET | lem:reduced-basis, lines 287–290 | Upper triangular inverse coefficient bound
complete | 2026-10-09 01:59:33 ET | lem:reduced-basis, lines 291–292 | Dual basis norm bound
complete | 2026-10-09 02:04:59 ET | lem:transference, lines 296–303 | Euclidean dual lattice and integer pairing
complete | 2026-10-09 02:10:25 ET | lem:transference, lines 296–305 | Symmetric convex body, polar, and gauge
complete | 2026-10-09 02:14:34 ET | lem:transference, line 305 | Successive minima are finite and attained
complete | 2026-10-09 02:18:17 ET | lem:transference, line 305 | Dimension and integer pairing give lower product bound
complete | 2026-10-09 02:21:48 ET | lem:transference, line 307 | Euclidean ball upper product bound
complete | 2026-10-09 02:30:01 ET | lem:transference, lines 309–313 | Maximum determinant basis and ellipsoid comparison
complete | 2026-10-09 02:34:55 ET | lem:transference, line 314 | Linear transport and full successive-minima product bound

# Quantitative rational linear algebra prerequisite

The rational height bounds needed throughout the finite coefficient constructions are absent from pinned Mathlib: its rational heights, determinants and projections do not provide the required uniform counting, inverse, pivot right-inverse and projection estimates. Effective rational linear algebra via common denominators and Cramer's rule is a substantial reusable development, including real scalar extension and operator norms. The complete development moves together to TrilinearHT/Auto/RationalLinearAlgebra.lean; all statements and local definitions depend only on Mathlib. This invokes the reusable-prerequisite exception, not a split along machine-generated blueprint sections. Verified references are blueprint lem:rational-linear, lines 416–420, and the pinned Mathlib rational, matrix adjugate, rank and orthogonal-projection developments. The independently reusable height-bin theorem (lem:height, lines 603–619) extends this same module using its local rationalHeight and sharp denominator/minor bounds; no project-specific operator data enter its statements.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 04:31:15 ET | lem:rational-linear, lines 416–418 | Bounded-height rational and matrix counting
complete | 2026-10-09 04:37:05 ET | lem:rational-linear, line 420 | Common denominators and determinant bounds
complete | 2026-10-09 04:47:12 ET | lem:rational-linear, lines 418–420 | Nonsingular inverse heights and operator norms
complete | 2026-10-09 04:57:14 ET | lem:rational-linear, line 420 | Pivot right inverses and bounded-height basis selection
complete | 2026-10-09 05:03:39 ET | lem:rational-linear, line 420 | Gram inverse formula for the orthogonal row-space projection
complete | 2026-10-09 05:08:24 ET | lem:rational-linear, line 420 | Common integer numerator and denominator bounds for projections
complete | 2026-10-09 05:10:46 ET | lem:rational-linear, lines 418–420 | Exponential projection height and norm bounds
complete | 2026-10-09 05:14:42 ET | lem:rational-linear, line 420 | Arbitrary rational systems and orthogonal complements
complete | 2026-10-09 12:23:24 ET | lem:height, proof line 617 | Sharp per-vector denominator clearing with entries bounded by B^d
complete | 2026-10-09 12:35:56 ET | lem:height, proof line 617 | Bounded nonzero integer circuit coefficients
complete | 2026-10-09 12:44:46 ET | lem:height, proof line 617 | Independence of geometrically separated nonzero evaluations
complete | 2026-10-09 12:52:49 ET | lem:height, lines 603 and 617 | Greedy cover by at most d logarithmic intervals
complete | 2026-10-09 13:04:45 ET | lem:height, lines 603-610 and 617 | Dyadic magnitude bins and translated scale counts
complete | 2026-10-09 16:47:09 ET | eq:tiny-sum, lines 611–617 | Geometric small-value tail summed over occupied bins
complete | 2026-10-09 13:27:14 ET | lem:height, lines 616-617 | Coordinate suprema and Euclidean-norm enlargements

# Dyadic stopping and logarithmic hull maximal prerequisite

The fixed-function hull cuts in lem:cuts need a general finite dyadic stopping theorem absent from pinned Mathlib; finite integration, Markov and layer-cake results supply its classical ingredients. The complete grid, path packing and first-crossing development in TrilinearHT/Auto/DyadicStopping.lean is independently stated for arbitrary real dyadic grids, finite families and normed-space-valued L2 functions, using only Mathlib and its own definitions. Its dedicated module is justified before creation at 2026-10-09 06:18:23 ET and serves later root-normalized attempts as well as path-packing and lem:cuts.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 06:18:23 ET | line 364 | Real dyadic grid data, partitions and children
complete | 2026-10-09 05:22:11 ET | eq:path, lines 424–428 | Exact finite dyadic path integral identity
complete | 2026-10-09 05:25:27 ET | path-packing, line 429 | Generation decay and geometric restart bound
complete | 2026-10-09 05:28:40 ET | path-packing, line 429 | Combining first-stop families by maximal union cells
complete | 2026-10-09 05:31:58 ET | lem:cuts, lines 433–436 | Dyadic nesting and disjoint maximal cells
complete | 2026-10-09 05:34:17 ET | lem:cuts, lines 435–436 | Ancestor sums, first crossings and retained cells
complete | 2026-10-09 05:43:43 ET | lem:cuts, line 451 | First-crossing length cost from path integration and Markov
complete | 2026-10-09 05:46:23 ET | lem:cuts, lines 436 and 451 | Everywhere bound for retained ancestor sums
complete | 2026-10-09 05:50:31 ET | lem:cuts, lines 453–457 | Finite hull maximal weak bound and support bound
complete | 2026-10-09 05:59:06 ET | lem:cuts, lines 458–462 | Truncated hull maxima logarithmic integral estimate
complete | 2026-10-09 06:04:06 ET | lem:cuts, line 463 | Partial hull maxima through the current depth and full-max domination
complete | 2026-10-09 06:11:17 ET | lem:cuts, lines 458 and 463–465 | Individual and truncated-sum first-crossing costs and their combination
complete | 2026-10-09 06:18:00 ET | eq:hull-cap, lines 444–448 and 464–465 | Everywhere whole-cell cap on retained hull maxima

complete | 2026-10-09 08:14:25 ET | lem:compression, line 553 | Finite dyadic descendant generations and partition identities
complete | 2026-10-09 08:18:00 ET | lem:compression, line 553 | Enclosing finite cell families in complete finite dyadic trees
complete | 2026-10-09 08:28:30 ET | lem:compression, line 553 | Finite threshold stopping cuts and terminal partition identities
complete | 2026-10-09 08:32:31 ET | lem:compression, line 553 | Parent averages and the four-times-root threshold-cut estimate
complete | 2026-10-09 08:36:05 ET | lem:compression, line 553 | Iterated doubling roots and finite depth termination
complete | 2026-10-09 08:41:02 ET | lem:compression, line 553 | Deepest stopping-root assignment and size-segment partitions
complete | 2026-10-09 09:10:35 ET | lem:compression, lines 561–565 | Local weak-type distribution and weighted layer-cake energy inequality
complete | 2026-10-09 09:18:35 ET | lem:compression, lines 561–565 | Finite dyadic maximal L2 estimate with norm constant two
complete | 2026-10-09 09:23:00 ET | lem:compression, lines 561–564 | Pointwise geometric square-average bound along stopping paths
complete | 2026-10-09 09:34:12 ET | lem:compression, line 565 | Small-size geometric sums and logarithmic counts of large stopping sizes
complete | 2026-10-09 09:42:35 ET | lem:compression, line 565 | Abstract logarithmic energy estimate for supported moment families

complete | 2026-10-09 10:01:46 ET | lem:compression, line 567 | Norm-threshold anchor generations, finite termination and restart assignment

complete | 2026-10-09 10:09:32 ET | lem:compression, line 569 | Completion of anchor generations to refining terminal partitions

complete | 2026-10-09 10:27:41 ET | lem:compression, lines 569–572 | Jump ancestors and disjoint-cell L2 mass bounds

# Rademacher–Menshov and nested projection products prerequisite

Justification: the dyadic-prefix row estimate and noncommuting nested-product consequences needed by lem:prefix (lines 508–535) are absent from pinned Mathlib and searched sibling repositories. The classical Rademacher–Menshov dyadic decomposition is a substantial general Hilbert-space theorem (Tao, 247A Lecture Notes 2, page 31, Q14–Q15); one independent Mathlib-only module, TrilinearHT/Auto/RademacherMenshov.lean, will contain the finite row version, nested projections and disjoint-interval jumps, with no project-specific column data. Recorded before creation at 2026-10-09 07:32:32 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 07:37:43 ET | lem:prefix proof, lines 522–526 | Orthogonal block energy and restriction of square-summable rows
complete | 2026-10-09 07:43:58 ET | lem:prefix proof, lines 522–527 | Dyadic prefix decomposition and logarithmic row estimate
complete | 2026-10-09 07:49:01 ET | lem:prefix, lines 508–514 and 522–527 | Nested projection increments and exact logarithmic prefix bound
complete | 2026-10-09 07:53:09 ET | lem:prefix, lines 508–514 and 524–527 | Noncommuting products of nested projection layers
complete | 2026-10-09 07:59:32 ET | eq:product-jump, lines 515–519 and 529–534 | Product telescoping and square-sum jump estimate
complete | 2026-10-09 08:06:08 ET | lem:prefix, lines 519 and 534 | Disjoint-interval product jumps and empty products

complete | 2026-10-09 10:45:41 ET | lem:compression, line 579 | Explicit logarithmic prefix count and numerical restart contraction
complete | 2026-10-09 11:43:48 ET | lem:compression, line 597 | General cubic layer-count and logarithmic budget prefix bound
complete | 2026-10-09 11:56:34 ET | lem:compression, line 597 | General complement-product expansion and finite row bound
complete | 2026-10-09 12:11:54 ET | lem:compression, lines 550 and 597 | Finite row averages for arbitrary complex measures and total variation

# Minkowski integral inequality prerequisite

Justification: lem:shortblock (lines 2328-2340: "Minkowski and the sign moments give (E‖F^σ(n,·)‖_2^a)^(1/a) ≤ C_a e_j(n)", and the deletion bound) needs Minkowski's integral inequality (L^p norm of an integral at most the integral of L^p norms). Searches of pinned Mathlib (MeasureTheory/Integral/MeanInequalities: only the two-function Minkowski inequality) and the repository found no integral version. It is a named textbook theorem (Stein, Singular Integrals, Appendix A.1; Hardy–Littlewood–Pólya, Inequalities, Thm 202). Stated for ℝ≥0∞-valued jointly measurable f, σ-finite μ, s-finite ν, p ≥ 1, depending only on Mathlib, in TrilinearHT/Auto/MinkowskiIntegralInequality.lean. Recorded before creation at 2026-10-11 14:44:15 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-11 14:47:28 ET | lem:shortblock, line 2330 | Minkowski integral inequality via Hölder duality and truncation (lintegral_minkowski)

# Main proof ledger

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-08 21:53:39 ET | lem:budget-rules, lines 82–101 | Sums and products of quasipolynomial bounds
complete | 2026-10-08 21:53:39 ET | lem:budget-rules, lines 82–101 | Positive fixed powers and compositions
complete | 2026-10-08 21:58:59 ET | lem:budget-rules, lines 82–101 | Polynomial logarithmic bounds and parameter-uniform degrees
complete | 2026-10-08 21:58:59 ET | lem:budget-rules, lines 82–101 | Compression overhead bound in logarithmic k
complete | 2026-10-08 21:58:59 ET | lem:budget-rules, lines 82–101 | Domination by every positive power of P
complete | 2026-10-08 23:05:08 ET | lem:fourier-foundation, lines 137–157 | Separated-frequency rows, multipliers, finite Schur test, and Hilbert duality
complete | 2026-10-08 23:10:30 ET | lem:fourier-foundation, lines 143–158 | Quadratic oscillatory integral
complete | 2026-10-08 23:24:00 ET | cube-definition, lines 162–175 | Probability counting measure and normalized finite convolution
complete | 2026-10-08 23:48:00 ET | lem:finite-fourier, lines 190–213 | Finite cyclic Fourier inversion, Parseval, and convolution
complete | 2026-10-08 23:48:00 ET | lem:finite-fourier, lines 192–213 | U2 Fourier identity and U3 recursion
complete | 2026-10-09 00:53:14 ET | lem:vector-maximal, lines 240–251 | Real-line transport and Mq mixed norm power identities
complete | 2026-10-09 04:03:13 ET | line 67 and lem:vector-maximal, lines 240–251 | Uncentered maximal comparison and source specialization
complete | 2026-10-09 02:38:35 ET | lem:lattice-box, lines 329–331 | Reduced basis and uniform weighted coordinate bound
complete | 2026-10-09 02:40:44 ET | lem:lattice-box, lines 332–336 | Integer side lengths, active basis subset, and norm budget
complete | 2026-10-09 02:43:55 ET | lem:lattice-box, lines 337–342 | Explicit radius and containment of small lattice vectors
complete | 2026-10-09 02:46:06 ET | lem:lattice-box, lines 325, 344 | Partial sums, empty box, and complete coefficient-box theorem
complete | 2026-10-09 02:52:41 ET | lem:torus-annihilator, line 358 | Integer basis coordinate automorphism and annihilator model
complete | 2026-10-09 02:57:38 ET | lem:torus-annihilator, line 358 | Coordinate torus homeomorphism and connectedness
complete | 2026-10-09 03:02:30 ET | lem:torus-annihilator, lines 350–352, 358 | Haar character integral equals the lattice indicator
complete | 2026-10-09 03:05:20 ET | lem:torus-annihilator, lines 354–358 | Nonzero integer multiplication and progression surjectivity
complete | 2026-10-09 03:13:39 ET | lem:torus-annihilator, lines 358–360 | Progression map preserves Haar probability
complete | 2026-10-09 03:19:36 ET | lem:absolute, line 390 | Reciprocal exponent polytope is the convex hull of Boolean endpoints
complete | 2026-10-09 03:24:08 ET | lem:absolute, line 392 | Positive interpolation by finite Hölder
complete | 2026-10-09 03:30:47 ET | eq:local and lem:absolute, lines 366–388 | Real local form and endpoint change of variables estimates
complete | 2026-10-09 03:37:20 ET | lem:absolute, line 394 | Torus and integer lattice endpoint estimates
complete | 2026-10-09 03:55:09 ET | eq:absolute, lines 378–396 | Full positive local form estimate in all three settings
complete | 2026-10-09 04:11:38 ET | eq:local, eq:marginals and eq:CN, lines 364–403 | Dyadic grid and admissible kernel-family data
complete | 2026-10-09 04:15:03 ET | lem:finite-CN, line 409 | Local norms bounded by uncentered maximal functions
complete | 2026-10-09 04:22:34 ET | lem:finite-CN, line 409 | Disjoint depth summation gives linear depth bound
complete | 2026-10-09 04:24:35 ET | eq:CN, lines 398–403 | Real supremum of positive finite-denominator ratios
complete | 2026-10-09 04:26:36 ET | lem:finite-CN, lines 405–411 | Least constant, zero denominator and infinite denominator cases
complete | 2026-10-09 06:26:52 ET | column-data, lines 470–481 | Finite private-coordinate column data and inherited masks
complete | 2026-10-09 06:31:55 ET | column-data, lines 480–483 | Cell-supported L2 columns and finite-dimensional projection ranges
complete | 2026-10-09 06:37:27 ET | column-data, lines 480–483 | Restriction to descendants preserves old column combinations
complete | 2026-10-09 06:40:45 ET | column-data, lines 480–483 | Cell support and orthogonality of disjoint column ranges
complete | 2026-10-09 06:43:15 ET | column-data, lines 480–483 | Finite stopping-partition ranges and direct-sum projections
complete | 2026-10-09 06:47:42 ET | column-data, lines 480–483 | Refinement range inclusion and nested orthogonal projections
complete | 2026-10-09 06:50:38 ET | column-data, line 483 | Row-family square bound and exact decision-cell locality interface
complete | 2026-10-09 07:00:16 ET | lem:coeff, lines 487–491 and 503 | Private-coordinate lower bound and column-sum upper bound
complete | 2026-10-09 07:11:31 ET | lem:coeff, line 503 | Positive averaged Gram operator and inverse bound
complete | 2026-10-09 07:15:33 ET | lem:coeff, line 503 | Inverse-Gram formula for orthogonal projection coefficients
complete | 2026-10-09 07:20:53 ET | lem:coeff, line 503 | Pointwise projection kernel formula and norm bound
complete | 2026-10-09 07:23:24 ET | lem:coeff, lines 492–495 | D5 average-to-supremum projection bound
complete | 2026-10-09 07:32:32 ET | eq:predictor-moment, lines 496–503 | Predictor moment identity and coefficient uniqueness
complete | 2026-10-09 08:06:08 ET | lem:prefix, lines 508–535 | Nested-product row, successive-jump and disjoint-interval estimates
complete | 2026-10-09 08:24:02 ET | lem:compression, lines 553 and 569 | Extend inherited masks to the completed tree while preserving original projections
complete | 2026-10-09 08:47:11 ET | lem:compression, line 553 | Doubling-average stopping roots, size segments and terminal cut partitions
complete | 2026-10-09 08:49:22 ET | lem:compression, line 553 | Cut-cell averages are at most four times the segment-root average
complete | 2026-10-09 08:54:01 ET | eq:moment-representative, lines 555–556 | Cut-supported projections onto segment-ancestor columns
complete | 2026-10-09 08:58:12 ET | eq:moment-representative, lines 558–559 | Uniform bound and projection energy identity for moment representatives
complete | 2026-10-09 09:04:40 ET | eq:moment-representative, lines 559–561 | Preservation of every first-layer segment projection
complete | 2026-10-09 09:27:18 ET | lem:compression, lines 561–564 | Dyadic maximal L2 bound and square-average stopping energy
complete | 2026-10-09 09:52:57 ET | lem:compression, line 565 | Logarithmic aggregate energy of moment representatives
complete | 2026-10-09 09:55:47 ET | lem:compression, line 567 | Common coefficient space and cell-product representation
complete | 2026-10-09 10:05:12 ET | lem:compression, line 567 | Coefficient anchors and finite restart attempts
complete | 2026-10-09 10:23:00 ET | lem:compression, lines 569–572 | Refining anchor partitions and private-coordinate jump lower bounds
complete | 2026-10-09 10:30:10 ET | lem:compression, lines 570–572 | Integrated restart-length jump budget
complete | 2026-10-09 10:39:00 ET | lem:compression, lines 573–578 | Restart length and energy contraction ratios
complete | 2026-10-09 10:49:05 ET | lem:compression, line 579 | Specialize numerical contraction below one half
complete | 2026-10-09 11:04:34 ET | lem:compression, line 579 | Total attempt length and energy packing
complete | 2026-10-09 11:08:49 ET | lem:compression, line 581 | Finite attempt-root and last-anchor assignment
complete | 2026-10-09 11:13:59 ET | lem:compression, line 581 | Anchor row control from the nested-product prefix theorem
complete | 2026-10-09 11:17:53 ET | lem:compression, lines 587–589 | Birth-supported columns and integrated path-budget bound
complete | 2026-10-09 11:21:52 ET | lem:compression, lines 581–584 | Exact local coefficient-error formula
complete | 2026-10-09 11:29:19 ET | lem:compression, lines 585–589 | Coefficient-error row estimate from the original Bessel bound
complete | 2026-10-09 11:32:01 ET | lem:compression, lines 592–595 | Combine anchor and error rows on a fixed attempt
complete | 2026-10-09 11:35:05 ET | lem:compression, lines 591–595 | Sum attempt packing within each size segment
complete | 2026-10-09 11:40:16 ET | lem:compression, lines 591–595 | Sum size segments using logarithmic moment energy
complete | 2026-10-09 11:51:55 ET | eq:compression, line 597 | Polynomial prefix constant and final depth-independent estimate
complete | 2026-10-09 12:04:59 ET | lem:compression, lines 548–550 and 597 | Spatial compression for projection complements
complete | 2026-10-09 12:16:34 ET | lem:compression, lines 548–550 and 597 | Fixed averages with total-variation cost
complete | 2026-10-09 13:37:25 ET | def:chart, lines 625-637 | Quadratic chart data, atom formula, Gevrey complexity and boundedness
complete | 2026-10-09 13:43:28 ET | def:chart, lines 635-637 | Finite lattice summands and pointwise counting
complete | 2026-10-09 13:55:36 ET | def:chart, lines 635-637 | Zero-dimensional phases and quasipolynomial normalization
complete | 2026-10-09 13:58:52 ET | lem:chart-operations, lines 642-660 | Complex conjugation with unchanged complexity and boundedness
complete | 2026-10-09 14:04:38 ET | lem:chart-operations, lines 642-660 | Real dilation with unchanged complexity and boundedness
complete | 2026-10-09 14:10:13 ET | lem:chart-operations, lines 642-646 | Block-diagonal product chart and exact atom multiplication
complete | 2026-10-09 14:17:27 ET | lem:chart-operations, lines 642-646 | Product cutoff derivative and complexity bounds
complete | 2026-10-09 14:22:10 ET | lem:chart-operations, lines 642-646 | Fixed finite product closure and boundedness
complete | 2026-10-09 14:25:21 ET | lem:chart-operations, lines 646-653 | Denominator clearing and uniformly bounded offset reduction
complete | 2026-10-09 14:30:31 ET | lem:chart-operations, lines 646-653 | Translation phase identity and exact translated atom
complete | 2026-10-09 14:35:07 ET | lem:chart-operations, lines 646-653 | Translated phase-modulated cutoff derivative bounds
complete | 2026-10-09 14:38:17 ET | lem:chart-operations, lines 646-653 | Uniform translation complexity and quasipolynomial budget
complete | 2026-10-09 14:40:59 ET | lem:chart-operations, lines 642-653 | Uniform affine closure and boundedness
complete | 2026-10-09 14:47:46 ET | Chart formula and matrix decomposition, lines 656-660 | Several-variable atoms and symmetric/skew matrix parts
complete | 2026-10-09 15:25:46 ET | lem:sumset-growth, lines 701-728 | Ruzsa triangle and minimal-growth iteration via Mathlib
complete | 2026-10-09 16:50:36 ET | lem:derivative-graph, lines 829-835 | Large derivative Fourier coefficients and dense frequency selection
complete | 2026-10-09 16:54:57 ET | lem:derivative-graph, lines 836-841 | Squared derivative correlation identity and positive lower bound
complete | 2026-10-09 17:02:06 ET | lem:derivative-graph, lines 842-848 | First Cauchy-Schwarz step and translated square expansion
complete | 2026-10-09 17:05:02 ET | lem:derivative-graph, lines 849-855 | Second Cauchy-Schwarz step and differenced character averages
complete | 2026-10-09 17:11:29 ET | lem:derivative-graph, lines 856-861 | Character orthogonality and exact graph energy count
complete | 2026-10-09 17:15:20 ET | lem:derivative-graph, lines 822-863 | Derivative graph with density, correlation and delta-to-the-64th energy
complete | 2026-10-09 17:20:48 ET | lem:local-frequency, line 881 | Large small-difference subgraph retaining derivative correlations
complete | 2026-10-09 17:25:04 ET | lem:local-frequency, lines 883-885 | Vertical obstruction set and K-to-the-seventeenth cardinality
complete | 2026-10-09 17:33:29 ET | lem:local-frequency, line 887 | Half-density bound for nonzero character tests
complete | 2026-10-09 17:38:11 ET | lem:local-frequency, line 887 | Logarithmic separating family of character tests
complete | 2026-10-09 17:41:27 ET | lem:local-frequency, line 889 | Dense common torus cube for graph frequencies
complete | 2026-10-09 17:45:57 ET | lem:local-frequency, line 889 | Elimination of vertical obstructions and iterated graph property
complete | 2026-10-09 17:49:05 ET | lem:local-frequency, line 891 | Bohr domain with the unit frequency and small radius
complete | 2026-10-09 17:53:21 ET | lem:local-frequency, line 891 | Unique Freiman frequency map and halving in odd modulus
complete | 2026-10-09 17:59:03 ET | lem:local-frequency, lines 865-893 | Quantitative locally additive frequency with retained correlations
complete | 2026-10-09 18:03:55 ET | lem:Bohr-weight, lines 895-914 | Centered-circle weights, support and mass bounds
complete | 2026-10-09 18:09:54 ET | lem:Bohr-weight, lines 914-915 | Periodic cutoff Lipschitz and product translation bounds
complete | 2026-10-09 18:14:35 ET | lem:Bohr-weight, lines 917-925 | Weighted local-character identity and Fourier decay
complete | 2026-10-09 18:19:19 ET | lem:Bohr-weight, lines 895-926 | Complete smooth Bohr weight theorem
complete | 2026-10-09 18:23:17 ET | lem:local-symmetry, lines 951-955 | Bohr calculus, weight interfaces and admissible inner radius
complete | 2026-10-09 18:26:42 ET | lem:local-symmetry, lines 955-958 | Weighted translation localization of the initial correlation
complete | 2026-10-09 18:30:22 ET | lem:local-symmetry, lines 959-964 | First weighted Cauchy-Schwarz and square expansion
complete | 2026-10-09 18:34:35 ET | lem:local-symmetry, lines 965-973 | Alternating phase identity and change of variables
complete | 2026-10-09 18:40:39 ET | lem:local-symmetry, lines 974-977 | Weight replacement and selection of one outer parameter
complete | 2026-10-09 18:49:21 ET | lem:local-symmetry, lines 978-982 | Second Cauchy-Schwarz and averaged local Fourier correlation
complete | 2026-10-09 18:53:35 ET | lem:local-symmetry, lines 983-989 | Large local spectrum set and ordinary density
complete | 2026-10-09 18:58:12 ET | lem:local-symmetry, lines 990-999 | Local Fourier decay on the iterated spectrum difference set
complete | 2026-10-09 19:02:00 ET | lem:local-symmetry, lines 1000-1007 | Dense Bohr subdomain and refined radius
complete | 2026-10-09 19:06:12 ET | lem:local-symmetry, lines 1008-1013 | Doubling the Bohr domain and controlling the alternating phase
complete | 2026-10-09 19:11:42 ET | lem:local-symmetry, lines 951-1015 | Correlation assembly with explicit complexity cost
complete | 2026-10-09 19:16:27 ET | lem:local-symmetry, lines 1015-1016 | Logarithmic bounds for inner radius, mass and decay constant
complete | 2026-10-09 19:20:45 ET | lem:local-symmetry, line 1017 | Polynomial complexity and complete local symmetry theorem
complete | 2026-10-09 19:32:50 ET | lem:local-chart, lines 1035-1039 | Cyclic Bohr full lattice, integer sublattice and quotient map
complete | 2026-10-09 19:40:07 ET | lem:local-chart, lines 1041 | Scaled coefficient box and injective Bohr projection
complete | 2026-10-09 19:45:55 ET | lem:local-chart, lines 1043-1052 | Local additivity on coefficient paths and quadratic polynomial
complete | 2026-10-09 19:53:23 ET | lem:local-chart, lines 1054-1057 | Integral dual basis and integer linear coordinate formula
complete | 2026-10-09 19:58:25 ET | lem:local-chart, line 1054 | Supported centered lift and coefficient-box containment
complete | 2026-10-09 20:06:09 ET | lem:local-chart, lines 1058-1067 | Coefficient reduction modulo one and phase substitution
complete | 2026-10-09 20:16:55 ET | lem:local-chart, lines 1069-1076 | Rational block chart and partitioned lattice-sum formula
complete | 2026-10-09 20:25:07 ET | lem:local-chart, line 1078 | Integer values and global boundedness of the constructed chart
complete | 2026-10-09 20:31:36 ET | lem:local-chart, lines 1080-1082 | Tensor cutoff and bounded quadratic-phase derivative estimates
complete | 2026-10-09 20:40:24 ET | lem:local-chart, line 1082 | Uniform Gevrey bound for the actual doubled amplitude
complete | 2026-10-09 20:48:31 ET | lem:local-chart, line 1084 | Quasipolynomial complexity and complete local-chart theorem
complete | 2026-10-09 20:54:41 ET | thm:finite-inverse, lines 1100-1104 | Weighted translate mass and supported basepoint selection
complete | 2026-10-09 20:56:47 ET | thm:finite-inverse, lines 1104-1107 | Affine derivative frequency on the selected Bohr translate
complete | 2026-10-09 21:05:49 ET | thm:finite-inverse, lines 1109-1114 | Phase alignment and the initial local correlation
complete | 2026-10-09 21:09:38 ET | thm:finite-inverse, lines 1116-1120 | Symmetry refinement and quantitative final radius
complete | 2026-10-09 21:15:18 ET | thm:finite-inverse, lines 1122-1127 | Shift averaging, weight error and supported translate selection
complete | 2026-10-09 21:17:08 ET | thm:finite-inverse, lines 1128-1132 | Spatial localization to the two weighted variables
complete | 2026-10-09 21:21:25 ET | thm:finite-inverse, lines 1133-1146 | Skew-phase replacement and exact local polarization
complete | 2026-10-09 21:31:20 ET | thm:finite-inverse, lines 1148-1157 | Fourier extraction of weighted quadratic correlation
complete | 2026-10-09 21:36:08 ET | thm:finite-inverse, line 1159 | Translated modulated bounded chart and exact input correlation
complete | 2026-10-09 21:41:51 ET | thm:finite-inverse, lines 1114, 1120, 1159 | Common uniform quasipolynomial budget for all parameters
complete | 2026-10-09 21:49:19 ET | thm:finite-inverse, lines 1088-1159 | Complete finite inverse theorem
complete | 2026-10-09 21:57:25 ET | lem:inverse, lines 1183-1187 | Cell averages, boundedness and no-wraparound supported cubes
complete | 2026-10-09 22:40:10 ET | lem:inverse, lines 1187-1189 | Continuous supported cube Riemann sums and torus Haar identification
complete | 2026-10-09 22:46:03 ET | lem:inverse, line 1189 | Eight-factor L1 stability of bounded cube averages
complete | 2026-10-09 22:50:58 ET | lem:inverse, line 1189 | L1 contraction of cell averaging with the cyclic normalization
complete | 2026-10-09 22:58:58 ET | lem:inverse, line 1189 | Unit-bounded continuous interior approximation in L1
complete | 2026-10-09 23:04:40 ET | lem:inverse, line 1189 | Uniform approximation and convergence for bounded measurable functions
complete | 2026-10-09 23:13:58 ET | lem:inverse, lines 1191-1195 | Selection and normalization of the finite inverse witness
complete | 2026-10-09 23:21:20 ET | lem:inverse, lines 1197 | Integer-preserving reduction of unrestricted chart parameters
complete | 2026-10-09 23:34:58 ET | lem:inverse, lines 1199-1214 | Exact floor interpolation and global boundedness
complete | 2026-10-09 23:56:35 ET | lem:inverse, lines 1214 | Uniform Gevrey complexity of the interpolated chart
complete | 2026-10-10 00:18:30 ET | lem:inverse, lines 1216 | Cell integral identity and the continuous inverse witness on intervals
complete | 2026-10-10 00:38:41 ET | lem:inverse, lines 1218 | L2 realization of the interval U3 seminorm
complete | 2026-10-10 00:48:24 ET | lem:inverse, lines 1218-1237 | Balanced convex separation and the three dual bounds
complete | 2026-10-10 01:01:37 ET | lem:inverse, line 1239 | Inverse contradiction and finite L2 decomposition
complete | 2026-10-10 01:10:05 ET | lem:inverse, lines 1173-1183 and 1239 | Probability-L2 interval normalization and general-interval decomposition
complete | 2026-10-10 01:15:13 ET | lem:inverse, line 1239 | One quasipolynomial chart and coefficient budget
complete | 2026-10-10 01:15:13 ET | lem:inverse, lines 1173-1241 | Complete continuous inverse and decomposition theorem
complete | 2026-10-10 01:24:38 ET | lem:return-splitting, lines 1265-1269 | Short-return bilinear identity, integer pairing and isotropy
complete | 2026-10-10 01:30:55 ET | lem:return-splitting, lines 1271 | Zero-dimensional short-return bound
complete | 2026-10-10 01:35:52 ET | lem:return-splitting, lines 1271-1275 | Symmetric convex return body with nonempty interior
complete | 2026-10-10 01:40:59 ET | lem:return-splitting, lines 1275-1279 | An empty interval of successive minima
complete | 2026-10-10 01:53:23 ET | lem:return-splitting, lines 1279-1281 | Isotropic span of short return lattice points
complete | 2026-10-10 01:56:30 ET | lem:return-splitting, line 1281 | Rank gap and annihilation by short dual vectors
complete | 2026-10-10 02:00:10 ET | lem:return-splitting, line 1281 | Transference dual basis spanning the orthogonal complement
complete | 2026-10-10 02:03:22 ET | lem:return-splitting, line 1281 | Dual coordinate and velocity-pairing bounds
complete | 2026-10-10 02:08:39 ET | lem:return-splitting, lines 1281-1285 | Rational slow projection with controlled height
complete | 2026-10-10 02:15:13 ET | lem:return-splitting, lines 1281-1285 | Bounded slow velocity
complete | 2026-10-10 02:19:35 ET | lem:return-splitting, lines 1287-1292 | Quantitative coordinate-axis returns by torus pigeonhole
complete | 2026-10-10 02:30:17 ET | lem:return-splitting, lines 1293-1300 | Effective quadratic identity and column bounds
complete | 2026-10-10 07:24:03 ET | lem:return-splitting, lines 1300 | Uniform quasipolynomial short-return budget
complete | 2026-10-10 07:32:42 ET | Declaration return-splitting, line 1302 | THT.Chart.shortReturnSplitting
complete | 2026-10-10 07:38:45 ET | lem:weyl, lines 1321-1331 | Exact quadratic lattice return phase and reindexing
complete | 2026-10-10 07:48:44 ET | lem:weyl, lines 1321-1331 | Uniform amplitude and localized return-error estimates
complete | 2026-10-10 07:56:49 ET | lem:weyl, line 1321 | Localized support, L1, L2 and first-moment bounds
complete | 2026-10-10 08:01:13 ET | lem:weyl, line 1333 | Fourier Lipschitz bound from the first absolute moment
complete | 2026-10-10 08:25:42 ET | lem:weyl, line 1333 | Quantitative propagation along return multiples
complete | 2026-10-10 08:44:51 ET | lem:weyl, line 1333 | Disjoint frequency balls and Plancherel mass bound
complete | 2026-10-10 08:44:51 ET | lem:weyl, line 1333 | Uniform return threshold and denominator budget
complete | 2026-10-10 08:44:51 ET | Declaration weyl, line 1335 | THT.Chart.weylSplitting
complete | 2026-10-10 08:51:14 ET | lem:chartfourier, lines 1349-1355 | Exact symmetric/skew phase extraction of the effective quadratic form
complete | 2026-10-10 08:58:39 ET | lem:chartfourier, line 1355 | Smooth periodic functions on R^n have absolutely convergent Fourier series with derivative-controlled coefficients
complete | 2026-10-10 09:08:31 ET | lem:chartfourier, line 1355 | Even clearing period, residue phase and slow lattice values with quasipolynomial count
complete | 2026-10-10 09:08:31 ET | lem:chartfourier, lines 1357-1361 | Exact equality cutoff and periodic two-variable amplitude identity
complete | 2026-10-10 09:13:30 ET | lem:chartfourier, lines 1361-1363 | Periodization in the slow variable and rescaling to unit periods
complete | 2026-10-10 09:25:09 ET | lem:chartfourier, lines 1368-1372 | Uniform derivative bounds of the rescaled periodic amplitudes
complete | 2026-10-10 10:20:52 ET | lem:chartfourier, lines 1363-1366 and 1372-1377 | Fourier substitution, rational heights, coefficient decay, shell bounds, family count
complete | 2026-10-10 10:20:52 ET | Declaration chart-fourier, line 1379 | THT.Chart.splitFourierExpansion
complete | 2026-10-10 10:24:56 ET | lem:separation, lines 1401-1405 | Fixed rational coefficients and the exact quadratic/lift phase identity
complete | 2026-10-10 10:35:27 ET | lem:separation, lines 1402-1404 | Bounded carries, exact equality cutoff and the coupled amplitude for one atom
complete | 2026-10-10 10:40:13 ET | lem:separation, line 1407 | Product-cutoff Fourier expansion of a compactly supported smooth amplitude
complete | 2026-10-10 10:55:36 ET | lem:separation, line 1407 | Factorization into three chart amplitudes and exact one-atom separation
complete | 2026-10-10 11:06:47 ET | lem:separation, line 1407 | Product of the two separated atoms and normalization to bounded atoms
complete | 2026-10-10 11:32:21 ET | lem:separation, line 1407 | Shell mass, dimension and complexity bounds of the separated terms
complete | 2026-10-10 12:00:35 ET | lem:separation, line 1409 | Single-scale two-slot form norm bound by the Fourier supremum A_r
complete | 2026-10-10 12:17:26 ET | lem:separation, line 1411 | Separated phase eq:separated-phase from the Weyl splitting and Fourier expansion
complete | 2026-10-10 12:53:29 ET | lem:separation, line 1411 | Uniform separated approximation of the two-variable kernel by bounded atoms
complete | 2026-10-10 13:14:38 ET | Declaration separation, line 1413 | THT.Chart.progressionSeparation (progressionSeparation, separated_form_le)
complete | 2026-10-10 13:41:06 ET | lem:von-neumann, lines 1431-1446 | Three Cauchy-Schwarz steps for the progression average on a compact abelian probability group
complete | 2026-10-10 13:54:24 ET | lem:von-neumann, line 1447 | Integer dilations preserve Haar probability on the torus; identification with the U3 norm
complete | 2026-10-10 14:30:12 ET | lem:von-neumann, lines 1427-1429 | Kernel Fourier expansion, characters to slots 0, 1, modulation invariance of norms
complete | 2026-10-10 14:30:12 ET | lem:von-neumann, line 1429 | Identification of the real progression form with the torus average without wraparound
complete | 2026-10-10 14:30:12 ET | lem:von-neumann, lines 1426, 1447 | L1 two-coordinate case and extension to L2 inputs by truncation
complete | 2026-10-10 14:30:12 ET | Declaration von-neumann, line 1449 | THT.LocalForm.vonNeumannOneL2 (Lean: vonNeumannOneL2, vonNeumann_local_L2, vonNeumann_local_L1)
complete | 2026-10-10 14:52:38 ET | lem:detection, lines 1465-1467 | Clipping of the three opponents and the clipped-form lower bound
complete | 2026-10-10 15:34:52 ET | lem:detection, lines 1469-1471 | Two successive decompositions and a bounded atom pair with a large form
complete | 2026-10-10 15:34:52 ET | lem:detection, line 1473 | Separation of the atom pair, shell truncation and the A_r lower bound
complete | 2026-10-10 15:17:46 ET | lem:detection, line 1473 | Kernel separation and extraction of a large normalized moment of R (separated_moment_extraction)
complete | 2026-10-10 15:34:52 ET | lem:detection, line 1473 | Quasipolynomial budget of the detection constant (detection_budget)
complete | 2026-10-10 15:34:52 ET | Declaration detection, line 1475 | THT.LocalForm.detectResidual (Lean: detectResidual)
complete | 2026-10-10 15:59:41 ET | lem:predictors, proof line 1531 | Single-scale square function for modulated mean-zero bumps on disjoint cells (cell_bump_square_function)
complete | 2026-10-10 17:17:34 ET | lem:predictors, proof lines 1539-1541 | Multi-scale Bessel bound from band multiplicity, lem:height, center separation
complete | 2026-10-10 17:17:34 ET | lem:predictors, proof lines 1521-1523 | L1 bound for time modifiers, depth energy, single-phase scale sums
complete | 2026-10-10 16:32:50 ET | lem:predictors, proof line 1529 | Mean-zero tensor decomposition of the kernel in (y_a, y_b)
complete | 2026-10-10 16:57:45 ET | lem:predictors, proof lines 1534-1542 | Linear-phase scale sum against admissible opponents, multiplicity M
complete | 2026-10-10 17:41:50 ET | lem:predictors, proof lines 1517-1542 | Core band scale sum: exceptional depths, clumps, replacement errors, tails
complete | 2026-10-10 18:28:58 ET | lem:predictors, lines 1489-1494 and proof lines 1517-1542 | eq:band-scale-sum for one separated chart time factor (band_scale_sum)
complete | 2026-10-10 19:35:00 ET | lem:predictors, proof line 1533 | Square-energy and fixed opponents are admissible with depth energy
complete | 2026-10-10 21:03:03 ET | lem:predictors, proof line 1532 | Current projection opponents are admissible via lem:compression
complete | 2026-10-10 19:35:00 ET | lem:predictors, proof line 1535 | Finite predictor list eq:predictors with explicit parameters
complete | 2026-10-10 19:35:00 ET | lem:predictors, line 1514 | Quasipolynomial budget log D_pred ≤ poly(1+B, log H) (qp_pdCard, qp_pdH0)
complete | 2026-10-10 19:35:00 ET | Declaration predictors, line 1536 | THT.Base.finitePredictorList (Lean: finitePredictorList)
complete | 2026-10-10 20:43:15 ET | lem:delay, lines 1549-1562 | eq:delay-telescope, chirp expansion and eq:delay-error for scalar delay data
complete | 2026-10-10 20:57:05 ET | lem:delay, lines 1549-1553 | Column partition projections with predictor label give the delay data
complete | 2026-10-10 20:57:05 ET | lem:delay, lines 1563-1565 | Rolling differences have square energy K₀²‖1_J F‖², hence admissible
complete | 2026-10-10 20:57:05 ET | Declaration delay, line 1566 | THT.Base.delayedPredictorReplacement (Lean: delayedPredictorReplacement)
complete | 2026-10-10 21:44:13 ET | adaptive-fit, lines 1572-1574 | Greedy insertion with detection oracle, energy gain ≥ ρ²|I|/4 per insertion
complete | 2026-10-10 21:44:13 ET | adaptive-fit, line 1574 | Nested fit ranges: energy telescoping, insertion mass ≤ 4ρ⁻²|J|
complete | 2026-10-10 21:44:13 ET | adaptive-fit, lines 1574-1575 | Stopped roots cost ≤ |J|/4, restarts with root length ≤ 4/3|J|, segments
complete | 2026-10-10 21:44:13 ET | adaptive-fit, line 1575 | Coefficient ℓ² ≤ 1, |g_I| ≤ √M, ‖g_I‖_(2,I) ≤ 1, bounded chart atoms
complete | 2026-10-10 21:44:13 ET | Declaration adaptive-fit, line 1579 | THT.Base.inheritedAdaptiveFit (Lean: inheritedAdaptiveFit)
complete | 2026-10-10 22:07:40 ET | stagger, lines 1589-1594 | eq:stagger pair replacement against supremum, then the L^q input
complete | 2026-10-10 22:07:40 ET | stagger, line 1596 | Index cases u < t-4 and u ≥ t-3: full pairs ≤ 8e^(-k_(t-7))
complete | 2026-10-10 22:07:40 ET | stagger, line 1587 | Grouping into eq:base-tuple, single-increment, four-residual terms; remainders
complete | 2026-10-10 22:07:40 ET | stagger, lines 1581, 1596 | Accuracy schedule k_(t+1) = k_t^A, cyclic adaptive fits, root-length bound
complete | 2026-10-10 22:07:40 ET | Declaration stagger, line 1598 | THT.Base.twoEarliestIncrements (Lean: twoEarliestIncrements)
complete | 2026-10-10 22:20:16 ET | prop:base, proof lines 1626-1631 (opponents) | Adaptive fits as ColumnDepthFamily per root; admissible opponents
complete | 2026-10-10 22:53:07 ET | prop:base, proof lines 1626-1631 | Low-pair predictor expansion grouped by joint birth cells
complete | 2026-10-11 04:33:37 ET | prop:base, proof lines 1626-1631 | High families, delayed replacement, base roots, stagger wrapper, baseParams
complete | 2026-10-11 04:33:37 ET | prop:base, proof lines 1634-1641 | Tuple-specific accurate high fits and pair control (AccSetup.accurateFit)
complete | 2026-10-11 02:47:00 ET | prop:base, proof line 1643 | Local sizes, eq:basic-side, the two-U term on one root
complete | 2026-10-11 00:46:07 ET | prop:base, proof lines 1645-1653 | eq:triple-tail: transpose and Cauchy-Schwarz, six-atom chart, scale count
complete | 2026-10-11 04:33:37 ET | prop:base, proof lines 1655-1660 | Active cells, path multiplicity, inactive error, eq:min-subadd reduction
complete | 2026-10-11 04:33:37 ET | Declaration base, line 1662 | THT.Base.activeCellReduction (Lean: activeCellReduction in SecBaseReductionBaseAssembly.lean; standard axioms)
complete | 2026-10-11 04:49:35 ET | lem:graph, lines 1680-1690 | Tags (ChartTag), edge relation tagEdge, slot multiplier invariance
complete | 2026-10-11 04:49:35 ET | lem:graph, proof line 1692 | Same-slot separation (graph_sameSlot_tag)
complete | 2026-10-11 05:07:11 ET | lem:graph, proof lines 1694-1702 | Distinct-slot separation via lem:separation (graph_distinctSlot_tag)
complete | 2026-10-11 05:44:30 ET | lem:graph, proof line 1704 | Short paths with endpoint splitting (tagEdge_path, shortPath_budget)
complete | 2026-10-11 05:44:30 ET | Declaration graph, line 1709 | THT.Localization.curvatureGraph (curvatureGraph; standard axioms)
complete | 2026-10-11 07:18:05 ET | coloring, lines 1714-1727 | Rounds, cohorts, profiles, context pseudometrics, balls, color data
complete | 2026-10-11 07:18:05 ET | coloring, lines 1728-1730 | Change counter and nonincreasing colors (potential_step, color_anti)
complete | 2026-10-11 07:18:05 ET | coloring, lines 1732-1734 | Choice of the delays: marking probability, union bound, delays_exist
complete | 2026-10-11 07:18:05 ET | Declaration coloring, line 1755 | THT.Localization.monotoneColoring (monotoneColoring)
complete | 2026-10-11 07:18:05 ET | lem:masks, lines 1760-1762 | Use ball, eq:rival-bound, neighbor closure, short path, persistence
complete | 2026-10-11 07:18:05 ET | lem:masks, lines 1767-1771 | Separation of distinct groups on overlapping endpoints (mask_separation)
complete | 2026-10-11 07:18:05 ET | Declaration masks, line 1774 | THT.Localization.historicalMaskSeparation (Lean: historicalMaskSeparation; standard axioms)
complete | 2026-10-11 07:43:32 ET | lem:whole-ranges, proof lines 1785-1788 | Analytic core wholeRanges_core: group outputs, pairings, Cauchy–Schwarz
complete | 2026-10-11 07:43:32 ET | lem:whole-ranges, proof line 1785 | Combined coefficients constant on last separating depth cells
complete | 2026-10-11 07:43:32 ET | Declaration whole-ranges, line 1791 | THT.Localization.usableRangeBessel (usableRangeBessel)
complete | 2026-10-11 08:45:32 ET | same-tag, line 1813 | One-term bound: plane change of variables, slot triple as convolution form, kernel Fourier expansion (slotTriple_form_le)
complete | 2026-10-11 08:45:32 ET | same-tag, lines 1800-1810 | Exact phase transfer and unit-piece decomposition (tag_transfer_pointwise)
complete | 2026-10-11 09:15:54 ET | same-tag, line 1810 | Periodized source expansion, quasipolynomial mass, form assembly (tag_single_term_le)
complete | 2026-10-11 09:16:02 ET | Declaration same-tag, line 1817 | THT.Localization.sameTagTemplateTest (sameTagTemplateTest, tagTemplate_column)
complete | 2026-10-11 09:25:17 ET | lem:closure, lines 1825-1829 | Trial count via eq:prefix with complements expanded (catalog_trial_count, catalog_rank_count)
complete | 2026-10-11 09:25:17 ET | lem:closure, lines 1829-1831 | Path counts n_r = exp(r k^C₂): caps not attained, log n_(L+5) ≤ k^O(1) (closure_parameters)
complete | 2026-10-11 09:25:17 ET | Declaration closure, line 1832 | THT.Localization.catalogClosure (catalogClosure)
complete | 2026-10-11 09:34:44 ET | prop:localize, lines 1841-1843 | Binary color search: exact split-tree expansion, L leaves, height O(log L) (SplitTree, colorSearch)
complete | 2026-10-11 09:34:44 ET | prop:localize, lines 1845-1852 | Leaf expansion: old sources, matching difference, pair separation, residual tests (leaf_localization)
complete | 2026-10-11 09:34:44 ET | prop:localize, line 1858 | Cell minima distributed over leaves via eq:min-subadd (cell_min_leaves)
complete | 2026-10-11 09:34:44 ET | Declaration localize, line 1856 | THT.Localization.binaryGroupExpansion (binaryGroupExpansion)
complete | 2026-10-11 09:41:08 ET | lem:variation, line 1867 | Joint Bessel across groups from eq:whole-ranges by duality (joint_bessel_of_wholeRanges)
complete | 2026-10-11 09:41:08 ET | lem:variation, lines 1870-1871 | Product jumps with compressed right factors (product_jumps_compression)
complete | 2026-10-11 09:41:08 ET | Declaration variation, line 1879 | THT.Localization.certifiedVariation (certifiedVariation)
complete | 2026-10-11 09:59:21 ET | first-match, line 1908 | eq:offset-mean for the periodic Gevrey branch cutoff (offsetMean)
complete | 2026-10-11 09:59:21 ET | first-match, lines 1913-1922 | eq:firstmatch, eq:mode-differences from tagEdge via chartfourier (splitPhase, firstMatchExpansion)
complete | 2026-10-11 09:59:21 ET | first-match, lines 1932-1940 | Pointwise lift to modes: exact synthesis, absolute norm bound (modeLift_synthesis, modeLift_norm_sq_le)
complete | 2026-10-11 09:59:21 ET | Declaration first-match, line 1936 | THT.Modes.firstMatchExpansionAndLift (firstMatchExpansionAndLift)
complete | 2026-10-11 10:13:41 ET | mode-schedule, line 1942 | eq:gauge-cancel with integer carries for four offsets (gauge_cancel, gaugeCarry_int)
complete | 2026-10-11 10:13:41 ET | mode-schedule, line 1966 | eq:slope-variation on frozen pre-cells (slope_variation)
complete | 2026-10-11 10:13:41 ET | Declaration mode-schedule, line 1976 | THT.Modes.chooseSchedule: eq:mode-parameters, polynomial logarithms (chooseSchedule)
complete | 2026-10-11 10:21:11 ET | Declaration tiny-space, line 2000 | Auto.exceptional_blocks_count, Auto.tiny_span_closed (FixedModes)
complete | 2026-10-11 10:30:16 ET | Declaration stabilize, line 2029 | Auto.height_stabilization, Auto.stable_heights_card (FixedModes; see ErrorReport)
complete | 2026-10-11 10:35:00 ET | Declaration coherence, line 2047 | Auto.ModeComponents.good_same_predecessor, core_good_iff, core_bad_proportion
complete | 2026-10-11 10:40:28 ET | Declaration mode-rows, line 2059 | Auto.separated_projection_rows, Auto.cell_cross_pair_le (FixedModes; see ErrorReport)
complete | 2026-10-11 10:48:10 ET | Declaration lift-composition, line 2077 | Auto.compose_lift_with_main_histories (FixedModes; see ErrorReport)
complete | 2026-10-11 10:48:10 ET | Declaration linear-side, line 2120 | Auto.linear_side_square_energy, chain_length_bound, sum_frac_le_log (see ErrorReport)
complete | 2026-10-11 10:51:29 ET | Declaration offset-selection, line 2157 | Auto.select_offsets_by_majorant, majorant_offset_mean (see ErrorReport)
complete | 2026-10-11 10:51:29 ET | Declaration side-caps, line 2166 | Auto.rolling_side_budget; cuts from DyadicStopping (see ErrorReport)
complete | 2026-10-11 10:51:29 ET | Declaration helpers, line 2169 | Auto.catalogClosure (universal helper part on fixed bases)
complete | 2026-10-11 10:54:28 ET | Declaration representatives, line 2194 | Auto.early_predecessor_nested, affine_separation_on_cell (see ErrorReport)
complete | 2026-10-11 10:54:28 ET | Declaration component-sizes, line 2210 | Auto.component_size_comparison (FixedModes)
complete | 2026-10-11 10:54:28 ET | Declaration tops, line 2231 | Auto.top_measure_absorb (FixedModes; see ErrorReport)
complete | 2026-10-11 10:57:42 ET | Declaration transfer, line 2265 | Auto.transfer_identity, Auto.transfer_near_bands (TwoSideEstimate; see ErrorReport)
complete | 2026-10-11 11:02:45 ET | Declaration shortblock, line 2369 | components only: fourth_moment_pairing, position_holder_sum; assembly open (ErrorReport)
complete | 2026-10-11 14:01:33 ET | lem:shortblock, lines 2290-2296 | Leaf-depth rectangles partition depth tuples (DepthRect.existsUnique_mem, uniq_disjoint)
complete | 2026-10-11 14:16:46 ET | lem:shortblock, lines 2298-2312 | δ-lattice decomposition; first kernel-sampling error per cell (latticeSampled_form_error)
complete | 2026-10-11 14:28:54 ET | lem:shortblock, lines 2302-2326 | Fast lift; U_(j,γ) invariance and eq:fourth-moment for finite Fourier sums
complete | 2026-10-11 14:31:58 ET | lem:shortblock, lines 2328-2332 | eq:window-mass, local bound, regular-slot bound ℓ + 2r_t (leaf_window_mass_le, window sums)
complete | 2026-10-11 15:35:41 ET | lem:shortblock, lines 2334-2340 | Per-cell deletion bound, exponents (1,3,3,3), Hölder in (γ,σ) (per_cell_deletion_bound)
complete | 2026-10-11 15:41:56 ET | lem:shortblock, lines 2340-2343 | Deletion summed over cells, depths, positions (deletion_sum_bound, deletion_threshold_cost)
complete | 2026-10-11 16:02:13 ET | lem:shortblock, lines 2345-2357 | Interval inputs, progression of centers, second sampling error, eq:CN (interval_form_identity)
complete | 2026-10-11 16:21:03 ET | lem:shortblock, lines 2357-2369 | Mixed Hölder, interval-input norms, window powers, block factor (mixed_holder_four, block_factor_bound)
complete | 2026-10-11 17:48:51 ET | lem:shortblock, lines 2302-2325 | Fast lift on T₀², L² fast form and S_N limit, maximalQ measurable (fast_lift_form, fast_form_tendsto)
complete | 2026-10-11 17:48:51 ET | lem:shortblock, lines 2307-2312 | Sampled form as lattice sum of fast forms; summed first sampling error (BlockData.total_eq, err1_bound)
complete | 2026-10-11 17:48:51 ET | lem:shortblock, lines 2314-2337 | Fatou over S_N, γ-invariance on T₀², heavy-slot split, window majorant (norm_latticeSum_le_windows)
complete | 2026-10-11 18:43:03 ET | lem:shortblock, lines 2334-2369 | Per-rectangle bound: deletion, interval comparison, eq:CN main term, second error (BlockData.rect_bound)
complete | 2026-10-11 19:43:38 ET | lem:shortblock, lines 2276-2369 | eq:shortblock: tree piece, leaf masks, level sums, normalization (short_block_comparison)
complete | 2026-10-11 11:05:57 ET | Declaration power-costs, line 2390 | components: three_sides_power, min_le_rpow_mul (see ErrorReport)
complete | 2026-10-11 11:05:57 ET | Declaration fixed-stacks, line 2423 | component: binary_prefix_expansion; eq:stack-energy open (ErrorReport)
complete | 2026-10-11 19:49:35 ET | fixed-stacks, lines 2400-2423 | eq:stack-energy: stack_energy_linear, stack_energy_rolling (Hilbert-space core)
complete | 2026-10-11 11:05:57 ET | Declaration side-estimate, line 2456 | component: hull_maxima_cauchy_schwarz; assembly open (ErrorReport)
complete | 2026-10-11 19:59:04 ET | side-estimate, lines 2425-2456 | Flags, Rademacher selection, sparse split, eq:near-band (near_band_total, sparse_two_stacks_volume_le)
complete | 2026-10-11 11:07:56 ET | Declaration common-height, line 2480 | components: first_success_weights_sum, all_good_proportion (see ErrorReport)
complete | 2026-10-11 11:07:56 ET | Declaration frequency-tests, line 2585 | component: schur_test; Fourier tests open (ErrorReport)
complete | 2026-10-11 20:17:35 ET | frequency-tests, lines 2482-2585 | eq:Haar-four, character averages, kernel decay, Hölder moments (haar_four, core_moment_bound)
complete | 2026-10-11 11:17:15 ET | Declaration sparse-count, line 2705 | components: minimal_growth_iteration, packing_card_le, count_balance_bound
complete | 2026-10-11 22:25:13 ET | lem:sparse-count, lines 2587-2705 | eq:sparse-count: four-step paths, covers, slab count, grid reduction (sparse_count)
complete | 2026-10-11 11:23:11 ET | Declaration tested-counts, line 2744 | components: pair_difference_eq_zero, total_count_le (see ErrorReport)
complete | 2026-10-11 22:27:54 ET | tested-counts, lines 2707-2744 | Pair determination, Parseval side incidence, eq:total-count (side_incidence_count)
complete | 2026-10-11 11:17:15 ET | Declaration distribution, line 2769 | Auto.distribution_power (exact statement; CoreTerms)
complete | 2026-10-11 11:17:15 ET | Declaration core-estimate, line 2822 | components: powered_count_exponents, amplitude_factor_le_one (ErrorReport)
complete | 2026-10-11 22:33:40 ET | core-estimate, lines 2771-2822 | Powered count, Hölder over groups, band sums, minimum step (powered_count, sum_prod_rpow_le)
complete | 2026-10-11 11:20:02 ET | Declaration normalized, line 2904 | components: exists_exponent_near_two, absorption_power_bound (ErrorReport)
complete | 2026-10-11 23:15:34 ET | prop:normalized row 1, lines 1675-1686 | Nested charts of active setups; tag graph refinement, symmetry; graph distances (DepthDistance.ofEdges)
complete | 2026-10-11 23:15:34 ET | prop:normalized row 1, lines 1677-1681 | Admission tree below a root: admission cells, positions, AdmTree (admTree)
complete | 2026-10-11 23:21:26 ET | prop:normalized row 1, lines 1677-1686 | Active-setup vertices, charts, normalized tags, tag graph and its distances (vtag, tagDist)
complete | 2026-10-11 23:46:19 ET | prop:normalized row 1, lines 1720-1734 | Colors on the admission tree: per-cell bound D = 4|L|+1, failed cells ≤ 100·2001⁷|R|/D (coloring)
complete | 2026-10-11 23:47:54 ET | prop:normalized row 1, lines 1712-1760 | Color parameters b₁, b₂ and historical mask properties for the attempt (colorParams, masks)
complete | 2026-10-12 00:31:50 ET | prop:normalized row 1, lines 1611-1613, 1859 | Basic args as differences of two current basic projections, root energy ≤ |R| (HasColumnRep)
complete | 2026-10-12 00:40:15 ET | prop:normalized row 1, lines 1820-1831 | Local catalog closure: valid insertion sequences, cap argument, maximal sequence passes all tests (local_closure)
complete | 2026-10-12 00:44:40 ET | prop:normalized row 1, lines 1805-1809, 1823-1825 | Catalog columns, rank/mask projections, nesting, fresh coordinates, insertion gain (catProj_gain)
complete | 2026-10-12 00:52:12 ET | prop:normalized row 1, lines 1809-1831 | Catalog tests at a cell, same-tag repair of failed tests, per-cell closure with rank counts (cell_closure)
complete | 2026-10-12 01:01:38 ET | prop:normalized row 1, lines 1820-1831 | Catalog over a finite tree: ancestors first, earlier tests preserved, per-cell rank counts (tree_closure)
complete | 2026-10-12 01:05:18 ET | prop:normalized row 1, lines 488-497, 1835 | Catalog outputs as column combinations with private-coordinate coefficient bounds (catRange_expansion)
complete | 2026-10-12 01:12:07 ET | prop:normalized row 1, lines 418-420, 1845 | Local form a.e.-invariant in each slot; multilinear cell form on augmented inputs (cellForm)
complete | 2026-10-12 01:17:53 ET | prop:normalized row 1, lines 1798-1803 | Inserted columns recorded as same-tag templates; templates are pure modulated charts (templateCol_chart)
complete | 2026-10-12 01:25:10 ET | prop:normalized row 1, lines 1804-1813 | Cumulative masks (monotone, neighbor closure, old/current split, depth growth); averaged histories as choice averages
complete | 2026-10-12 01:29:30 ET | prop:normalized row 1, lines 1809-1815, 1850-1852 | Form only sees the cell; a passing test bounds forms with a pure source and scaled spectators (CatTest.form_le)
complete | 2026-10-12 01:36:12 ET | prop:normalized row 1, lines 1841-1849 | Guarded binary color search: exact leaf expansion, guard invariants, leaves = colors (searchLeaves)
complete | 2026-10-12 01:46:24 ET | prop:normalized row 1, lines 1813, 1850-1852 | Averaged residual bound; leaf residuals as averages of single-choice test residuals (residual_layerOp_eq_avg)
complete | 2026-10-12 01:51:07 ET | prop:normalized row 1, lines 1835, 1850 | Averaged catalog filter outputs as column combinations of the largest mask with coefficients ≤ ‖X‖/√|I|
complete | 2026-10-12 01:53:38 ET | prop:normalized row 1, lines 1850-1852 | Spectator sizes ≤ ‖x‖/√|I|; pair separation bound for a source against separated columns (cellForm_pair_le)
complete | 2026-10-12 01:58:24 ET | prop:normalized row 1, lines 1850-1855 | Source combinations against averaged residuals (CatTest.form_combo_le); contractions of averaged filters and layers
complete | 2026-10-12 02:08:30 ET | prop:normalized row 1, lines 1850-1855 | Leaf filters; old-source, matching, separation and residual-insertion bounds at a leaf (LeafFilters.old_le, match_le, sep_le, res_le)
complete | 2026-10-12 02:12:28 ET | prop:normalized row 1, lines 1848-1856 | Leaf error of the localization from the catalog tests and separation (LeafFilters.leaf_error)
complete | 2026-10-12 02:15:19 ET | prop:normalized row 1, lines 1838-1856 | Cell sums of the localization over the leaves of the guarded search (search_cell_min)
complete | 2026-10-12 02:26:36 ET | prop:normalized row 1, lines 1835, 1850-1855 | ℓ² coefficient bounds (private recovery); separation and residual errors with √N; rank-split thresholds in leaf_error
complete | 2026-10-12 02:37:43 ET | prop:normalized row 1, lines 1677-1680 | Base inputs as cell L² classes; dimension padding of charts; vertex charts of dimension ≥ 1 (vchart_spec)
complete | 2026-10-12 02:40:25 ET | prop:normalized row 1, lines 1760-1762 | Attempt mask facts: pad monotonicity, current vertices in group masks, separation of distinct groups, no tag edges
complete | 2026-10-12 02:46:32 ET | prop:normalized row 1, lines 1804-1853 | Attempt parameters; cell masks, filters, current groups, named tests of each slot (AttemptParams.tests)
complete | 2026-10-12 02:51:11 ET | prop:normalized row 1, lines 1820-1831 | Attempt catalogs for the four slots passing all named tests (AttemptParams.catalogs_exist)
complete | 2026-10-12 02:59:25 ET | prop:normalized row 1, lines 1798-1803, 1850 | Leaf layer lengths; Pass monotone; present vertices available; vertex charts and templates as sources of common complexity (templateCol_source)
complete | 2026-10-12 03:03:18 ET | prop:normalized row 1, line 1798 | Mask vertices are present; selected catalog columns are pure sources of their tags (catColumn_source)
complete | 2026-10-12 03:10:19 ET | prop:normalized row 1, lines 1835, 1858 | Upper guard expansions: catalog case (upper_expansion) and basic case in vertex charts (basic_expansion, basic_source)
complete | 2026-10-12 03:16:00 ET | prop:normalized row 1, lines 1848-1851 | Complete-search leaves have one color in [1,L] (leafAt_facts); old/current classification of upper sources (classify)
complete | 2026-10-12 03:20:41 ET | prop:normalized row 1, lines 1851-1853 | Ball pads restricted to Fin P in leaf_error; template atoms are bounded charts; current groups pair-separated (sep_pair)
complete | 2026-10-12 03:27:53 ET | prop:normalized row 1, lines 1848-1856 | One leaf at one active cell from a bounded-chart expansion of the upper guard (AttemptParams.leaf_bound)
complete | 2026-10-12 03:32:48 ET | prop:normalized row 1, lines 1850, 1858 | Leaf bound with both upper-guard cases: catalog filter with l2 coefficients, basic slot in vertex charts (leaf_main)
complete | 2026-10-12 03:37:53 ET | prop:normalized row 1, lines 1838-1856 | Localized sum of an attempt over successful cells and all leaves, rank-wise leaf errors (localized_sum)
complete | 2026-10-12 03:45:34 ET | prop:normalized row 1, lines 1826-1831 | Label counts by birth and rank; thresholds τ_r from a count sequence give catalogs with ≤ n_r labels (catalogs_counted)
complete | 2026-10-12 03:48:31 ET | prop:normalized row 1, lines 1834-1836, 1855 | Leaf error O(G_c τ₃) from rank-wise cancellation; √n_r τ_(r+1) ≤ τ₃ under the closure ratio (leafErr_le, catTau_ratio)
complete | 2026-10-12 03:53:23 ET | prop:normalized row 1, lines 1820-1856 | Attempt localization with counted catalogs: error Σ|I|·#leaves·5(D+2)(S⁴+|L|D_c S³)τ₃ (attempt_localization)
complete | 2026-10-12 03:54:12 ET | prop:normalized, lines 2838-2840 | Attempt on an active setup: catalogs, colors, ball histories, leaf data (attempt_localization)
complete | 2026-10-12 04:15:05 ET | prop:normalized row 2, lines 1684, 1704, 1903 | Short tag paths; equal tags joined; ball-mask primaries tag-joined to the group center (mask_tagEdge_center)
complete | 2026-10-12 04:23:44 ET | prop:normalized row 2, lines 470-483, 1748, 1807 | Catalog projections as column-tree projections; attempt masks inherited in depth (catProj_eq_cellColumnProjection)
complete | 2026-10-12 04:41:28 ET | prop:normalized row 2, lines 1893-1922 | Branch-chart complexity; recentred first-match expansions on the first-match cell (firstMatch_attempt)
complete | 2026-10-12 04:57:24 ET | prop:normalized row 2, lines 1907, 1932-1940 | First-match truncation; global mode lift, ‖R‖ ≤ √5, exact synthesis after the match (LiftData.op)
complete | 2026-10-12 05:25:52 ET | prop:normalized row 2, lines 1891, 1913, 1924-1940 | First-match cells; counted finite expansions (box truncation); the mode lift R_(l,G) (attemptLift)
complete | 2026-10-12 05:39:43 ET | prop:normalized row 2, lines 1913-1922, 1980-1988 | Mode curvature and rational differences of the lift; PRE/CURRENT edges and components (preCurrent)
complete | 2026-10-12 05:52:57 ET | prop:normalized row 2, lines 1958, 2005-2012 | CURRENT paths sum their witnesses; bounded-denominator basis expansion (rational_span_expand_bounded)
complete | 2026-10-12 06:07:56 ET | prop:normalized row 2, lines 1995-2029 | Tiny span closure; stabilization core; good heights give direct PRE adjacency on a pre-cell (stabilize_pre); bad-height count (bad_heights_card)
complete | 2026-10-12 06:26:46 ET | prop:normalized row 2, lines 1893, 1913, 2031-2045 | Normalized vector Θ'=(θ_v,θ_z/Q₀); same-key differences; hstab from good primaries (hstab_of_primaryGood)
in progress | 2026-10-12 03:57:21 ET | prop:normalized, lines 2838-2840 | Attempt: first-match modes, offsets, linear sides, helpers instantiated
not started | 2026-10-11 13:57:00 ET | prop:normalized, lines 2840-2843 | Cuts, exceptional roots ≤ |R|/4, restarts, root packing 4|R|/3
not started | 2026-10-11 13:57:00 ET | prop:normalized, lines 2845-2848 | Cores, three sides and transfer decomposition of the active form
not started | 2026-10-11 13:57:00 ET | prop:normalized, lines 2850-2858 | eq:before-absorption for a retained attempt
not started | 2026-10-11 13:57:00 ET | prop:normalized, lines 2860-2890 | Choice of q, α, P; eq:active-final
not started | 2026-10-11 13:57:00 ET | prop:normalized, lines 2892-2900 | Summing the update levels
not started | 2026-10-11 13:57:00 ET | prop:normalized, lines 2902-2904 | Cutoff limit; eq:normalized (NormalizedAbsorption)
complete | 2026-10-11 11:20:02 ET | thm:uniform-local, lines 2926-2931 | Absorption C_N ≤ 2 + 2CA (uniform_constant_absorption)
complete | 2026-10-11 11:48:20 ET | thm:uniform-local, lines 2906-2908 | prop:normalized as a hypothesis (Auto.NormalizedAbsorption)
complete | 2026-10-11 12:01:34 ET | thm:uniform-local, lines 2910-2915 | Stopping generations, first stops of total length ≤ abs(J)/4 (stops_measure_le)
complete | 2026-10-11 12:01:34 ET | thm:uniform-local, lines 2916-2918 | Piece bound from prop:normalized after rescaling (piece_bound_of_normalized)
complete | 2026-10-11 12:01:34 ET | thm:uniform-local, lines 2919-2924 | Sparse sets E_J, sum abs(J) prod a ≤ (4/3) ∫ prod M_q f (stop_sparse_bound)
complete | 2026-10-11 12:01:34 ET | thm:uniform-local, line 2931 | C_N ≤ 2 + 2CA for all N, given prop:normalized (uniform_local_of_normalized)
complete | 2026-10-11 12:05:08 ET | thm:main, lines 2944-2950 | Kernel W = Π_j (∂_S - j∂_X) g has four zero marginals (fourMarginalKernel_marginal)
complete | 2026-10-11 12:11:17 ET | thm:main, lines 2951-2955 | Partition sum of W equals φ''''; eq:kernel-reconstruction (gevrey_fourMarginalKernel_partition_sum)
complete | 2026-10-11 12:11:12 ET | thm:main, lines 2963-2967 | Three nested lattices interlace; short intervals avoid two of them (interlacing_boundaries)
complete | 2026-10-11 12:13:58 ET | thm:main, line 2944 | W for ω(X)φ(S) = ωφ'''' - 6ω'φ''' + 11ω''φ'' - 6ω'''φ' (fourMarginalKernel_tensor)
complete | 2026-10-11 12:32:08 ET | thm:main, lines 2970-2974 | Rescaled W: derivative bound r^{-u}(C(u+2))^{C(u+2)} given Gevrey ω,φ (rescaledW_derivative_bound)
complete | 2026-10-11 12:48:27 ET | thm:main, lines 2966-2970 | Rescaled translates admissible in a margin-r/24 lattice cell (rescaledW_admissible)
complete | 2026-10-11 12:51:14 ET | thm:main, lines 2962-2965 | The three lattices r_s(ℤ + (-1)^s j/3) as nested dyadic grids (interlacedGrid)
complete | 2026-10-11 12:51:14 ET | thm:main, lines 2968-2969 | A cell receives at most D + 1 translates (card_int_le_of_interval)
complete | 2026-10-11 12:58:35 ET | thm:main, lines 2971-2976 | Scale-truncated form ≤ 3(D+1) C_N ∫ Π M_q f for each b (truncated_scale_sum_bound)
complete | 2026-10-11 13:02:45 ET | thm:main, lines 2976-2980 | ∫ Π M_q f ≤ B Π C‖f_j‖_3 by Hölder and the maximal theorem (maximal_product_bound)
complete | 2026-10-11 13:34:22 ET | thm:main, lines 2982-2995 | Scale limit to φ'''(0)·∫ f₀ p.v.; uniform bound (scale_fubini, integrated_scale_form_bound, pv_form_bound)
complete | 2026-10-11 13:39:56 ET | thm:main, lines 2996-2999 | L1 bound by duality, thtPV bounded measurable (lintegral_enorm_le_of_duality, thtPV_lintegral_le)
complete | 2026-10-11 13:53:48 ET | thm:main, lines 2934-2947 | ω, φ = S³χ chosen; L1 operator, L3 extension given uniform-local (tht_main_of_uniform)
complete | 2026-10-11 13:53:48 ET | thm:main, line 2931 | uniform-local for every class from prop:normalized (uniform_of_normalized)
