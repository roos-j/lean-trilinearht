# Main theorem overview

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-16 11:36:19 ET | thm:main, lines 2934-2939 | Uniform L1 bound, unconditional: tht_main (tht_main_of_activeFinal activeFinal_holds)
complete | 2026-10-11 11:29:42 ET | thm:main, line 2940, proof 2985-2990 | Pointwise principal value on Schwartz inputs (thtTruncated_tendsto_thtPV)
complete | 2026-10-11 11:35:58 ET | thm:main, line 2940, proof 2999-3008 | Unique bounded L3 extension given the bound (schwartz_L3_unique_extension)

# Quantitative Gevrey cutoff prerequisite

The Fourier localization needs compact cutoffs and a locally finite integer partition with uniform all-orders Gevrey bounds. Pinned Mathlib supplies smooth expNegInvGlue and smooth
transitions but no quantitative Gevrey derivative or partition theorem; the repository's already-proved construction supplies this substantial classical calculus prerequisite. Move
that entire independent development, without duplicating or changing its proofs, into TrilinearHT/Auto/GevreyCutoffs.lean. Its general interval, affine-rescaling and finite-product
statements use only Mathlib and local definitions. This is the reusable-prerequisite exception, not a machine-blueprint section split. Verified references: blueprint lem:gevrey,
lines 107–126, and Mathlib.Analysis.SpecialFunctions.SmoothTransition. Recorded before module creation at 2026-10-09 09:58:48 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-08 22:14:53 ET | lem:gevrey, lines 110–114 | Quantitative derivative bounds for expNegInvGlue
complete | 2026-10-08 22:24:10 ET | lem:gevrey, lines 116–117 | Normalized compact bump and interval cutoffs
complete | 2026-10-08 22:24:10 ET | lem:gevrey, lines 117–125 | Locally finite partition of unity
complete | 2026-10-08 22:24:10 ET | lem:gevrey, line 126 | Rescaling and multidimensional products

# Quantitative Fourier approximation prerequisite

The chart development and later Fourier splitting use the general derivative-to-Fourier-decay, absolute convergence and quantitative uniform truncation theorem on
finite-dimensional tori. Pinned Mathlib has Fourier completeness and summability interfaces, but searches found no matching explicit derivative-order, dimension and tail estimate.
This is a substantial classical Fourier-analysis prerequisite. Move the entire already-proved 702-line independent development, without changing its mathematics, into
TrilinearHT/Auto/FourierApproximation.lean. A declaration-reference scan found no external project dependencies; its statements and local definitions use only Mathlib. This invokes
the reusable-prerequisite exception, not a source-section split. Verified references: blueprint lem:fourier-foundation, lines 130-146, and Mathlib.Analysis.Fourier.AddCircleMulti.
Preserve the existing attribution to ../lean-dfr. Recorded before creation at 2026-10-09 13:27:14 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-08 22:44:53 ET | lem:fourier-foundation, lines 130–146 | Coordinate Fourier coefficient decay
complete | 2026-10-08 22:44:53 ET | lem:fourier-foundation, lines 134–146 | Nonzero shell counting, tails, and uniform convergence
complete | 2026-10-09 13:30:19 ET | lem:fourier-foundation, lines 130-146 | Independent Fourier approximation module verification

# Balog-Szemeredi-Gowers prerequisite

The finite inverse argument needs the classical Balog-Szemeredi-Gowers energy-to-small-difference theorem and its dense bipartite four-path prerequisite. Pinned Mathlib supplies
Finset.addEnergy and basic finite inequalities, but direct searches found no quantitative BSG or dependent-random-choice four-path theorem; searches of ../lean-spherical,
../lean-dfr and ../lean-variationalsw found no adequate replacement. This substantial textbook additive-combinatorics theorem qualifies for the reusable-prerequisite exception.
Develop exactly one independent module, TrilinearHT/Auto/BalogSzemerediGowers.lean, with general finite bipartite relations and finite subsets of arbitrary abelian groups. Its
statements and supporting definitions use only Mathlib and that module, including Mathlib additive energy. Verified reference: blueprint lem:four-paths, lines 668-680, and lem:BSG,
lines 683-698. Recorded before module creation at 2026-10-09 14:47:46 ET.

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

The finite inverse theorem and dense Bogolyubov argument need Chang's quantitative spectrum-generating theorem and the Bohr-set cardinality estimate. Pinned Mathlib has
AddDissociated, maximal dissociated span, and AddDissociated.randomisation (the Riesz-product mean identity), but direct searches found no quantitative spectrum cardinality bound
or Bohr-set pigeonhole estimate; searches of ../lean-spherical, ../lean-dfr and ../lean-variationalsw found no replacement. This is a substantial classical finite harmonic-analysis
theorem. Create exactly one independent module, TrilinearHT/Auto/ChangSpectrum.lean, using only Mathlib and local definitions for finite abelian groups, additive characters, and
circle-valued homomorphisms. Reuse the existing randomisation and dissociation proofs. The source cyclic statement will be connected to the project's normalized Fourier transform
in the main file. This is the reusable-prerequisite exception, not a blueprint-section split. Verified reference: blueprint lem:Chang, lines 730-764. Recorded before creation at
2026-10-09 15:25:46 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 15:30:40 ET | lem:Chang, lines 735-748 | Circle partition and large Bohr-set fiber
complete | 2026-10-09 15:34:22 ET | lem:Chang, lines 749-757 | Phase alignment and positive Riesz-product mean
complete | 2026-10-09 15:42:35 ET | lem:Chang, lines 758-763 | Logarithmic lower bound and Jensen cardinality estimate
complete | 2026-10-09 15:49:08 ET | lem:Chang, lines 739-764 | Spectrum generation, cyclic Fourier bridge and full-density case

# Khintchine and empirical sampling prerequisite

The later almost-period and signed-stack arguments need the general Khintchine upper inequality and its empirical-sampling consequence. Searches of pinned Mathlib Probability and
Analysis found no Khintchine or symmetrization/sampling moment theorem; the repository already contains a complete proof adapted from ../lean-variationalsw. Extract that
substantial textbook probability prerequisite, unchanged, into TrilinearHT/Auto/KhintchineSampling.lean. Include all sign, independent-copy, finite-mean, finite-Lp and convolution
definitions it uses. A declaration-reference scan found only finiteAverage and finiteConvolution as outside dependencies; move those definitions too, so all statements depend only
on Mathlib and local definitions. This invokes the reusable-prerequisite exception, not a blueprint section split. Extend this same independent empirical-sampling module with the
Croot-Sisask almost-period consequence, blueprint lem:almostperiods, lines 766-784, using its existing probability norms and sampling theorem. No additional module is needed.
Verified reference: blueprint lem:finite-fourier, lines 177-209; preserve sibling attribution. Recorded before creation at 2026-10-09 13:58:52 ET. Consolidation recorded at
2026-10-09 21:22:18 ET: move the already-proved finite Fourier foundations from main into this module, beside their local finiteAverage, finiteConvolution and uniformMean
primitives (the finite-inverse trilinear selection, lines 1148-1157, is in Sec07FiniteInverse). The unchanged foundation statements depend only on Mathlib and this module.

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

The finite inverse argument needs the classical quasipolynomial dense Bogolyubov theorem: for every nonempty subset A of a finite cyclic group, 2A-2A contains a Bohr set with rank
O(log^4(1/alpha)), reciprocal radius O(alpha^(-1) log^4(1/alpha)), and density exp(-O(log^5(1/alpha))). Searches of pinned Mathlib additive combinatorics/Fourier and
../lean-spherical, ../lean-dfr and ../lean-variationalsw found no such theorem. This substantial named theorem qualifies for the reusable-prerequisite exception. Create exactly one
module, TrilinearHT/Auto/DenseBogolyubov.lean, general over all positive cyclic moduli and arbitrary finite subsets. Its theorem statements and local definitions use Mathlib/local
vocabulary; proofs may reuse the already-verified KhintchineSampling and ChangSpectrum modules, as explicitly permitted by the skill. Do not import the main proof module or create
a cycle. The main module has 9489 lines, but mathematical substance, not file length, justifies this split. Verified reference: blueprint lem:dense-Bohr, lines 786-820. Recorded
before creation at 2026-10-09 16:10:28 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 16:16:13 ET | lem:dense-Bohr, lines 794-795 | Positive convolution witness, value at zero and difference-set support
complete | 2026-10-09 16:23:23 ET | lem:dense-Bohr, lines 796-805 | Sampling parameters and convolution amplification of almost periods
complete | 2026-10-09 16:30:47 ET | lem:dense-Bohr, lines 806-812 | Iterated averaging measure and Fourier multiplier
complete | 2026-10-09 16:39:28 ET | lem:dense-Bohr, lines 813-817 | Spectrum split and uniform Fourier translation estimate
complete | 2026-10-09 16:47:09 ET | lem:dense-Bohr, lines 786-820 | Quasipolynomial rank, radius, containment and density


# Hilbert-space atomic decomposition prerequisite

The decomposition in lem:inverse, lines 1218-1239, requires a substantial general Hilbert-space separation theorem for finite atomic sums and two seminorm balls, together with
probability-L2 dual bounds. Mathlib supplies Hahn--Banach, Riesz representation and convex hulls but no matching quantitative atomic decomposition theorem; the sibling
lean-spherical convex-duality module concerns scalar convex functions. Develop TrilinearHT/Auto/HilbertAtomicDecomposition.lean under the reusable-prerequisite exception, using
only Mathlib and definitions local to that module in its statements. The general result will take an independently stated inverse-correlation hypothesis; the main file must
discharge it using continuous_inverse. This is not a split along machine-blueprint sections. Recorded before creation at 2026-10-10 00:38:41 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-10 00:48:24 ET | lem:inverse proof, lines 1218-1237 | Separation of atomic hull and two seminorm balls; three dual bounds (probabilityL2_atomic_separation)
complete | 2026-10-10 01:01:37 ET | lem:inverse proof, line 1239 | Closure and finite atomic decomposition (probabilityL2_atomic_decomposition)

# Gowers–Cauchy–Schwarz and cube continuity prerequisite

The mixed cube estimates used by lem:cube-foundation and later local von Neumann arguments require the classical Gowers–Cauchy–Schwarz inequality, its U3 seminorm, and eight-input
L2 continuity. A search of pinned Mathlib found no Gowers development; Haar integration and Holder provide only its ingredients. Move the already-proved general Haar-probability
construction and its supporting cube definitions, without duplication, into TrilinearHT/Auto/GowersCauchySchwarz.lean. The inspected statements use only Mathlib and local
definitions, and a declaration-dependency scan found no remaining main-file dependencies. This substantial general additive-combinatorial theorem qualifies for the
reusable-prerequisite exception; it is not a machine-blueprint section split. Verified source: blueprint cube-definition, lines 162–175, and lem:cube-foundation, lines 216–237.
Recorded before creation at 2026-10-09 10:55:13 ET. Extension recorded at 2026-10-09 21:49:19 ET: the continuous inverse requires finite-to-continuous convergence of cell-averaged
cube integrals (lines 1183-1189). Searches of pinned Mathlib and sibling repositories found no ready Gowers discretization theorem. Develop the general cube discretization in this
existing module, using Mathlib integration and approximation. Move the normalized finite Haar definition and its two basic instances from main here so all new statements use
Mathlib/local definitions; retain source-specific chart applications in main.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-08 23:24:00 ET | cube-definition, lines 162–175 | Mixed cubes, squared-face identity, positivity and nonnegative roots
complete | 2026-10-08 23:55:00 ET | lem:cube-foundation, lines 216–231 | Coordinate reflection Cauchy–Schwarz and mixed cube bound
complete | 2026-10-09 00:00:00 ET | lem:cube-foundation, lines 218–232 | Homogeneity, triangle inequality, and bundled U3 seminorm
complete | 2026-10-09 00:15:00 ET | eq:cube-L2, lines 223–237 | Independent vertex halves and eight L2 bounds
complete | 2026-10-09 00:24:23 ET | lem:cube-foundation, lines 227–237 | Continuous extension to eight L2 inputs

# Fefferman–Stein maximal inequality prerequisite

The mixed maximal estimate in lem:vector-maximal needs the general vector Hardy–Littlewood theorem, absent from pinned Mathlib; the textbook Fefferman–Stein theorem is a
substantial reusable prerequisite, developed for general exponents and finite inner measure spaces in TrilinearHT/Auto/FeffermanStein.lean, adapting the finite Hilbert-family proof
in ../lean-variationalsw.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-09 00:27:15 ET | ../lean-variationalsw/VariationalSW/Auto/MarcinkiewiczInterpolation.lean, lines 692–914 | Weak-type interpolation and scalar maximal foundations
complete | 2026-10-09 00:30:18 ET | ../lean-variationalsw/VariationalSW/Auto/FeffermanSteinInequality.lean, lines 829–953 | Weighted maximal inequality, exponents above one
complete | 2026-10-09 00:36:18 ET | ../lean-variationalsw/VariationalSW/Auto/FeffermanSteinInequality.lean, lines 955–1114 | Mixed norm duality, outer exponent above inner
complete | 2026-10-09 00:41:08 ET | lem:vector-maximal, lines 248–250, permitted vector maximal theorem | Mixed Hölder and dual testing
complete | 2026-10-09 00:48:15 ET | lem:vector-maximal, lines 248–250, permitted vector maximal theorem | Remaining exponent range and truncation on finite inner measure spaces

# Lattice transference principle prerequisite

The successive-minima transference principle is needed by lem:transference and lem:lattice-box; pinned Mathlib supplies dual lattices and Minkowski's first theorem but no adequate
successive-minima product bound. This is a substantial classical geometry-of-numbers theorem, here for arbitrary finite-dimensional real inner-product spaces, full lattices and
compact symmetric convex bodies, with constants independent of the lattice and body. Its statement and all supporting definitions depend only on Mathlib and the dedicated
TrilinearHT/Auto/LatticeTransference.lean. The already-proved integer-basis, reduced-basis and transference development is moved together before the main file reaches its
10000-line limit; the coefficient-box application is in Sec02. Verified references are blueprint lem:integer-basis, lem:reduced-basis and lem:transference, and pinned
Mathlib.MeasureTheory.Group.GeometryOfNumbers and Mathlib.LinearAlgebra.BilinearForm.DualLattice.

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

The rational height bounds needed throughout the finite coefficient constructions are absent from pinned Mathlib: its rational heights, determinants and projections do not provide
the required uniform counting, inverse, pivot right-inverse and projection estimates. Effective rational linear algebra via common denominators and Cramer's rule is a substantial
reusable development, including real scalar extension and operator norms. The complete development moves together to TrilinearHT/Auto/RationalLinearAlgebra.lean; all statements and
local definitions depend only on Mathlib. This invokes the reusable-prerequisite exception, not a split along machine-generated blueprint sections. Verified references are
blueprint lem:rational-linear, lines 416–420, and the pinned Mathlib rational, matrix adjugate, rank and orthogonal-projection developments. The independently reusable height-bin
theorem (lem:height, lines 603–619) extends this same module using its local rationalHeight and sharp denominator/minor bounds; no project-specific operator data enter its
statements.

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

The fixed-function hull cuts in lem:cuts need a general finite dyadic stopping theorem absent from pinned Mathlib; finite integration, Markov and layer-cake results supply its
classical ingredients. The complete grid, path packing and first-crossing development in TrilinearHT/Auto/DyadicStopping.lean is independently stated for arbitrary real dyadic
grids, finite families and normed-space-valued L2 functions, using only Mathlib and its own definitions. Its dedicated module is justified before creation at 2026-10-09 06:18:23 ET
and serves later root-normalized attempts as well as path-packing and lem:cuts.

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

Justification: the dyadic-prefix row estimate and noncommuting nested-product consequences needed by lem:prefix (lines 508–535) are absent from pinned Mathlib and searched sibling
repositories. The classical Rademacher–Menshov dyadic decomposition is a substantial general Hilbert-space theorem (Tao, 247A Lecture Notes 2, page 31, Q14–Q15); one independent
Mathlib-only module, TrilinearHT/Auto/RademacherMenshov.lean, will contain the finite row version, nested projections and disjoint-interval jumps, with no project-specific column
data. Recorded before creation at 2026-10-09 07:32:32 ET.

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

Justification: lem:shortblock (lines 2328-2340: "Minkowski and the sign moments give (E‖F^σ(n,·)‖_2^a)^(1/a) ≤ C_a e_j(n)", and the deletion bound) needs Minkowski's integral
inequality (L^p norm of an integral at most the integral of L^p norms). Searches of pinned Mathlib (MeasureTheory/Integral/MeanInequalities: only the two-function Minkowski
inequality) and the repository found no integral version. It is a named textbook theorem (Stein, Singular Integrals, Appendix A.1; Hardy–Littlewood–Pólya, Inequalities, Thm 202).
Stated for ℝ≥0∞-valued jointly measurable f, σ-finite μ, s-finite ν, p ≥ 1, depending only on Mathlib, in TrilinearHT/Auto/MinkowskiIntegralInequality.lean. Recorded before
creation at 2026-10-11 14:44:15 ET.

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-11 14:47:28 ET | lem:shortblock, line 2330 | Minkowski integral inequality via Hölder duality and truncation (lintegral_minkowski)

# Main proof ledger

Rebuilt from scratch at 2026-10-14 03:49:26 ET by a line-by-line audit of the blueprint against the Lean code (user directive 2026-10-14 03:21 ET).
A row is complete only when the claim at those lines is proved in Lean for the objects the blueprint uses, with no hypothesis beyond
earlier blueprint results that the step itself invokes. Rows tagged with a prerequisite module are tracked in detail in its section above.
Timestamps of this ledger are the audit time, not the original proof times. Gaps of in-progress rows are detailed in ErrorReport.md.

## sec:foundations, lines 53-253

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 03:49:26 ET | lines 58-60 | Pinned Mathlib revision and toolchain (lakefile.toml, lake-manifest.json, lean-toolchain)
complete | 2026-10-14 03:49:26 ET | lines 67-72 | Permitted vector maximal theorem, proved in-house (prerequisite FeffermanStein); uncentered M <= 2 centered M
complete | 2026-10-14 03:49:26 ET | lines 75-80 | Local normalized norms with ess sup at p = infinity (normalizedIntervalMeasure)
complete | 2026-10-14 03:49:26 ET | lem:budget-rules, line 83 | Quasipolynomial bounds closed under sums, products, fixed powers, compositions (QuasipolynomialBound_*)
complete | 2026-10-14 03:49:26 ET | lem:budget-rules, line 83 | Polynomial-in-log bounds closed with explicit degrees (polynomial_majorant_add/_mul/_comp)
complete | 2026-10-14 03:55:13 ET | lem:budget-rules, line 83 | q-uniform clause: degree-indexed closure, output degree depends only on input degrees (QuasipolynomialBoundOfDegree)
complete | 2026-10-14 04:20:05 ET | lem:budget-rules, lines 85-98 | Overhead bound F <= exp(K(1+log 2k)^2), K from A, B, C, d (compression_overhead_bound)
complete | 2026-10-14 04:20:05 ET | lem:budget-rules, lines 89, 99 | Quasipolynomial overheads and every real power k^p eventually below every power P^eps
complete | 2026-10-14 03:49:26 ET | lem:gevrey, lines 107-126 | Gevrey glue derivatives, cutoffs, partition, rescaling, products (prerequisite GevreyCutoffs)
complete | 2026-10-14 03:49:26 ET | lem:fourier-foundation, lines 130-146 | Decay, nonzero shells (n=0 excluded: source error), tails (prerequisite FourierApproximation)
complete | 2026-10-14 03:49:26 ET | lem:fourier-foundation, lines 136-158 | Separated frequencies, Schur test, multipliers, duality, quadratic oscillatory integral
complete | 2026-10-14 03:49:26 ET | cube forms, lines 163-174 | Cube forms, diagonal identity, U^j norms, finite expectation and convolution
complete | 2026-10-14 03:49:26 ET | lem:finite-fourier, lines 178-212 | Khintchine, double signs, sampling (prerequisite KhintchineSampling); Z/qZ, U2 and U3 identities
complete | 2026-10-14 03:49:26 ET | lem:cube-foundation, lines 216-236 | U3 seminorm, Gowers-Cauchy-Schwarz, eq:cube-L2, L2 extension (prerequisite GowersCauchySchwarz)
complete | 2026-10-14 03:49:26 ET | lem:vector-maximal, lines 240-250 | Mixed maximal bound for 2<q<3, p>q on finite inner measure spaces (oneMixedNorm)

## sec:lattices, lines 254-362

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 03:49:26 ET | lem:integer-basis, lines 255-263 | Primitive vectors, saturated subgroups, rational intersections (prerequisite LatticeTransference)
complete | 2026-10-14 03:49:26 ET | lem:reduced-basis, lines 268-292 | Reduced basis with adjacent, primal and dual bounds (prerequisite LatticeTransference)
complete | 2026-10-14 03:49:26 ET | lem:transference, lines 296-314 | Successive minima products between 1 and (100d)^(10d) (prerequisite LatticeTransference)
complete | 2026-10-14 03:49:26 ET | lem:lattice-box, lines 318-344 | Small lattice vectors in a coefficient box inside B(0,1/4) (smallBallCoefficientBox)
complete | 2026-10-14 03:49:26 ET | lem:torus-annihilator, lines 347-358 | Annihilator torus, character integral, Haar-preserving progression map

## sec:reduction, lines 363-468

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 03:49:26 ET | line 364 | Real dyadic grids and finite trees (prerequisite DyadicStopping)
complete | 2026-10-14 03:49:26 ET | eq:local, eq:marginals, lines 366-376 | Local progression forms and admissible kernels with four zero marginals
complete | 2026-10-14 03:49:26 ET | lem:absolute, lines 380-394 | eq:absolute on the line, on connected tori and on Z; exponent polytope
complete | 2026-10-14 03:49:26 ET | eq:CN, lem:finite-CN, lines 398-410 | C_N(q) defined; 1 <= C_N <= 1+CN, attained and least (finiteDepthConstant_finite)
complete | 2026-10-14 03:49:26 ET | lem:rational-linear, lines 416-420 | Heights, inverses, right inverses, projections, bases (prerequisite RationalLinearAlgebra)
complete | 2026-10-14 03:49:26 ET | eq:path, lines 425-429 | Path identity, restart packing, combined stop rules (prerequisite DyadicStopping)
complete | 2026-10-14 03:49:26 ET | lem:cuts, lines 433-465 | First crossings, hull distribution, log integral, eq:hull-cap (prerequisite DyadicStopping)

## sec:columns, lines 469-623

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 03:49:26 ET | lines 470-484 | Column data, eq:columnbudget, inherited masks, nested projections, row interface
complete | 2026-10-14 03:49:26 ET | lem:coeff, lines 487-503 | Two-sided coefficient bounds, sup bound D^5, eq:predictor-moment
complete | 2026-10-14 03:49:26 ET | lem:prefix, lines 509-533 | eq:prefix, eq:product-jump, disjoint intervals (prerequisite RademacherMenshov)
complete | 2026-10-14 03:49:26 ET | lem:compression, lines 539-550 | eq:compression with C=512, complements and averages (columnSpatialCompression)
complete | 2026-10-14 03:49:26 ET | lem:compression proof, lines 553-597 | Stopping, moment representatives, anchors, restarts, error rows, summation
complete | 2026-10-14 03:49:26 ET | lem:height, lines 603-617 | Log intervals, bins, scale counts, eq:tiny-sum (prerequisite RationalLinearAlgebra)

## sec:chart-definitions, lines 624-663

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 03:49:26 ET | def:chart, lines 626-637 | Quadratic charts, complexity, bounded atoms and remarks (Sec05QuadraticCharts)
complete | 2026-10-14 03:49:26 ET | lem:chart-operations, lines 642-651 | Conjugation, finite products, affine changes of one variable (Sec05QuadraticCharts)
complete | 2026-10-14 05:58:38 ET | lem:chart-operations, line 651 | Affine substitutions of several-variable charts (multivariableQuadraticChart_affine_closure)
complete | 2026-10-14 03:49:26 ET | several-variable charts, lines 656-660 | Q(z), symmetric and skew parts, A = C - C^T

## sec:additive, lines 664-928

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 03:49:26 ET | lem:four-paths, lem:BSG, lines 668-697 | Dense four paths and Balog-Szemeredi-Gowers (prerequisite BalogSzemerediGowers)
complete | 2026-10-14 03:49:26 ET | lem:sumset-growth, lines 702-726 | |mA-nA| <= K^(m+n)|A| and Ruzsa triangle (finite_difference_growth)
complete | 2026-10-14 03:49:26 ET | lem:Chang, lines 730-762 | Bohr sets, cardinality, spectrum generation (prerequisite ChangSpectrum)
complete | 2026-10-14 03:49:26 ET | lem:almostperiods, lines 767-782 | Croot-Sisask almost periods (prerequisite KhintchineSampling)
complete | 2026-10-14 03:49:26 ET | lem:dense-Bohr, lines 787-819 | Dense Bogolyubov theorem (prerequisite DenseBogolyubov)
complete | 2026-10-14 03:49:26 ET | lem:derivative-graph, lines 823-861 | Derivative frequency selection and graph energy (derivative_graph_energy)
complete | 2026-10-14 03:49:26 ET | lem:local-frequency, lines 866-891 | Locally additive derivative frequency (locally_additive_derivative_frequency)
complete | 2026-10-14 03:49:26 ET | lem:Bohr-weight, lines 896-925 | Smooth Bohr weight: mass, translation, Fourier decay (smooth_bohr_weight)

## sec:finite-inverse, lines 929-1163

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 03:49:26 ET | lem:local-symmetry, lines 932-1015 | Local symmetry of the derivative frequency (local_symmetry)
complete | 2026-10-14 03:49:26 ET | lem:local-chart, lines 1019-1084 | Locally quadratic chart on a Bohr set (locally_quadratic_chart)
complete | 2026-10-14 03:49:26 ET | thm:finite-inverse, lines 1088-1159 | Finite U3 inverse theorem for every odd q (finite_inverse)

## sec:continuous, lines 1164-1243

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 03:49:26 ET | lines 1164-1170 | Interval Gowers norm U(I) on T16 and its L2 seminorm bound (intervalGowersNorm)
complete | 2026-10-14 03:49:26 ET | lem:inverse, lines 1172-1216 | Continuous inverse with bounded atoms (continuous_inverse)
complete | 2026-10-14 03:49:26 ET | lem:inverse, lines 1173-1239 | eq:decomp bounded atomic decomposition (continuous_decomposition; prerequisite HilbertAtomicDecomposition)

## sec:charts, lines 1244-1417

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 03:49:26 ET | lem:return-splitting, lines 1245-1300 | Isotropic rational return splitting (shortReturnSplitting)
complete | 2026-10-14 03:49:26 ET | lem:weyl, lines 1304-1333 | eq:weyl-splitting and eq:effective (weylSplitting)
complete | 2026-10-14 03:49:26 ET | lem:chartfourier, lines 1338-1377 | Chart Fourier expansion, envelope and shells for one splitting (splitFourierExpansion)
complete | 2026-10-14 06:20:38 ET | lem:chartfourier, lines 1349, 1377 | Envelope pooled over all splittings of height <= B, shells and tail (splitFourierExpansion_pooled)
complete | 2026-10-14 03:49:26 ET | lem:chartfourier, line 1349 | Uniform tail needs only quasipolynomial truncation (pooled_shell_tail_bound)
complete | 2026-10-14 06:42:24 ET | lem:separation, lines 1382-1388 | eq:separation for charts of every dimension, padding d = 0 (progressionSeparation_all)
complete | 2026-10-14 03:49:26 ET | lem:separation, lines 1390-1411 | Separated form norm, kernel approximation, eq:separated-phase and proof steps

## sec:detection, lines 1418-1479

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 07:02:47 ET | lem:von-neumann, lines 1419-1447 | Local von Neumann bound with b, c in L^inf(I) (vonNeumann_essSup) and the L1 form (vonNeumannOneL2)
complete | 2026-10-14 03:49:26 ET | lem:detection, lines 1451-1473 | A large local form gives a bounded-atom moment of the residual (detectResidual)

## sec:base, lines 1480-1666

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 03:49:26 ET | lines 1482-1486 | Fixed, current-projection and square-energy opponents are admissible
complete | 2026-10-14 03:49:26 ET | lem:predictors, lines 1489-1534 | eq:band-scale-sum, vanishing, finite predictor list eq:predictors (finitePredictorList)
complete | 2026-10-14 03:49:26 ET | lem:delay, lines 1539-1564 | eq:delay-error and delayed admissible opponents (delayedPredictorReplacement)
complete | 2026-10-14 03:49:26 ET | lines 1570-1579 | d_(j,I) and inherited adaptive fits eq:adaptive (inheritedAdaptiveFit)
complete | 2026-10-14 03:49:26 ET | lines 1581-1596 | Stagger schedule, eq:base-tuple expansion, eq:stagger, pair bounds (twoEarliestIncrements)
complete | 2026-10-14 08:55:24 ET | prop:base, lines 1600-1607 | eq:Y error e^-k |R| (baseTuple, baseBottom); basic projections: budgets, charts <= H, inverse weights exp(k^Cb)
complete | 2026-10-14 03:49:26 ET | prop:base, lines 1607-1616 | Sizes <= 2, pair smallness, Y = B + U, eq:basic-side on sub-roots (activeCellReduction)
complete | 2026-10-14 03:49:26 ET | prop:base, lines 1618-1623 | eq:active-min reduction with path multiplicity (ActiveSetup.reduction, active_count)
complete | 2026-10-14 03:49:26 ET | prop:base proof, lines 1626-1660 | Low pairs, accurate high fits, sizes, eq:triple-tail, eq:min-subadd

## sec:localization, lines 1667-1883

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 08:19:15 ET | lines 1668-1673 | P = ceil(eta^-alpha): 2 <= P <= e^k, G0 <= P^eps, k^p <= P^eps for large k (localization_largeParameter)
complete | 2026-10-14 03:49:26 ET | lines 1676-1687 | Normalized tags, edge relation, depth distances (ChartTag, tagEdge, DepthDistance)
complete | 2026-10-14 03:49:26 ET | lem:graph, lines 1689-1707 | Far tags separate; short paths give endpoint splittings (curvatureGraph)
complete | 2026-10-14 03:49:26 ET | lines 1713-1745 | Decreasing colors and delays with small failure set for any D >= list size (monotoneColoring)
complete | 2026-10-14 03:49:26 ET | lem:masks, lines 1747-1773 | Historical pad masks, usable endpoints, inclusion, closure, separation
complete | 2026-10-14 03:49:26 ET | lem:whole-ranges, lines 1777-1794 | eq:whole-ranges and adjoint ranges (usableRangeBessel, attempt_wholeRanges)
complete | 2026-10-14 03:49:26 ET | lines 1797-1801, 1817 | Same-tag template test (sameTagTemplateTest)
complete | 2026-10-14 09:39:07 ET | lines 1803-1815 | Main columns (originals rank 0, own weights; templates weight 1), masks, ranks, pads, filters, eq:catalog-test (Sec12_3b)
complete | 2026-10-14 10:20:26 ET | lem:closure, lines 1819-1828 | Main and helper closure on all active cells with rank and path counts (main_closure, helper_closure)
complete | 2026-10-14 10:44:02 ET | lem:closure, lines 1820, 1823, 1828-1830 | Names exp(k^O(1)), log n_(L+5), log T <= k^C, no cap attained (closure_poly, colorSizes_poly)
complete | 2026-10-14 11:05:35 ET | line 1835 | D_m = colBudget^2 T U, log D_m <= k^O(1); rank-r primal costs D sqrt(n_r) (mainBudget, primal_expansion_count)
complete | 2026-10-14 12:04:51 ET | prop:localize, lines 1838-1856 | Current-group decomposition on the main columns, error 9(D+1)tau_3 S^4 per leaf (attempt_localization)
complete | 2026-10-14 13:13:32 ET | line 1859 | B_(l,s)B_l = signed sum of averaged main products on F_l (basic_history_expand); loss G0 (basic_compression); zero/retained masks
complete | 2026-10-14 03:49:26 ET | lem:variation proof, lines 1871-1877 | Joint Bessel via whole ranges, product jumps, compression, averages (abstract)
complete | 2026-10-14 14:17:36 ET | lem:variation, lines 1861-1879 | eq:variation on main columns (basic_variation_G0), shared history, overlap, one-time; whole ranges on vertices

## sec:modes, lines 1884-2235

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-14 14:32:19 ET | line 1888 | Primaries = main columns of the outer ball at max pad/rank; first-match cells, branches disjoint, nested (primaries, firstCells)
complete | 2026-10-14 03:49:26 ET | lines 1890-1893 | Branch lift d_rho, branch phase p_rho, theta_z/Q0 (branchLift, centerPhase)
complete | 2026-10-14 14:43:37 ET | eq:offset-mean, lines 1895-1901 | zeta in [0,1], 0 within delta of cuts, 1 beyond 2 delta; E zeta >= 1/2, E|1-zeta^2|^2 <= 4 d delta
complete | 2026-10-14 14:54:29 ET | eq:firstmatch, lines 1888, 1903-1910 | Finite first-match expansion of main primaries, kept on descendants (mainFirstMatch_kept)
complete | 2026-10-14 03:49:26 ET | eq:mode-differences, lines 1911-1916 | Same-primary mode differences a.(theta_v, theta_z/Q0), recentring (key_diff)
complete | 2026-10-14 03:49:26 ET | eq:modes, lines 1918-1922 | Augmented modes with distinct private indices (augMode)
complete | 2026-10-14 03:49:26 ET | lines 1923-1932 | Lift R_(l,G): bounded, |q_Phi| <= delta_c, exact synthesis (modeLift, LiftData)
complete | 2026-10-14 15:17:43 ET | line 1932 | Main-column lift (mainAttemptLift): private eps_Phi, local eps_m, 1/eps_m <= cB^2(e^(2DX^D)+1), sum|q|^2/eps <= dc^2 N cB^2, synth
complete | 2026-10-14 16:07:04 ET | line 1934 | D_* = modeStar >= e^k, mode counts and uses on paths across groups, heights, weights, Q0, R Z sums on cells; log D_* <= C(kP)^C
complete | 2026-10-14 03:49:26 ET | eq:gauge-cancel, lines 1938-1944 | Product of demodulations is an integer-carry character (gauge_cancel)
complete | 2026-10-14 16:53:10 ET | line 1944 | Multiplier exact on true supports (cutoff delta/2); Fourier norms of M, zeta^2 in D_*; tails <= D_*^-300 at B_*; log B_* <= P^C
complete | 2026-10-14 03:49:26 ET | eq:mode-parameters, lines 1946-1962 | Mode schedule and choice of K (chooseSchedule, exists_attempt_schedule)
complete | 2026-10-14 03:49:26 ET | eq:lags, line 1963-1966 | Blocks [b,b+K) and lags u_b, v_b, t_b (lagU, lagV, lagT)
complete | 2026-10-14 17:19:22 ET | line 1967 | Z frozen at u_b (zero before attempt); retained v_b-cells (actual uses); Z~ = R Z_(u_b), coefficients constant on u_b-cells
complete | 2026-10-14 03:49:26 ET | eq:slope-variation, lines 1968-1975 | Slope oscillation bound and frozen-mode interface (slope_variation_mode, ModeSystem)
complete | 2026-10-14 03:49:26 ET | eq:PRE, eq:CURRENT, lines 1979-1989 | PRE and CURRENT graphs, components, monotonicity (preCurrent, blockComps)
complete | 2026-10-14 03:49:26 ET | eq:gap, lines 1991-1995 | Nonexceptional primary at a block (nonexcAt)
complete | 2026-10-14 17:34:32 ET | line 1996 | Each primary exceptional in at most 4 dim Theta blocks (lem:height packets); zero evaluations tiny (exceptional_blocks_le)
complete | 2026-10-14 17:48:30 ET | lines 1997-1998 | Height-H vectors of K_rat tiny at a nonexceptional block, spanning constant below T^2 2^(3K) from T_gt; K_B = tinyKB
complete | 2026-10-14 18:09:51 ET | lem:stabilize, lines 2002-2028 | Nonexceptional primary: all but 3 d_max R heights <= J_* give direct PRE edges at h-10 (Valid.stabilize)
complete | 2026-10-14 03:49:26 ET | eq:good, lines 2030-2037 | Good modes, core and side modes, using the stable heights of the stabilize proof
complete | 2026-10-14 18:20:32 ET | lines 2039-2044 | Same PRE predecessor and core coherence on eq:upper-heights at the schedule, hstab from lem:stabilize
complete | 2026-10-14 03:49:26 ET | lines 2039, 2044 | Minimal-PRE invariance and core bad proportion <= 2 delta_* (good_iff_of_minimal_pre)
complete | 2026-10-14 03:49:26 ET | lem:mode-rows, lines 2049-2057 | Separated mode rows and cross pairs (aug_mode_rows, modeWave_pair_le)
complete | 2026-10-14 19:20:23 ET | lem:lift-composition, lines 2062-2077 | Main-column lift rows jointly Bessel, histories and basic inputs added: c G0 |R| (lift_composition_G0)
complete | 2026-10-15 20:14:15 ET | prop:linear-side, lines 2080-2087 | eq:linear-energy: sum ||V||^2 <= 24(L+1)(G0+2C_F/D_*^394)|R|, frozen coeffs, per-group Q0 (linear_energy)
complete | 2026-10-14 03:49:26 ET | lines 2088-2099 | Side events, classes, links; failed-test telescoping (sideEvents, chain_bad_count)
complete | 2026-10-14 19:38:43 ET | eq:bad-density, lines 2100-2112 | One-class chains: N <= 180 d_max log(2D_m)/delta_*, path labels, A_e, A_h derived (chain_length_schedule)
complete | 2026-10-14 19:55:46 ET | lines 2114-2116 | Level rows with path counts <= D_*, pairings <= D_*^-200; group rows Bessel 6(L+1) (group_event_rows_schedule)
complete | 2026-10-14 20:12:36 ET | line 2118 | Per-event error^2 <= B_c|J|/D_*^397; total over groups <= 3(L+1)B_c|R|/D_*^396 by path counts (side_errors_negligible)
complete | 2026-10-14 21:13:02 ET | eq:sides, eq:core-side-error, lines 2124-2133 | Z~ = A + V (full core subtotal); S = Z_s - Z_u + V; Z_s = A + S + E (core_side_error)
complete | 2026-10-14 21:50:07 ET | lines 2135-2150 | |E|^2 <= 2|1-zeta^2|^2|Z|^2 + 2dc^2(sum|beta|)^2, sup <= sum|beta|; mean, path count, offsets (exists_offsets_used)
complete | 2026-10-14 21:50:07 ET | eq:physical-error, lines 2151-2156 | Used cells: sum int |E|^2 <= (8 d_max delta + 2dc^2) 4N colBudget^2 C_F N_use |R| (physical_error_used)
complete | 2026-10-15 20:14:15 ET | line 2159 | Rolling <= K(20G0+32)|R|; V counted <= K times; U side <= 2C_U|R|; side states with per-group Q0 (sideState_budget)
complete | 2026-10-14 22:12:18 ET | eq:side-cap, lines 2160-2163 | One cut of length <= rho|R| caps sum ||S||^2 on retained paths by (sum A)/rho <= m P^(C+1) (side_cap_states)
complete | 2026-10-14 22:24:26 ET | line 2164 | Core/error sizes on retained cells via Z_u = Z_s - (Z_s - Z_u); error terms <= C M^3 sqrt(N eps)|R| (error_terms_le)
complete | 2026-10-14 22:34:50 ET | lines 2167-2169 | Helper closure (rank L+5) on whole side states; main tests, ball and cumulative filters unchanged (helper_instantiation_main)
complete | 2026-10-14 22:47:46 ET | lines 2172-2185 | Typed hereditary representatives; stabilization via lem:stabilize (blockComps_stab, typed_representatives_sched)
complete | 2026-10-14 03:49:26 ET | eq:representative-separation, lines 2186-2192 | Separation given CURRENT non-adjacency (representative_separation)
complete | 2026-10-14 03:49:26 ET | eq:component-size, lines 2196-2201 | Component sizes sigma_F (component_sizes)
complete | 2026-10-14 23:13:04 ET | eq:size-comparison, lines 2202-2209 | sigma_F^2 <= 12(PZ+V_F)+3Bc/D*^59, sum|V_F|^2 <= 2|V| (size_comparison, side_comparison_block)
complete | 2026-10-15 20:14:15 ET | prop:tops, lines 2212-2219 | Cuts <= rho|R|; sum_G |A_G| <= min(D*, M N/(rho s^2)) off cuts; per-group Q0 (first_top_count_main)
complete | 2026-10-15 00:08:28 ET | lines 2221-2228 | First tops, cross-mode separation, path-count rows, lift composition, side part, absorption (tops_energy)
complete | 2026-10-15 00:08:28 ET | line 2229 | Cuts over all choices (tops_cut_many), first tops above uses, D* budget, component sizes (compSize_le)

## sec:sides, lines 2236-2459

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-15 00:20:24 ET | lines 2236-2237 | Helper rank L+5 on whole side states, all named histories; per cell <= n_(L+5), log n_(L+5) <= k^C (helper_sides)
complete | 2026-10-14 03:49:26 ET | line 2240 | Complement expansion into chain products; distinct ranks (form_layer_chains)
complete | 2026-10-14 03:49:26 ET | eq:transfer, lines 2242-2251 | Pad bands and exact transfer identity (padFam, transfer_identity)
complete | 2026-10-15 01:46:26 ET | lines 2252-2256 | Far bands, main columns: <= #steps (P+1)^2 8 tau_3 S_z^2 S_a S_b per chain pair; thresholds cancel costs (leaf_far_search)
complete | 2026-10-15 01:46:26 ET | eq:transferred-main, lines 2257-2263 | H(D S_a,S_b,Y_c,Y_d) - U corrections + defects, D <= 2fuel+2 helper averages (leaf_transferred_mainM)
complete | 2026-10-14 03:49:26 ET | eq:mixed-Mq, lines 2267-2272 | Mixed maximal bound (oneMixedNorm)
complete | 2026-10-14 03:49:26 ET | lem:shortblock, lines 2275-2367 | eq:shortblock and its proof (short_block_comparison)
complete | 2026-10-15 01:59:31 ET | line 2373 | P^C1 budgets of size P^C2|R| capped at P^(C1+C2)/rho by one cut of length <= rho|R| (poly_budget_caps)
complete | 2026-10-14 03:49:26 ET | eq:three-sides, lines 2375-2382 | Group Cauchy-Schwarz and eq:three-sides (group_triple_le, three_sides_power)
complete | 2026-10-15 01:59:31 ET | lines 2382-2384 | Leaf main <= eta sqrt(sum S_a^2) sqrt(sum S_b^2); U corrections three strong factors (leaf_main_groupsM, leaf_corr_groupsM)
complete | 2026-10-15 02:24:32 ET | line 2386 | Frozen complements: local bounds, single-pad variation joint (ball) or shared (cum, history) G0|R| (basic_variation_ballP/cumP)
complete | 2026-10-14 03:49:26 ET | line 2388 | Flag indicator inequality (freeze_flag_le)
complete | 2026-10-15 02:24:32 ET | line 2388 | Flag energy <= K C0^-2 sum |u_J - v_J|^2 over certified ancestors (flag_energy_le, band_stack_le, Cert.mono)
complete | 2026-10-15 02:55:16 ET | eq:stack-energy, lines 2393-2399 | Banded side via global helper bands (bandStackM_all), untouched side (posStack_all); varCap_basicOut
complete | 2026-10-14 03:49:26 ET | lines 2401-2419 | Binary prefix expansion, linear-side product jumps, rolling split (abstract Hilbert space)
complete | 2026-10-16 00:05:56 ET | lines 2415-2419 | Rolling base terms: E_W <= 2(20G0+32)|R|+2V|R|, no K (sideState_budget_blocks, rolling_budget_blocks)
complete | 2026-10-15 02:55:16 ET | line 2419 | Leaves, chain pairs, steps, offsets, lengths <= exp((7c+6)X^2), X = 1+log 2k (config_count_le, leaf_chain_counts)
complete | 2026-10-14 03:49:26 ET | line 2421 | Rademacher selection identities (rademacher_select_two, piece_select_bound)
complete | 2026-10-15 03:44:08 ET | line 2426 | Sum |Omega_nu| <= |configs| M_act D |R|, active multiplicity, uniform in depth (hull_mass_active, hull_mult_le, useHull_max_sub)
complete | 2026-10-14 03:49:26 ET | line 2428 | Hull cuts for two energies (two_hull_caps)
complete | 2026-10-15 03:44:08 ET | line 2428 | Joint caps of the actual stacks from eq:stack-energy and the use multiplicity (near_band_cutM, near_band_actualM)
complete | 2026-10-14 03:49:26 ET | lines 2430-2437 | Sparse decomposition into short-block pieces and hull-maxima summation
complete | 2026-10-15 03:44:08 ET | eq:near-band, lines 2438-2443 | (o/P) near bands <= 4 C_q(1+C_N) log K K^e B_c B_d G0 P^(-1/2)|R| (near_band_criticalM, stackEA_le)
complete | 2026-10-14 03:49:26 ET | eq:min-power, lines 2444-2449 | Signs to absolute sums; min(eta,x) <= eta^(1-p) x^p and split
complete | 2026-10-15 20:14:15 ET | lines 2446, 2451 | Leaf side estimate on side states of per-group Q0 (side_estimate_leaf, toLeafQ); base data anew below subroots
complete | 2026-10-16 00:05:56 ET | lines 2454-2456 | Exported estimate: cut 2rho, two-side, near-band (K-free stacks sideB0), three-side, side cap (side_estimate_leaf)

## sec:core, lines 2460-2825

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-15 20:14:15 ET | line 2461 | Core reduction: errors, 2+2 restored, >=3 sides, retained sizes; cores of D.withQ0 (qG G) (core_reduction_leaf)
complete | 2026-10-15 08:23:22 ET | line 2464 | Component expansion and first success over upper heights on side states (coreAt_eq_comps, tuple_success, pattern_first_success)
complete | 2026-10-15 08:32:17 ET | line 2466 | Masks select whole components and final classes; selected modes in the good predecessor; stabilization
complete | 2026-10-15 08:42:01 ET | eq:core-torus-form, lines 2466-2471 | Selected wave sum = e(cp)e(g*(y-x*))g(xi(y-x*)) up to D_*^-150 (cell_torus_form, core_torus_form)
complete | 2026-10-15 08:49:43 ET | eq:frequency-box, lines 2471-2476 | All indices in D_*^5 E_h, cutoff costs <= gaugeSqNorm, tails <= D_*^-300 (freqBox_*, cutoffP_truncate_full)
complete | 2026-10-15 08:54:16 ET | line 2478 | Offset cutoff average, offset side norm, gauge multiplier; truncated R_z <= 1 + tail (multTrunc_sup)
complete | 2026-10-15 08:58:02 ET | line 2480 | Declaration common-height on a leaf cell of the side states (SideInput.firstSuccessfulHeight)
complete | 2026-10-15 09:06:20 ET | lines 2482-2487 | Tiny/huge dichotomy in the full box at the schedule (box_dichotomy, frequency_dichotomy); torus H
complete | 2026-10-15 09:41:15 ET | eq:torus-size, lines 2489-2496 | True periodic factor on H: a' <= 6 (sum_D (|A_D|_2,I + D*^-30 s_D)^2)^1/2 <= 6 sigma_F (torus_size)
complete | 2026-10-14 03:49:26 ET | eq:Haar-four, lines 2498-2504 | Four-function Haar bound on rational subtori (haar_four)
complete | 2026-10-15 09:45:50 ET | eq:four-tests, lines 2506-2520 | U0, Q, T, fixed-rule reference in the full box, discard test, dyadic bands (fourRef_spec, fourBands_spec)
complete | 2026-10-15 10:19:22 ET | lines 2522-2530 | Four-core coset reduction on side states: |Lambda| <= errors + |W|(1+tau_m) prod(a'_j+tau_c s_j) (four_core_test)
complete | 2026-10-15 10:24:25 ET | lines 2530-2540 | Kernel decay; three-core test on side states: threeRef, threeBeta, threePasses, bands; W_beta entries
complete | 2026-10-15 10:33:35 ET | lines 2542-2547 | Three-core cosets on the side states (three_cosets); Parseval for D_m with sup (1+tau_m)(1+tau_c) (dual_slice_parseval_of)
complete | 2026-10-15 11:17:23 ET | eq:side-windows, lines 2549-2560 | Averaged windows b_Lambda (threeWin), W=(1+tau_m)(1+tau_c), prod(a'_j+tau_c s_j), tail (three_core_test)
complete | 2026-10-15 12:42:49 ET | eq:core-numerical, lines 2562-2567 | Tuple errors <= C D_*^-100 prod sum|alpha| (x side size); first-success weight one; integrated O(e^-k|R|)
complete | 2026-10-15 12:58:11 ET | lines 2569-2577 | a'_j <= 6 sigma_F, E a'_j^2 <= 36 (2d_*)^n_j sigma_F^2; Holder E prod a'_j <= 36^4 (2d_*)^(n/4) prod sigma_F
complete | 2026-10-15 13:36:31 ET | eq:principal-core, lines 2577-2582 | 4 and 3 cores: sum over heights and bins of C mu nu^-J Lambda^-J prod sigma_j N plus errors
complete | 2026-10-15 13:41:31 ET | line 2585 | Declaration frequency-tests on a leaf cell of the side states (SideInput.principalFrequencyTests)
complete | 2026-10-14 03:49:26 ET | lem:sparse-count, lines 2587-2705 | Sparse progression mass count and its proof (sparse_count)
complete | 2026-10-15 14:18:57 ET | lines 2709-2717 | Hereditary reps of class nodes, path separation, injective labels, FourRef/ThreeRef, pair determination, b_Lambda <= |S|_2,I
complete | 2026-10-15 14:26:56 ET | eq:triple-test, lines 2718-2724 | Side-state triple tests; scale count L0 by lem:height, L0 <= 32(dmax+5)^4 (log(288D^5H)+log2+1)(1+log nu/mu)
complete | 2026-10-15 14:46:52 ET | eq:total-count, lines 2726-2729 | Side states: sum N_s <= L0 M_i M_j, N_s <= M_i M_j; disjoint side windows + Bessel give incidence <= w_s
complete | 2026-10-15 14:59:05 ET | eq:applied-sparse, lines 2731-2742 | Side states: lem:sparse-count with explicit C, C_res; reserves from A0, Xi; pure-shift gap of good modes
complete | 2026-10-15 15:04:13 ET | line 2744 | Declaration tested-counts on the side states (SideInput.testedTupleCounts)
complete | 2026-10-14 03:49:26 ET | lem:distribution, lines 2747-2769 | Distribution power bound (distribution_power)
complete | 2026-10-15 15:16:30 ET | lines 2772-2774 | Side states: <= D*^4 tuples; bins with amplitude < eps sum to <= e^-k|R|; retained quadruples <= (log2 U/eps+1)^4
complete | 2026-10-14 03:49:26 ET | eq:fixed-power, lines 2776-2779 | eps = 1/1200 and p = 1 - eps bookkeeping (powered_count_exponents)
complete | 2026-10-15 15:22:13 ET | eq:powered-count, lines 2781-2786 | Side states: sum_s N_s^p <= 4/3 (L0 M_i M_j)^3/4 (C l L0^12)^1/4 M^(1-c)/2, any pair; three cores, M_l >= 1
complete | 2026-10-14 03:49:26 ET | lines 2788-2799 | Holder over groups and amplitude factor <= 1
complete | 2026-10-15 15:34:37 ET | lines 2783-2800 | Side states: (sum_G sum_s N^p)(prod sigma)^p <= 16/3 L0^3/4 B^1/4 K^(2-c/2); top-count caps bridged to prop:tops
complete | 2026-10-14 03:49:26 ET | lines 2802-2806 | Band series summable (band_sum_summable)
complete | 2026-10-15 15:42:15 ET | lines 2802-2806 | Coefficient <= C Pw^15/4 Pl^1/4 (1+log nu/mu)^4 (schedule); dyadic band sums <= convergent series; types in [0,log2 D*]^2
complete | 2026-10-15 23:02:41 ET | eq:core-final, lines 2808-2817 | eq:core-final across groups, per-group Q0, anchors where alive sets are nonempty (four/three_core_final_side)
complete | 2026-10-15 16:17:46 ET | lines 2820-2822 | Declaration core-estimate (poweredCoreEstimate): patterns added, exponent 1/1200, M_tau with absolute exponents

## sec:completion, lines 2826-3010

status | timestamp (YYYY-MM-DD HH:MM:SS ET) | exact source location | brief mathematical step
--- | --- | --- | ---
complete | 2026-10-15 17:42:28 ET | line 2836 | Side-state bounds carry C_N for the window of nonzero-weight cells (ActiveSetup.DepthWin), as in RetainedMin
complete | 2026-10-15 18:37:37 ET | lines 2839-2840 | Basic inputs normalized on every setup cell: HasColumnRep cell energies, BasicFamilies.normF (hnormF, C_F = 1)
complete | 2026-10-15 18:37:37 ET | line 2839 | Main and helper catalogs closed on test cells Tc (the active cells): main_closure, helper_closure, attempt_localization
complete | 2026-10-15 18:46:21 ET | line 2839 | Attempt parameters and catalogs: exists_attempt (counts before H_ed, then colors, M_c; localization of pattern minima)
complete | 2026-10-15 18:37:37 ET | line 2839 | Current groups certified on retained cells (groupsAt_cert_use with FamParams.failure_cut)
complete | 2026-10-15 20:23:44 ET | line 2839 | Schedule: d_max = 2d_B+2 <= D_* = modeStarG, Q0 = ceil(H_ed^(d_B^2)) >= all clearInt C_z, B_* = Q0 2^(K*+1) (exists_leaf_schedule)
complete | 2026-10-15 20:33:28 ET | line 2839 | Offsets by the majorant, then modes of all roles and groups; errors <= (8d_B delta+2dc^2)4N C_F N_use|R| (exists_leaf_modes)
complete | 2026-10-15 21:31:13 ET | line 2839 | One frozen family c: reps, sq sums, eq:linear-energy, retained-path top counts (first_top_count_main); RepAt, hlin forms
complete | 2026-10-15 22:05:06 ET | line 2839 | Helper catalogs: leaf with cat ++ hcat (appendCat), main objects unchanged on active cells, helper tests (helper_sides), BallData
complete | 2026-10-15 22:11:47 ET | line 2839 | Stacks cost G0: stackEA_le_G0, bandJumpM <= (n+1)^2 G0^2; counts Lp = 2^fuel, Jm = 2fuel+2 (pe/desc lengths), Ee (errAt_energy_le)
complete | 2026-10-16 11:36:19 ET | line 2839 | Exceptional roots <= |R|/4: padded vertex bound (padDc) gives failure roots <= |R|/8, leaf cuts 12 N_l rho <= 1/8 (root_assembly)
complete | 2026-10-14 03:49:26 ET | lines 2840-2841 | Restarts: retained estimate gives all active cells with factor 4/3 (activeMin_of_retainedMin)
complete | 2026-10-16 11:36:19 ET | line 2844 | Explicit leaf bound: leaf_final (sizes via B = C_b (k_D P)^C_b, G = e^(g(1+log 2k)^2)) and leaf_estimate
complete | 2026-10-16 11:36:19 ET | eq:before-absorption, lines 2846-2853 | Retained attempt: N_l leaf bounds plus localization error (exists_attempt, root_assembly)
complete | 2026-10-16 11:36:19 ET | lines 2854-2866 | Absolute degrees c, cc before q (attempt_param_bounds, retained_numeric_poly/exp); q after C_l
complete | 2026-10-14 03:49:26 ET | lines 2868-2870 | Choice of q with 2 C5 (q-2)/(q-1) < 1/8 (exists_exponent_near_two)
complete | 2026-10-16 11:36:19 ET | lines 2872-2876 | P = ceil(eta0^-alpha) dominates k^C, G^C; G0 <= P^(1/8) (retained_numeric_exp, retained_arith)
complete | 2026-10-14 03:49:26 ET | lines 2876-2883 | Block term and power absorption (block_term_le, absorption_power_bound)
complete | 2026-10-16 11:36:19 ET | eq:active-final, lines 2884-2889 | RetainedMin proved (retainedMin_holds); ActiveFinal for every class (activeFinal_holds)
complete | 2026-10-16 11:36:19 ET | line 2891 | Minima on the original cell sums throughout (exists_attempt localization, leaf_estimate, retainedMin_holds)
complete | 2026-10-14 03:49:26 ET | lines 2893-2900 | Update levels, choice of k_1, cutoff limit: prop:normalized from ActiveFinal
complete | 2026-10-16 11:36:19 ET | prop:normalized, lines 2827-2833 | Unconditional: normalizedAbsorption_holds (from activeFinal_holds)
complete | 2026-10-16 11:36:19 ET | thm:uniform-local, lines 2906-2908 | Unconditional: uniform_local_holds (uniform_of_activeFinal activeFinal_holds)
complete | 2026-10-14 03:49:26 ET | thm:uniform-local proof, lines 2910-2930 | Stops, piece bound, sparse sum, absorption (uniform_local_of_normalized)
complete | 2026-10-14 03:49:26 ET | thm:main proof, lines 2943-2983 | Kernel W, partition sum, reconstruction, lattices, scale form given thm:uniform-local
complete | 2026-10-14 03:49:26 ET | thm:main proof, lines 2985-2990 | Odd-part bound and pointwise principal value (unconditional)
complete | 2026-10-14 03:49:26 ET | thm:main proof, lines 2992-2997 | Principal-value form bound and L1 by duality given thm:uniform-local
complete | 2026-10-14 03:49:26 ET | thm:main proof, lines 2999-3008 | Unique bounded L3 extension (schwartz_L3_unique_extension)
