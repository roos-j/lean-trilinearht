# Main theorem overview

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
not started | thm:main, lines 2934–2941 | Uniform L3 trilinear Hilbert transform estimate | 2026-10-08T21:50:31.6115335-04:00
not started | thm:main, lines 2984–2992 | Pointwise principal value on Schwartz inputs | 2026-10-08T21:50:31.6115335-04:00
not started | thm:main, lines 2999–3009 | Unique bounded extension to L3 triples | 2026-10-08T21:50:31.6115335-04:00

# Quantitative quadratic chart calculus prerequisite

The locally quadratic chart lemma needs the substantial general calculus of compactly supported quadratic lattice-sum charts: finite summation, normalization, conjugation, products, affine changes and uniform Gevrey complexity. Pinned Mathlib has no matching quadratic chart theorem; its calculus and Fourier primitives underlie the already-proved general development. Extract that complete development into TrilinearHT/Auto/QuadraticCharts.lean under the reusable-prerequisite exception, not a machine-blueprint section split. Move the primitive logarithmic-size and quasipolynomial-bound definitions with it. Use a primitive local rational height definition, definitionally equal to the existing one, so every statement and local definition depends only on Mathlib and the same module. RationalLinearAlgebra may be imported for proof reuse only. A declaration-reference scan found no other external project dependencies. Verified source: def:chart, lines 625-637, lem:chart-operations, lines 642-660, and the several-variable chart formula. Recorded before creation at 2026-10-09T19:20:45.754745-04:00.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | def:chart and lem:chart-operations, lines 625-660 | Independent quantitative quadratic chart calculus | 2026-10-09T19:24:17.868635-04:00

# Quantitative Gevrey cutoff prerequisite

The Fourier localization needs compact cutoffs and a locally finite integer partition with uniform all-orders Gevrey bounds. Pinned Mathlib supplies smooth expNegInvGlue and smooth transitions but no quantitative Gevrey derivative or partition theorem; the repository's already-proved construction supplies this substantial classical calculus prerequisite. Move that entire independent development, without duplicating or changing its proofs, into TrilinearHT/Auto/GevreyCutoffs.lean. Its general interval, affine-rescaling and finite-product statements use only Mathlib and local definitions. This is the reusable-prerequisite exception, not a machine-blueprint section split. Verified references: blueprint lem:gevrey, lines 107–126, and Mathlib.Analysis.SpecialFunctions.SmoothTransition. Recorded before module creation at 2026-10-09T09:58:48.1075144-04:00.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | lem:gevrey, lines 110–114 | Quantitative derivative bounds for expNegInvGlue | 2026-10-08T22:14:53.8863812-04:00
complete | lem:gevrey, lines 116–117 | Normalized compact bump and interval cutoffs | 2026-10-08T22:24:10-04:00
complete | lem:gevrey, lines 117–125 | Locally finite partition of unity | 2026-10-08T22:24:10-04:00
complete | lem:gevrey, line 126 | Rescaling and multidimensional products | 2026-10-08T22:24:10-04:00

# Quantitative Fourier approximation prerequisite

The chart development and later Fourier splitting use the general derivative-to-Fourier-decay, absolute convergence and quantitative uniform truncation theorem on finite-dimensional tori. Pinned Mathlib has Fourier completeness and summability interfaces, but searches found no matching explicit derivative-order, dimension and tail estimate. This is a substantial classical Fourier-analysis prerequisite. Move the entire already-proved 702-line independent development, without changing its mathematics, into TrilinearHT/Auto/FourierApproximation.lean. A declaration-reference scan found no external project dependencies; its statements and local definitions use only Mathlib. This invokes the reusable-prerequisite exception, not a source-section split. Verified references: blueprint lem:fourier-foundation, lines 130-146, and Mathlib.Analysis.Fourier.AddCircleMulti. Preserve the existing attribution to ../lean-dfr. Recorded before creation at 2026-10-09T13:27:14.2870246-04:00.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | lem:fourier-foundation, lines 130–146 | Coordinate Fourier coefficient decay | 2026-10-08T22:44:53-04:00
complete | lem:fourier-foundation, lines 134–146 | Nonzero shell counting, tails, and uniform convergence | 2026-10-08T22:44:53-04:00
complete | lem:fourier-foundation, lines 130-146 | Independent Fourier approximation module verification | 2026-10-09T13:30:19.8983506-04:00
complete | lem:separation, line 1409 | Module extension: bilinear convolution forms bounded by the kernel's Fourier supremum (Parseval, Cauchy-Schwarz); statement uses only Mathlib | 2026-10-10T11:41:13-04:00

# Balog-Szemeredi-Gowers prerequisite

The finite inverse argument needs the classical Balog-Szemeredi-Gowers energy-to-small-difference theorem and its dense bipartite four-path prerequisite. Pinned Mathlib supplies Finset.addEnergy and basic finite inequalities, but direct searches found no quantitative BSG or dependent-random-choice four-path theorem; searches of ../lean-spherical, ../lean-dfr and ../lean-variationalsw found no adequate replacement. This substantial textbook additive-combinatorics theorem qualifies for the reusable-prerequisite exception. Develop exactly one independent module, TrilinearHT/Auto/BalogSzemerediGowers.lean, with general finite bipartite relations and finite subsets of arbitrary abelian groups. Its statements and supporting definitions use only Mathlib and that module, including Mathlib additive energy. Verified reference: blueprint lem:four-paths, lines 668-680, and lem:BSG, lines 683-698. Recorded before module creation at 2026-10-09T14:47:46.4267765-04:00.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | lem:four-paths, lines 670-674 | Neighborhood/codegree double counting and first/second moments | 2026-10-09T14:52:20.8641038-04:00
complete | lem:four-paths, lines 670-674 | Bad-pair averaging and selection of a dense neighborhood | 2026-10-09T14:57:13.8900741-04:00
complete | lem:four-paths, line 675 | Deletion bound and retained vertex-set size | 2026-10-09T15:01:48.0030381-04:00
complete | lem:four-paths, lines 675-679 | Common middle vertices and four-step path lower bound | 2026-10-09T15:08:14.766138-04:00
complete | lem:four-paths, lines 668 and 679-680 | Dense four-path theorem and proper-color path recovery | 2026-10-09T15:11:08.068583-04:00
complete | lem:BSG, lines 685-692 | Popular sums and the dense properly colored graph | 2026-10-09T15:14:54.415305-04:00
complete | lem:BSG, lines 693-697 | Injective path-color encoding of differences | 2026-10-09T15:18:18.207056-04:00
complete | lem:BSG, lines 683-698 | Energy-to-small-difference theorem with exponent ten | 2026-10-09T15:20:55.890802-04:00

# Chang spectrum and Bohr cardinality prerequisite

The finite inverse theorem and dense Bogolyubov argument need Chang's quantitative spectrum-generating theorem and the Bohr-set cardinality estimate. Pinned Mathlib has AddDissociated, maximal dissociated span, and AddDissociated.randomisation (the Riesz-product mean identity), but direct searches found no quantitative spectrum cardinality bound or Bohr-set pigeonhole estimate; searches of ../lean-spherical, ../lean-dfr and ../lean-variationalsw found no replacement. This is a substantial classical finite harmonic-analysis theorem. Create exactly one independent module, TrilinearHT/Auto/ChangSpectrum.lean, using only Mathlib and local definitions for finite abelian groups, additive characters, and circle-valued homomorphisms. Reuse the existing randomisation and dissociation proofs. The source cyclic statement will be connected to the project's normalized Fourier transform in the main file. This is the reusable-prerequisite exception, not a blueprint-section split. Verified reference: blueprint lem:Chang, lines 730-764. Recorded before creation at 2026-10-09T15:25:46.465143-04:00.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | lem:Chang, lines 735-748 | Circle partition and large Bohr-set fiber | 2026-10-09T15:30:40.734436-04:00
complete | lem:Chang, lines 749-757 | Phase alignment and positive Riesz-product mean | 2026-10-09T15:34:22.584971-04:00
complete | lem:Chang, lines 758-763 | Logarithmic lower bound and Jensen cardinality estimate | 2026-10-09T15:42:35.244416-04:00
complete | lem:Chang, lines 739-764 | Spectrum generation, cyclic Fourier bridge and full-density case | 2026-10-09T15:49:08.231318-04:00

# Khintchine and empirical sampling prerequisite

The later almost-period and signed-stack arguments need the general Khintchine upper inequality and its empirical-sampling consequence. Searches of pinned Mathlib Probability and Analysis found no Khintchine or symmetrization/sampling moment theorem; the repository already contains a complete proof adapted from ../lean-variationalsw. Extract that substantial textbook probability prerequisite, unchanged, into TrilinearHT/Auto/KhintchineSampling.lean. Include all sign, independent-copy, finite-mean, finite-Lp and convolution definitions it uses. A declaration-reference scan found only finiteAverage and finiteConvolution as outside dependencies; move those definitions too, so all statements depend only on Mathlib and local definitions. This invokes the reusable-prerequisite exception, not a blueprint section split. Extend this same independent empirical-sampling module with the Croot-Sisask almost-period consequence, blueprint lem:almostperiods, lines 766-784, using its existing probability norms and sampling theorem. No additional module is needed. Verified reference: blueprint lem:finite-fourier, lines 177-209; preserve sibling attribution. Recorded before creation at 2026-10-09T13:58:52.3025486-04:00. Consolidation recorded at 2026-10-09T21:22:18.523546-04:00: move the already-proved finite Fourier foundations from main into this module, beside their local finiteAverage, finiteConvolution and uniformMean primitives; add the trilinear Fourier selection estimate needed for finite-inverse lines 1148-1157. The unchanged foundation statements depend only on Mathlib and this module.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | lem:finite-fourier, lines 177–200 | Signs with constant 2 sqrt(p) and double randomization | 2026-10-08T23:38:00-04:00
complete | lem:finite-fourier, lines 183–209 | Independent-copy symmetrization and sampling convolution bound with constant 4 | 2026-10-08T23:38:00-04:00
complete | lem:finite-fourier, lines 177-209 | Independent Khintchine and sampling module verification | 2026-10-09T14:01:38.3847714-04:00
complete | lem:almostperiods, lines 766-783 | Finite probability Lp triangle and translation laws | 2026-10-09T15:53:14.874213-04:00
complete | lem:almostperiods, lines 777-781 | Markov bound and at least half good sample tuples | 2026-10-09T15:56:41.390579-04:00
complete | lem:almostperiods, lines 781-783 | Diagonal tuple fibers and a large parameter set | 2026-10-09T16:01:15.051590-04:00
complete | lem:almostperiods, lines 766-783 | Translation difference bound and exact sample-size density | 2026-10-09T16:05:17.921479-04:00
complete | lem:almostperiods, lines 775 and 783 | Iterated sum-difference almost periods | 2026-10-09T16:10:28.248803-04:00

# Dense Bogolyubov prerequisite

The finite inverse argument needs the classical quasipolynomial dense Bogolyubov theorem: for every nonempty subset A of a finite cyclic group, 2A-2A contains a Bohr set with rank O(log^4(1/alpha)), reciprocal radius O(alpha^(-1) log^4(1/alpha)), and density exp(-O(log^5(1/alpha))). Searches of pinned Mathlib additive combinatorics/Fourier and ../lean-spherical, ../lean-dfr and ../lean-variationalsw found no such theorem. This substantial named theorem qualifies for the reusable-prerequisite exception. Create exactly one module, TrilinearHT/Auto/DenseBogolyubov.lean, general over all positive cyclic moduli and arbitrary finite subsets. Its theorem statements and local definitions use Mathlib/local vocabulary; proofs may reuse the already-verified KhintchineSampling and ChangSpectrum modules, as explicitly permitted by the skill. Do not import the main proof module or create a cycle. The main module has 9489 lines, but mathematical substance, not file length, justifies this split. Verified reference: blueprint lem:dense-Bohr, lines 786-820. Recorded before creation at 2026-10-09T16:10:28.248803-04:00.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | lem:dense-Bohr, lines 794-795 | Positive convolution witness, value at zero and difference-set support | 2026-10-09T16:16:13.631781-04:00
complete | lem:dense-Bohr, lines 796-805 | Sampling parameters and convolution amplification of almost periods | 2026-10-09T16:23:23.263794-04:00
complete | lem:dense-Bohr, lines 806-812 | Iterated averaging measure and Fourier multiplier | 2026-10-09T16:30:47.632930-04:00
complete | lem:dense-Bohr, lines 813-817 | Spectrum split and uniform Fourier translation estimate | 2026-10-09T16:39:28.562564-04:00
complete | lem:dense-Bohr, lines 786-820 | Quasipolynomial rank, radius, containment and density | 2026-10-09T16:47:09.953962-04:00


# Hilbert-space atomic decomposition prerequisite

The decomposition in lem:inverse, lines 1218-1239, requires a substantial general Hilbert-space separation theorem for finite atomic sums and two seminorm balls, together with probability-L2 dual bounds. Mathlib supplies Hahn--Banach, Riesz representation and convex hulls but no matching quantitative atomic decomposition theorem; the sibling lean-spherical convex-duality module concerns scalar convex functions. Develop TrilinearHT/Auto/HilbertAtomicDecomposition.lean under the reusable-prerequisite exception, using only Mathlib and definitions local to that module in its statements. The general result will take an independently stated inverse-correlation hypothesis; the main file must discharge it using continuous_inverse. This is not a split along machine-blueprint sections. Recorded before creation at 2026-10-10T00:38:41.342043-04:00.

# Gowers–Cauchy–Schwarz and cube continuity prerequisite

The mixed cube estimates used by lem:cube-foundation and later local von Neumann arguments require the classical Gowers–Cauchy–Schwarz inequality, its U3 seminorm, and eight-input L2 continuity. A search of pinned Mathlib found no Gowers development; Haar integration and Holder provide only its ingredients. Move the already-proved general Haar-probability construction and its supporting cube definitions, without duplication, into TrilinearHT/Auto/GowersCauchySchwarz.lean. The inspected statements use only Mathlib and local definitions, and a declaration-dependency scan found no remaining main-file dependencies. This substantial general additive-combinatorial theorem qualifies for the reusable-prerequisite exception; it is not a machine-blueprint section split. Verified source: blueprint cube-definition, lines 162–175, and lem:cube-foundation, lines 216–237. Recorded before creation at 2026-10-09T10:55:13.8581673-04:00. Extension recorded at 2026-10-09T21:49:19.044725-04:00: the continuous inverse requires finite-to-continuous convergence of cell-averaged cube integrals (lines 1183-1189). Searches of pinned Mathlib and sibling repositories found no ready Gowers discretization theorem. Develop the general cube discretization in this existing module, using Mathlib integration and approximation. Move the normalized finite Haar definition and its two basic instances from main here so all new statements use Mathlib/local definitions; retain source-specific chart applications in main.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | cube-definition, lines 162–175 | Mixed cubes, squared-face identity, positivity and nonnegative roots | 2026-10-08T23:24:00-04:00
complete | lem:cube-foundation, lines 216–231 | Coordinate reflection Cauchy–Schwarz and mixed cube bound | 2026-10-08T23:55:00-04:00
complete | lem:cube-foundation, lines 218–232 | Homogeneity, triangle inequality, and bundled U3 seminorm | 2026-10-09T00:00:00-04:00
complete | eq:cube-L2, lines 223–237 | Independent vertex halves and eight L2 bounds | 2026-10-09T00:15:00-04:00
complete | lem:cube-foundation, lines 227–237 | Continuous extension to eight L2 inputs | 2026-10-09T00:24:23.8312378-04:00

# Fefferman–Stein maximal inequality prerequisite

The mixed maximal estimate in lem:vector-maximal needs the general vector Hardy–Littlewood theorem, absent from pinned Mathlib; the textbook Fefferman–Stein theorem is a substantial reusable prerequisite, developed for general exponents and finite inner measure spaces in TrilinearHT/Auto/FeffermanStein.lean, adapting the finite Hilbert-family proof in ../lean-variationalsw.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | ../lean-variationalsw/VariationalSW/Auto/MarcinkiewiczInterpolation.lean, lines 692–914 | Weak-type interpolation and scalar maximal foundations | 2026-10-09T00:27:15.9941126-04:00
complete | ../lean-variationalsw/VariationalSW/Auto/FeffermanSteinInequality.lean, lines 829–953 | Weighted maximal inequality for arbitrary exponents greater than one | 2026-10-09T00:30:18.3551556-04:00
complete | ../lean-variationalsw/VariationalSW/Auto/FeffermanSteinInequality.lean, lines 955–1114 | Mixed norm duality for outer exponent above inner exponent | 2026-10-09T00:36:18.5217726-04:00
complete | lem:vector-maximal, lines 248–250, permitted vector maximal theorem | Mixed Hölder and dual testing | 2026-10-09T00:41:08.5159750-04:00
complete | lem:vector-maximal, lines 248–250, permitted vector maximal theorem | Remaining exponent range and truncation on finite inner measure spaces | 2026-10-09T00:48:15.5427826-04:00

# Lattice transference principle prerequisite

The successive-minima transference principle is needed by lem:transference and lem:lattice-box; pinned Mathlib supplies dual lattices and Minkowski's first theorem but no adequate successive-minima product bound. This is a substantial classical geometry-of-numbers theorem, here for arbitrary finite-dimensional real inner-product spaces, full lattices and compact symmetric convex bodies, with constants independent of the lattice and body. Its statement and all supporting definitions depend only on Mathlib and the dedicated TrilinearHT/Auto/LatticeTransference.lean. The already-proved integer-basis, reduced-basis and transference development is moved together before the main file reaches its 10000-line limit; the coefficient-box application remains in the main file. Verified references are blueprint lem:integer-basis, lem:reduced-basis and lem:transference, and pinned Mathlib.MeasureTheory.Group.GeometryOfNumbers and Mathlib.LinearAlgebra.BilinearForm.DualLattice.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | lem:integer-basis, lines 257–263 | Primitive integer vector extends to a basis | 2026-10-09T01:00:16.2290272-04:00
complete | lem:integer-basis, lines 257–263 | Saturated subgroup adapted basis and free quotient | 2026-10-09T01:03:57.7910860-04:00
complete | lem:integer-basis, line 263 | Rational subspace integer intersection is saturated | 2026-10-09T01:05:29.6315041-04:00
complete | lem:reduced-basis, line 279 | Finite bounded lattice intersections and shortest nonzero vector | 2026-10-09T01:07:12.4000815-04:00
complete | lem:reduced-basis, line 279 | Shortest vector primitive and extendible to a lattice basis | 2026-10-09T01:09:47.9043507-04:00
complete | lem:reduced-basis, line 279 | Remaining basis projects to a full lattice in the perpendicular space | 2026-10-09T01:16:56.5275745-04:00
complete | lem:reduced-basis, line 279 | Induction on projected lattices and lifting the basis | 2026-10-09T01:27:54.7175149-04:00
complete | lem:reduced-basis, line 279 | Descending integer size reduction preserves later projections | 2026-10-09T01:35:04.0994644-04:00
complete | lem:reduced-basis, line 281 | Adjacent Gram–Schmidt length inequality | 2026-10-09T01:40:07.0238090-04:00
complete | lem:reduced-basis, lines 281–286 | Geometric prefix sum and primal basis norm bound | 2026-10-09T01:44:45.0578284-04:00
complete | lem:reduced-basis, lines 287–290 | Upper triangular inverse coefficient bound | 2026-10-09T01:49:45.1986603-04:00
complete | lem:reduced-basis, lines 291–292 | Dual basis norm bound | 2026-10-09T01:59:33.1650998-04:00
complete | lem:transference, lines 296–303 | Euclidean dual lattice and integer pairing | 2026-10-09T02:04:59.6064805-04:00
complete | lem:transference, lines 296–305 | Symmetric convex body, polar, and gauge | 2026-10-09T02:10:25.7703001-04:00
complete | lem:transference, line 305 | Successive minima are finite and attained | 2026-10-09T02:14:34.5091558-04:00
complete | lem:transference, line 305 | Dimension and integer pairing give lower product bound | 2026-10-09T02:18:17.6561629-04:00
complete | lem:transference, line 307 | Euclidean ball upper product bound | 2026-10-09T02:21:48.7216481-04:00
complete | lem:transference, lines 309–313 | Maximum determinant basis and ellipsoid comparison | 2026-10-09T02:30:01.4863767-04:00
complete | lem:transference, line 314 | Linear transport and full successive-minima product bound | 2026-10-09T02:34:55.5923175-04:00

# Quantitative rational linear algebra prerequisite

The rational height bounds needed throughout the finite coefficient constructions are absent from pinned Mathlib: its rational heights, determinants and projections do not provide the required uniform counting, inverse, pivot right-inverse and projection estimates. Effective rational linear algebra via common denominators and Cramer's rule is a substantial reusable development, including real scalar extension and operator norms. The complete development moves together to TrilinearHT/Auto/RationalLinearAlgebra.lean; all statements and local definitions depend only on Mathlib. This invokes the reusable-prerequisite exception, not a split along machine-generated blueprint sections. Verified references are blueprint lem:rational-linear, lines 416–420, and the pinned Mathlib rational, matrix adjugate, rank and orthogonal-projection developments. The independently reusable height-bin theorem (lem:height, lines 603–619) extends this same module using its local rationalHeight and sharp denominator/minor bounds; no project-specific operator data enter its statements.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | lem:rational-linear, lines 416–418 | Bounded-height rational and matrix counting | 2026-10-09T04:31:15.4544041-04:00
complete | lem:rational-linear, line 420 | Common denominators and determinant bounds | 2026-10-09T04:37:05.2495747-04:00
complete | lem:rational-linear, lines 418–420 | Nonsingular inverse heights and operator norms | 2026-10-09T04:47:12.4740063-04:00
complete | lem:rational-linear, line 420 | Pivot right inverses and bounded-height basis selection | 2026-10-09T04:57:14.3462437-04:00
complete | lem:rational-linear, line 420 | Gram inverse formula for the orthogonal row-space projection | 2026-10-09T05:03:39.3851991-04:00
complete | lem:rational-linear, line 420 | Common integer numerator and denominator bounds for projections | 2026-10-09T05:08:24.1740810-04:00
complete | lem:rational-linear, lines 418–420 | Exponential projection height and norm bounds | 2026-10-09T05:10:46.2540625-04:00
complete | lem:rational-linear, line 420 | Arbitrary rational systems and orthogonal complements | 2026-10-09T05:14:42.2332350-04:00
complete | lem:height, proof line 617 | Sharp per-vector denominator clearing with entries bounded by B^d | 2026-10-09T12:23:24.6448111-04:00
complete | lem:height, proof line 617 | Bounded nonzero integer circuit coefficients | 2026-10-09T12:35:56.2258794-04:00
complete | lem:height, proof line 617 | Independence of geometrically separated nonzero evaluations | 2026-10-09T12:44:46.8898622-04:00
complete | lem:height, lines 603 and 617 | Greedy cover by at most d logarithmic intervals | 2026-10-09T12:52:49.8680184-04:00
complete | lem:height, lines 603-610 and 617 | Dyadic magnitude bins and translated scale counts | 2026-10-09T13:04:45.5253073-04:00
complete | eq:tiny-sum, lines 611–617 | Geometric small-value tail summed over occupied bins | 2026-10-09T16:47:09.953962-04:00
complete | lem:height, lines 616-617 | Coordinate suprema and Euclidean-norm enlargements | 2026-10-09T13:27:14.2870246-04:00

# Dyadic stopping and logarithmic hull maximal prerequisite

The fixed-function hull cuts in lem:cuts need a general finite dyadic stopping theorem absent from pinned Mathlib; finite integration, Markov and layer-cake results supply its classical ingredients. The complete grid, path packing and first-crossing development in TrilinearHT/Auto/DyadicStopping.lean is independently stated for arbitrary real dyadic grids, finite families and normed-space-valued L2 functions, using only Mathlib and its own definitions. Its dedicated module is justified before creation at 2026-10-09T06:18:23.3127599-04:00 and serves later root-normalized attempts as well as path-packing and lem:cuts.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | line 364 | Real dyadic grid data, partitions and children | 2026-10-09T06:18:23.3127599-04:00
complete | eq:path, lines 424–428 | Exact finite dyadic path integral identity | 2026-10-09T05:22:11.5434714-04:00
complete | path-packing, line 429 | Generation decay and geometric restart bound | 2026-10-09T05:25:27.5191409-04:00
complete | path-packing, line 429 | Combining first-stop families by maximal union cells | 2026-10-09T05:28:40.5509687-04:00
complete | lem:cuts, lines 433–436 | Dyadic nesting and disjoint maximal cells | 2026-10-09T05:31:58.4189825-04:00
complete | lem:cuts, lines 435–436 | Ancestor sums, first crossings and retained cells | 2026-10-09T05:34:17.8549265-04:00
complete | lem:cuts, line 451 | First-crossing length cost from path integration and Markov | 2026-10-09T05:43:43.7884176-04:00
complete | lem:cuts, lines 436 and 451 | Everywhere bound for retained ancestor sums | 2026-10-09T05:46:23.9059690-04:00
complete | lem:cuts, lines 453–457 | Finite hull maximal weak bound and support bound | 2026-10-09T05:50:31.2491202-04:00
complete | lem:cuts, lines 458–462 | Truncated hull maxima logarithmic integral estimate | 2026-10-09T05:59:06.4870164-04:00
complete | lem:cuts, line 463 | Partial hull maxima through the current depth and full-max domination | 2026-10-09T06:04:06.0704663-04:00
complete | lem:cuts, lines 458 and 463–465 | Individual and truncated-sum first-crossing costs and their combination | 2026-10-09T06:11:17.7463948-04:00
complete | eq:hull-cap, lines 444–448 and 464–465 | Everywhere whole-cell cap on retained hull maxima | 2026-10-09T06:18:00.8333180-04:00

complete | lem:compression, line 553 | Finite dyadic descendant generations and partition identities | 2026-10-09T08:14:25.2978306-04:00
complete | lem:compression, line 553 | Enclosing finite cell families in complete finite dyadic trees | 2026-10-09T08:18:00.0622912-04:00
complete | lem:compression, line 553 | Finite threshold stopping cuts and terminal partition identities | 2026-10-09T08:28:30.8284601-04:00
complete | lem:compression, line 553 | Parent averages and the four-times-root threshold-cut estimate | 2026-10-09T08:32:31.0451735-04:00
complete | lem:compression, line 553 | Iterated doubling roots and finite depth termination | 2026-10-09T08:36:05.0045950-04:00
complete | lem:compression, line 553 | Deepest stopping-root assignment and size-segment partitions | 2026-10-09T08:41:02.1914034-04:00
complete | lem:compression, lines 561–565 | Local weak-type distribution and weighted layer-cake energy inequality | 2026-10-09T09:10:35.7673445-04:00
complete | lem:compression, lines 561–565 | Finite dyadic maximal L2 estimate with norm constant two | 2026-10-09T09:18:35.4175737-04:00
complete | lem:compression, lines 561–564 | Pointwise geometric square-average bound along stopping paths | 2026-10-09T09:23:00.9337250-04:00
complete | lem:compression, line 565 | Small-size geometric sums and logarithmic counts of large stopping sizes | 2026-10-09T09:34:12.4117912-04:00
complete | lem:compression, line 565 | Abstract logarithmic energy estimate for supported moment families | 2026-10-09T09:42:35.6697747-04:00

complete | lem:compression, line 567 | Norm-threshold anchor generations, finite termination and restart assignment | 2026-10-09T10:01:46.7406631-04:00

complete | lem:compression, line 569 | Completion of anchor generations to refining terminal partitions | 2026-10-09T10:09:32.7778492-04:00

complete | lem:compression, lines 569–572 | Jump ancestors and disjoint-cell L2 mass bounds | 2026-10-09T10:27:41.7129579-04:00

# Rademacher–Menshov and nested projection products prerequisite

Justification: the dyadic-prefix row estimate and noncommuting nested-product consequences needed by lem:prefix (lines 508–535) are absent from pinned Mathlib and searched sibling repositories. The classical Rademacher–Menshov dyadic decomposition is a substantial general Hilbert-space theorem (Tao, 247A Lecture Notes 2, page 31, Q14–Q15); one independent Mathlib-only module, TrilinearHT/Auto/RademacherMenshov.lean, will contain the finite row version, nested projections and disjoint-interval jumps, with no project-specific column data. Recorded before creation at 2026-10-09T07:32:32.3778862-04:00.

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | lem:prefix proof, lines 522–526 | Orthogonal block energy and restriction of square-summable rows | 2026-10-09T07:37:43.9518782-04:00
complete | lem:prefix proof, lines 522–527 | Dyadic prefix decomposition and logarithmic row estimate | 2026-10-09T07:43:58.6653854-04:00
complete | lem:prefix, lines 508–514 and 522–527 | Nested projection increments and exact logarithmic prefix bound | 2026-10-09T07:49:01.1014365-04:00
complete | lem:prefix, lines 508–514 and 524–527 | Noncommuting products of nested projection layers | 2026-10-09T07:53:09.8162355-04:00
complete | eq:product-jump, lines 515–519 and 529–534 | Product telescoping and square-sum jump estimate | 2026-10-09T07:59:32.7934472-04:00
complete | lem:prefix, lines 519 and 534 | Disjoint-interval product jumps and empty products | 2026-10-09T08:06:08.5974719-04:00

complete | lem:compression, line 579 | Explicit logarithmic prefix count and numerical restart contraction | 2026-10-09T10:45:41.2520088-04:00
complete | lem:compression, line 597 | General cubic layer-count and logarithmic budget prefix bound | 2026-10-09T11:43:48.0889174-04:00
complete | lem:compression, line 597 | General complement-product expansion and finite row bound | 2026-10-09T11:56:34.0273079-04:00
complete | lem:compression, lines 550 and 597 | Finite row averages for arbitrary complex measures and total variation | 2026-10-09T12:11:54.5393549-04:00

# Main proof ledger

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | lem:budget-rules, lines 82–101 | Sums and products of quasipolynomial bounds | 2026-10-08T21:53:39.6248575-04:00
complete | lem:budget-rules, lines 82–101 | Positive fixed powers and compositions | 2026-10-08T21:53:39.6248575-04:00
complete | lem:budget-rules, lines 82–101 | Polynomial logarithmic bounds and parameter-uniform degrees | 2026-10-08T21:58:59.7690527-04:00
complete | lem:budget-rules, lines 82–101 | Compression overhead bound in logarithmic k | 2026-10-08T21:58:59.7690527-04:00
complete | lem:budget-rules, lines 82–101 | Domination by every positive power of P | 2026-10-08T21:58:59.7690527-04:00
complete | lem:fourier-foundation, lines 137–157 | Separated-frequency rows, multipliers, finite Schur test, and Hilbert duality | 2026-10-08T23:05:08-04:00
complete | lem:fourier-foundation, lines 143–158 | Quadratic oscillatory integral | 2026-10-08T23:10:30-04:00
complete | cube-definition, lines 162–175 | Probability counting measure and normalized finite convolution | 2026-10-08T23:24:00-04:00
complete | lem:finite-fourier, lines 190–213 | Finite cyclic Fourier inversion, Parseval, and convolution | 2026-10-08T23:48:00-04:00
complete | lem:finite-fourier, lines 192–213 | U2 Fourier identity and U3 recursion | 2026-10-08T23:48:00-04:00
complete | lem:vector-maximal, lines 240–251 | Real-line transport and Mq mixed norm power identities | 2026-10-09T00:53:14.8239152-04:00
complete | line 67 and lem:vector-maximal, lines 240–251 | Uncentered maximal comparison and source specialization | 2026-10-09T04:03:13.5692952-04:00
complete | lem:lattice-box, lines 329–331 | Reduced basis and uniform weighted coordinate bound | 2026-10-09T02:38:35.6077786-04:00
complete | lem:lattice-box, lines 332–336 | Integer side lengths, active basis subset, and norm budget | 2026-10-09T02:40:44.5036572-04:00
complete | lem:lattice-box, lines 337–342 | Explicit radius and containment of small lattice vectors | 2026-10-09T02:43:55.2702442-04:00
complete | lem:lattice-box, lines 325, 344 | Partial sums, empty box, and complete coefficient-box theorem | 2026-10-09T02:46:06.8602077-04:00
complete | lem:torus-annihilator, line 358 | Integer basis coordinate automorphism and annihilator model | 2026-10-09T02:52:41.7613034-04:00
complete | lem:torus-annihilator, line 358 | Coordinate torus homeomorphism and connectedness | 2026-10-09T02:57:38.6589457-04:00
complete | lem:torus-annihilator, lines 350–352, 358 | Haar character integral equals the lattice indicator | 2026-10-09T03:02:30.0789289-04:00
complete | lem:torus-annihilator, lines 354–358 | Nonzero integer multiplication and progression surjectivity | 2026-10-09T03:05:20.2536652-04:00
complete | lem:torus-annihilator, lines 358–360 | Progression map preserves Haar probability | 2026-10-09T03:13:39.7011648-04:00
complete | lem:absolute, line 390 | Reciprocal exponent polytope is the convex hull of Boolean endpoints | 2026-10-09T03:19:36.5033979-04:00
complete | lem:absolute, line 392 | Positive interpolation by finite Hölder | 2026-10-09T03:24:08.0681733-04:00
complete | eq:local and lem:absolute, lines 366–388 | Real local form and endpoint change of variables estimates | 2026-10-09T03:30:47.0555808-04:00
complete | lem:absolute, line 394 | Torus and integer lattice endpoint estimates | 2026-10-09T03:37:20.9352088-04:00
complete | eq:absolute, lines 378–396 | Full positive local form estimate in all three settings | 2026-10-09T03:55:09.8722956-04:00
complete | eq:local, eq:marginals and eq:CN, lines 364–403 | Dyadic grid and admissible kernel-family data | 2026-10-09T04:11:38.5255697-04:00
complete | lem:finite-CN, line 409 | Local norms bounded by uncentered maximal functions | 2026-10-09T04:15:03.5938819-04:00
complete | lem:finite-CN, line 409 | Disjoint depth summation gives linear depth bound | 2026-10-09T04:22:34.3225331-04:00
complete | eq:CN, lines 398–403 | Real supremum of positive finite-denominator ratios | 2026-10-09T04:24:35.3227759-04:00
complete | lem:finite-CN, lines 405–411 | Least constant, zero denominator and infinite denominator cases | 2026-10-09T04:26:36.8900084-04:00
complete | column-data, lines 470–481 | Finite private-coordinate column data and inherited masks | 2026-10-09T06:26:52.2367035-04:00
complete | column-data, lines 480–483 | Cell-supported L2 columns and finite-dimensional projection ranges | 2026-10-09T06:31:55.2415063-04:00
complete | column-data, lines 480–483 | Restriction to descendants preserves old column combinations | 2026-10-09T06:37:27.8067536-04:00
complete | column-data, lines 480–483 | Cell support and orthogonality of disjoint column ranges | 2026-10-09T06:40:45.5650753-04:00
complete | column-data, lines 480–483 | Finite stopping-partition ranges and direct-sum projections | 2026-10-09T06:43:15.1970088-04:00
complete | column-data, lines 480–483 | Refinement range inclusion and nested orthogonal projections | 2026-10-09T06:47:42.2970661-04:00
complete | column-data, line 483 | Row-family square bound and exact decision-cell locality interface | 2026-10-09T06:50:38.6993511-04:00
complete | lem:coeff, lines 487–491 and 503 | Private-coordinate lower bound and column-sum upper bound | 2026-10-09T07:00:16.0160019-04:00
complete | lem:coeff, line 503 | Positive averaged Gram operator and inverse bound | 2026-10-09T07:11:31.5815479-04:00
complete | lem:coeff, line 503 | Inverse-Gram formula for orthogonal projection coefficients | 2026-10-09T07:15:33.6342620-04:00
complete | lem:coeff, line 503 | Pointwise projection kernel formula and norm bound | 2026-10-09T07:20:53.0092731-04:00
complete | lem:coeff, lines 492–495 | D5 average-to-supremum projection bound | 2026-10-09T07:23:24.4128418-04:00
complete | eq:predictor-moment, lines 496–503 | Predictor moment identity and coefficient uniqueness | 2026-10-09T07:32:32.3778862-04:00
complete | lem:prefix, lines 508–535 | Nested-product row, successive-jump and disjoint-interval estimates | 2026-10-09T08:06:08.5974719-04:00
complete | lem:compression, lines 553 and 569 | Extend inherited masks to the completed tree while preserving original projections | 2026-10-09T08:24:02.1251863-04:00
complete | lem:compression, line 553 | Doubling-average stopping roots, size segments and terminal cut partitions | 2026-10-09T08:47:11.4674460-04:00
complete | lem:compression, line 553 | Cut-cell averages are at most four times the segment-root average | 2026-10-09T08:49:22.6254717-04:00
complete | eq:moment-representative, lines 555–556 | Cut-supported projections onto segment-ancestor columns | 2026-10-09T08:54:01.9618301-04:00
complete | eq:moment-representative, lines 558–559 | Uniform bound and projection energy identity for moment representatives | 2026-10-09T08:58:12.3591228-04:00
complete | eq:moment-representative, lines 559–561 | Preservation of every first-layer segment projection | 2026-10-09T09:04:40.8956322-04:00
complete | lem:compression, lines 561–564 | Dyadic maximal L2 bound and square-average stopping energy | 2026-10-09T09:27:18.1036025-04:00
complete | lem:compression, line 565 | Logarithmic aggregate energy of moment representatives | 2026-10-09T09:52:57.8411587-04:00
complete | lem:compression, line 567 | Common coefficient space and cell-product representation | 2026-10-09T09:55:47.6236077-04:00
complete | lem:compression, line 567 | Coefficient anchors and finite restart attempts | 2026-10-09T10:05:12.9968656-04:00
complete | lem:compression, lines 569–572 | Refining anchor partitions and private-coordinate jump lower bounds | 2026-10-09T10:23:00.3276588-04:00
complete | lem:compression, lines 570–572 | Integrated restart-length jump budget | 2026-10-09T10:30:10.1098631-04:00
complete | lem:compression, lines 573–578 | Restart length and energy contraction ratios | 2026-10-09T10:39:00.3980632-04:00
complete | lem:compression, line 579 | Specialize numerical contraction below one half | 2026-10-09T10:49:05.5614132-04:00
complete | lem:compression, line 579 | Total attempt length and energy packing | 2026-10-09T11:04:34.5127904-04:00
complete | lem:compression, line 581 | Finite attempt-root and last-anchor assignment | 2026-10-09T11:08:49.1472456-04:00
complete | lem:compression, line 581 | Anchor row control from the nested-product prefix theorem | 2026-10-09T11:13:59.1976582-04:00
complete | lem:compression, lines 587–589 | Birth-supported columns and integrated path-budget bound | 2026-10-09T11:17:53.2464169-04:00
complete | lem:compression, lines 581–584 | Exact local coefficient-error formula | 2026-10-09T11:21:52.8936208-04:00
complete | lem:compression, lines 585–589 | Coefficient-error row estimate from the original Bessel bound | 2026-10-09T11:29:19.1331720-04:00
complete | lem:compression, lines 592–595 | Combine anchor and error rows on a fixed attempt | 2026-10-09T11:32:01.5588805-04:00
complete | lem:compression, lines 591–595 | Sum attempt packing within each size segment | 2026-10-09T11:35:05.9756521-04:00
complete | lem:compression, lines 591–595 | Sum size segments using logarithmic moment energy | 2026-10-09T11:40:16.3109986-04:00
complete | eq:compression, line 597 | Polynomial prefix constant and final depth-independent estimate | 2026-10-09T11:51:55.5962485-04:00
complete | lem:compression, lines 548–550 and 597 | Spatial compression for projection complements | 2026-10-09T12:04:59.1914717-04:00
complete | lem:compression, lines 548–550 and 597 | Fixed averages with total-variation cost | 2026-10-09T12:16:34.1914303-04:00
complete | def:chart, lines 625-637 | Quadratic chart data, atom formula, Gevrey complexity and boundedness | 2026-10-09T13:37:25.5127427-04:00
complete | def:chart, lines 635-637 | Finite lattice summands and pointwise counting | 2026-10-09T13:43:28.7736816-04:00
complete | def:chart, lines 635-637 | Zero-dimensional phases and quasipolynomial normalization | 2026-10-09T13:55:36.3709952-04:00
complete | lem:chart-operations, lines 642-660 | Complex conjugation with unchanged complexity and boundedness | 2026-10-09T13:58:52.3025486-04:00
complete | lem:chart-operations, lines 642-660 | Real dilation with unchanged complexity and boundedness | 2026-10-09T14:04:38.9497243-04:00
complete | lem:chart-operations, lines 642-646 | Block-diagonal product chart and exact atom multiplication | 2026-10-09T14:10:13.1939897-04:00
complete | lem:chart-operations, lines 642-646 | Product cutoff derivative and complexity bounds | 2026-10-09T14:17:27.8756031-04:00
complete | lem:chart-operations, lines 642-646 | Fixed finite product closure and boundedness | 2026-10-09T14:22:10.8607547-04:00
complete | lem:chart-operations, lines 646-653 | Denominator clearing and uniformly bounded offset reduction | 2026-10-09T14:25:21.9600928-04:00
complete | lem:chart-operations, lines 646-653 | Translation phase identity and exact translated atom | 2026-10-09T14:30:31.8984984-04:00
complete | lem:chart-operations, lines 646-653 | Translated phase-modulated cutoff derivative bounds | 2026-10-09T14:35:07.9833010-04:00
complete | lem:chart-operations, lines 646-653 | Uniform translation complexity and quasipolynomial budget | 2026-10-09T14:38:17.2018481-04:00
complete | lem:chart-operations, lines 642-653 | Uniform affine closure and boundedness | 2026-10-09T14:40:59.4822043-04:00
complete | Chart formula and matrix decomposition, lines 656-660 | Several-variable atoms and symmetric/skew matrix parts | 2026-10-09T14:47:46.4267765-04:00
complete | lem:sumset-growth, lines 701-728 | Ruzsa triangle and minimal-growth iteration via Mathlib | 2026-10-09T15:25:46.465143-04:00
complete | lem:derivative-graph, lines 829-835 | Large derivative Fourier coefficients and dense frequency selection | 2026-10-09T16:50:36.798414-04:00
complete | lem:derivative-graph, lines 836-841 | Squared derivative correlation identity and positive lower bound | 2026-10-09T16:54:57.007247-04:00
complete | lem:derivative-graph, lines 842-848 | First Cauchy-Schwarz step and translated square expansion | 2026-10-09T17:02:06.230740-04:00
complete | lem:derivative-graph, lines 849-855 | Second Cauchy-Schwarz step and differenced character averages | 2026-10-09T17:05:02.573430-04:00
complete | lem:derivative-graph, lines 856-861 | Character orthogonality and exact graph energy count | 2026-10-09T17:11:29.411755-04:00
complete | lem:derivative-graph, lines 822-863 | Derivative graph with density, correlation and delta-to-the-64th energy | 2026-10-09T17:15:20.758683-04:00
complete | lem:local-frequency, line 881 | Large small-difference subgraph retaining derivative correlations | 2026-10-09T17:20:48.930748-04:00
complete | lem:local-frequency, lines 883-885 | Vertical obstruction set and K-to-the-seventeenth cardinality | 2026-10-09T17:25:04.748625-04:00
complete | lem:local-frequency, line 887 | Half-density bound for nonzero character tests | 2026-10-09T17:33:29.322435-04:00
complete | lem:local-frequency, line 887 | Logarithmic separating family of character tests | 2026-10-09T17:38:11.457480-04:00
complete | lem:local-frequency, line 889 | Dense common torus cube for graph frequencies | 2026-10-09T17:41:27.854643-04:00
complete | lem:local-frequency, line 889 | Elimination of vertical obstructions and iterated graph property | 2026-10-09T17:45:57.512631-04:00
complete | lem:local-frequency, line 891 | Bohr domain with the unit frequency and small radius | 2026-10-09T17:49:05.893578-04:00
complete | lem:local-frequency, line 891 | Unique Freiman frequency map and halving in odd modulus | 2026-10-09T17:53:21.195772-04:00
complete | lem:local-frequency, lines 865-893 | Quantitative locally additive frequency with retained correlations | 2026-10-09T17:59:03.538530-04:00
complete | lem:Bohr-weight, lines 895-914 | Centered-circle weights, support and mass bounds | 2026-10-09T18:03:55.105729-04:00
complete | lem:Bohr-weight, lines 914-915 | Periodic cutoff Lipschitz and product translation bounds | 2026-10-09T18:09:54.526056-04:00
complete | lem:Bohr-weight, lines 917-925 | Weighted local-character identity and Fourier decay | 2026-10-09T18:14:35.760352-04:00
complete | lem:Bohr-weight, lines 895-926 | Complete smooth Bohr weight theorem | 2026-10-09T18:19:19.261283-04:00
complete | lem:local-symmetry, lines 951-955 | Bohr calculus, weight interfaces and admissible inner radius | 2026-10-09T18:23:17.583039-04:00
complete | lem:local-symmetry, lines 955-958 | Weighted translation localization of the initial correlation | 2026-10-09T18:26:42.848711-04:00
complete | lem:local-symmetry, lines 959-964 | First weighted Cauchy-Schwarz and square expansion | 2026-10-09T18:30:22.373470-04:00
complete | lem:local-symmetry, lines 965-973 | Alternating phase identity and change of variables | 2026-10-09T18:34:35.236630-04:00
complete | lem:local-symmetry, lines 974-977 | Weight replacement and selection of one outer parameter | 2026-10-09T18:40:39.794406-04:00
complete | lem:local-symmetry, lines 978-982 | Second Cauchy-Schwarz and averaged local Fourier correlation | 2026-10-09T18:49:21.927261-04:00
complete | lem:local-symmetry, lines 983-989 | Large local spectrum set and ordinary density | 2026-10-09T18:53:35.332763-04:00
complete | lem:local-symmetry, lines 990-999 | Local Fourier decay on the iterated spectrum difference set | 2026-10-09T18:58:12.158953-04:00
complete | lem:local-symmetry, lines 1000-1007 | Dense Bohr subdomain and refined radius | 2026-10-09T19:02:00.616408-04:00
complete | lem:local-symmetry, lines 1008-1013 | Doubling the Bohr domain and controlling the alternating phase | 2026-10-09T19:06:12.639691-04:00
complete | lem:local-symmetry, lines 951-1015 | Correlation assembly with explicit complexity cost | 2026-10-09T19:11:42.409035-04:00
complete | lem:local-symmetry, lines 1015-1016 | Logarithmic bounds for inner radius, mass and decay constant | 2026-10-09T19:16:27.238754-04:00
complete | lem:local-symmetry, line 1017 | Polynomial complexity and complete local symmetry theorem | 2026-10-09T19:20:45.754745-04:00
complete | lem:local-chart, lines 1035-1039 | Cyclic Bohr full lattice, integer sublattice and quotient map | 2026-10-09T19:32:50.336387-04:00
complete | lem:local-chart, lines 1041 | Scaled coefficient box and injective Bohr projection | 2026-10-09T19:40:07.707715-04:00
complete | lem:local-chart, lines 1043-1052 | Local additivity on coefficient paths and quadratic polynomial | 2026-10-09T19:45:55.943219-04:00
complete | lem:local-chart, lines 1054-1057 | Integral dual basis and integer linear coordinate formula | 2026-10-09T19:53:23.591614-04:00
complete | lem:local-chart, line 1054 | Supported centered lift and coefficient-box containment | 2026-10-09T19:58:25.698286-04:00
complete | lem:local-chart, lines 1058-1067 | Coefficient reduction modulo one and phase substitution | 2026-10-09T20:06:09.245399-04:00
complete | lem:local-chart, lines 1069-1076 | Rational block chart and partitioned lattice-sum formula | 2026-10-09T20:16:55.633272-04:00
complete | lem:local-chart, line 1078 | Integer values and global boundedness of the constructed chart | 2026-10-09T20:25:07.731526-04:00
complete | lem:local-chart, lines 1080-1082 | Tensor cutoff and bounded quadratic-phase derivative estimates | 2026-10-09T20:31:36.297204-04:00
complete | lem:local-chart, line 1082 | Uniform Gevrey bound for the actual doubled amplitude | 2026-10-09T20:40:24.117674-04:00
complete | lem:local-chart, line 1084 | Quasipolynomial complexity and complete local-chart theorem | 2026-10-09T20:48:31.840712-04:00
complete | thm:finite-inverse, lines 1100-1104 | Weighted translate mass and supported basepoint selection | 2026-10-09T20:54:41.974919-04:00
complete | thm:finite-inverse, lines 1104-1107 | Affine derivative frequency on the selected Bohr translate | 2026-10-09T20:56:47.026006-04:00
complete | thm:finite-inverse, lines 1109-1114 | Phase alignment and the initial local correlation | 2026-10-09T21:05:49.911267-04:00
complete | thm:finite-inverse, lines 1116-1120 | Symmetry refinement and quantitative final radius | 2026-10-09T21:09:38.705201-04:00
complete | thm:finite-inverse, lines 1122-1127 | Shift averaging, weight error and supported translate selection | 2026-10-09T21:15:18.744942-04:00
complete | thm:finite-inverse, lines 1128-1132 | Spatial localization to the two weighted variables | 2026-10-09T21:17:08.202449-04:00
complete | thm:finite-inverse, lines 1133-1146 | Skew-phase replacement and exact local polarization | 2026-10-09T21:21:25.675914-04:00
complete | thm:finite-inverse, lines 1148-1157 | Fourier extraction of weighted quadratic correlation | 2026-10-09T21:31:20.163041-04:00
complete | thm:finite-inverse, line 1159 | Translated modulated bounded chart and exact input correlation | 2026-10-09T21:36:08.443678-04:00
complete | thm:finite-inverse, lines 1114, 1120, 1159 | Common uniform quasipolynomial budget for all parameters | 2026-10-09T21:41:51.375657-04:00
complete | thm:finite-inverse, lines 1088-1159 | Complete finite inverse theorem | 2026-10-09T21:49:19.044725-04:00
complete | lem:inverse, lines 1183-1187 | Cell averages, boundedness and no-wraparound supported cubes | 2026-10-09T21:57:25.027189-04:00
complete | lem:inverse, lines 1187-1189 | Continuous supported cube Riemann sums and torus Haar identification | 2026-10-09T22:40:10.827785-04:00
complete | lem:inverse, line 1189 | Eight-factor L1 stability of bounded cube averages | 2026-10-09T22:46:03.160480-04:00
complete | lem:inverse, line 1189 | L1 contraction of cell averaging with the cyclic normalization | 2026-10-09T22:50:58.257869-04:00
complete | lem:inverse, line 1189 | Unit-bounded continuous interior approximation in L1 | 2026-10-09T22:58:58.412183-04:00
complete | lem:inverse, line 1189 | Uniform approximation and convergence for bounded measurable functions | 2026-10-09T23:04:40.289792-04:00
complete | lem:inverse, lines 1191-1195 | Selection and normalization of the finite inverse witness | 2026-10-09T23:13:58.884082-04:00
complete | lem:inverse, lines 1197 | Integer-preserving reduction of unrestricted chart parameters | 2026-10-09T23:21:20.646135-04:00
complete | lem:inverse, lines 1199-1214 | Exact floor interpolation and global boundedness | 2026-10-09T23:34:58.757115-04:00
complete | lem:inverse, lines 1214 | Uniform Gevrey complexity of the interpolated chart | 2026-10-09T23:56:35.703403-04:00
complete | lem:inverse, lines 1216 | Cell integral identity and the continuous inverse witness on intervals | 2026-10-10T00:18:30.324507-04:00
complete | lem:inverse, lines 1218 | L2 realization of the interval U3 seminorm | 2026-10-10T00:38:41.342043-04:00
complete | lem:inverse, lines 1218-1237 | Balanced convex separation and the three dual bounds | 2026-10-10T00:48:24.870995-04:00
complete | lem:inverse, line 1239 | Inverse contradiction and finite L2 decomposition | 2026-10-10T01:01:37.792154-04:00
complete | lem:inverse, lines 1173-1183 and 1239 | Probability-L2 interval normalization and general-interval decomposition | 2026-10-10T01:10:05.218436-04:00
complete | lem:inverse, line 1239 | One quasipolynomial chart and coefficient budget | 2026-10-10T01:15:13.747585-04:00
complete | lem:inverse, lines 1173-1241 | Complete continuous inverse and decomposition theorem | 2026-10-10T01:15:13.747585-04:00
complete | lem:return-splitting, lines 1265-1269 | Short-return bilinear identity, integer pairing and isotropy | 2026-10-10T01:24:38.000193-04:00
complete | lem:return-splitting, lines 1271 | Zero-dimensional short-return bound | 2026-10-10T01:30:55.935946-04:00
complete | lem:return-splitting, lines 1271-1275 | Symmetric convex return body with nonempty interior | 2026-10-10T01:35:52.287571-04:00
complete | lem:return-splitting, lines 1275-1279 | An empty interval of successive minima | 2026-10-10T01:40:59.595572-04:00
complete | lem:return-splitting, lines 1279-1281 | Isotropic span of short return lattice points | 2026-10-10T01:53:23.972865-04:00
complete | lem:return-splitting, line 1281 | Rank gap and annihilation by short dual vectors | 2026-10-10T01:56:30.407663-04:00
complete | lem:return-splitting, line 1281 | Transference dual basis spanning the orthogonal complement | 2026-10-10T02:00:10.647428-04:00
complete | lem:return-splitting, line 1281 | Dual coordinate and velocity-pairing bounds | 2026-10-10T02:03:22.340765-04:00
complete | lem:return-splitting, lines 1281-1285 | Rational slow projection with controlled height | 2026-10-10T02:08:39.251119-04:00
complete | lem:return-splitting, lines 1281-1285 | Bounded slow velocity | 2026-10-10T02:15:13.227933-04:00
complete | lem:return-splitting, lines 1287-1292 | Quantitative coordinate-axis returns by torus pigeonhole | 2026-10-10T02:19:35.514095-04:00
complete | lem:return-splitting, lines 1293-1300 | Effective quadratic identity and column bounds | 2026-10-10T02:30:17.767922-04:00
complete | lem:return-splitting, lines 1300 | Uniform quasipolynomial short-return budget | 2026-10-10T07:24:03.638469-04:00
complete | Declaration return-splitting, line 1302 | THT.Chart.shortReturnSplitting | 2026-10-10T07:32:42.178233-04:00
complete | lem:weyl, lines 1321-1331 | Exact quadratic lattice return phase and reindexing | 2026-10-10T07:38:45.645436-04:00
complete | lem:weyl, lines 1321-1331 | Uniform amplitude and localized return-error estimates | 2026-10-10T07:48:44.280954-04:00
complete | lem:weyl, line 1321 | Localized support, L1, L2 and first-moment bounds | 2026-10-10T07:56:49.141626-04:00
complete | lem:weyl, line 1333 | Fourier Lipschitz bound from the first absolute moment | 2026-10-10T08:01:13.935609-04:00
complete | lem:weyl, line 1333 | Quantitative propagation along return multiples | 2026-10-10T08:25:42-04:00
complete | lem:weyl, line 1333 | Disjoint frequency balls and Plancherel mass bound | 2026-10-10T08:44:51-04:00
complete | lem:weyl, line 1333 | Uniform return threshold and denominator budget | 2026-10-10T08:44:51-04:00
complete | Declaration weyl, line 1335 | THT.Chart.weylSplitting | 2026-10-10T08:44:51-04:00
complete | lem:chartfourier, lines 1349-1355 | Exact symmetric/skew phase extraction of the effective quadratic form | 2026-10-10T08:51:14-04:00
complete | lem:chartfourier, line 1355 | Smooth periodic functions on R^n have absolutely convergent Fourier series with derivative-controlled coefficients | 2026-10-10T08:58:39-04:00
complete | lem:chartfourier, line 1355 | Even clearing period, residue phase and slow lattice values with quasipolynomial count | 2026-10-10T09:08:31-04:00
complete | lem:chartfourier, lines 1357-1361 | Exact equality cutoff and periodic two-variable amplitude identity | 2026-10-10T09:08:31-04:00
complete | lem:chartfourier, lines 1361-1363 | Periodization in the slow variable and rescaling to unit periods | 2026-10-10T09:13:30-04:00
complete | lem:chartfourier, lines 1368-1372 | Uniform derivative bounds of the rescaled periodic amplitudes | 2026-10-10T09:25:09-04:00
complete | lem:chartfourier, lines 1363-1366 and 1372-1377 | Fourier substitution, rational frequency heights, coefficient decay, shell bounds and family count | 2026-10-10T10:20:52-04:00
complete | Declaration chart-fourier, line 1379 | THT.Chart.splitFourierExpansion | 2026-10-10T10:20:52-04:00
complete | lem:separation, lines 1401-1405 | Fixed rational coefficients and the exact quadratic/lift phase identity | 2026-10-10T10:24:56-04:00
complete | lem:separation, lines 1402-1404 | Bounded carries, exact equality cutoff and the coupled amplitude for one atom | 2026-10-10T10:35:27-04:00
complete | lem:separation, line 1407 | Product-cutoff Fourier expansion of a compactly supported smooth amplitude | 2026-10-10T10:40:13-04:00
complete | lem:separation, line 1407 | Factorization into three chart amplitudes and exact one-atom separation | 2026-10-10T10:55:36-04:00
complete | lem:separation, line 1407 | Product of the two separated atoms and normalization to bounded atoms | 2026-10-10T11:06:47-04:00
complete | lem:separation, line 1407 | Shell mass, dimension and complexity bounds of the separated terms | 2026-10-10T11:32:21-04:00
complete | lem:separation, line 1409 | Single-scale two-slot form norm bound by the Fourier supremum A_r | 2026-10-10T12:00:35-04:00
complete | lem:separation, line 1411 | Separated phase eq:separated-phase from the Weyl splitting and Fourier expansion | 2026-10-10T12:17:26-04:00
complete | lem:separation, line 1411 | Uniform separated approximation of the two-variable kernel by bounded atoms | 2026-10-10T12:53:29-04:00
complete | Declaration separation, line 1413 | THT.Chart.progressionSeparation (Lean: progressionSeparation, separated_form_le, separatedPhase, separatedKernelApprox) | 2026-10-10T13:14:38-04:00
complete | lem:von-neumann, lines 1431-1446 | Three Cauchy-Schwarz steps for the progression average on a compact abelian probability group | 2026-10-10T13:41:06-04:00
complete | lem:von-neumann, line 1447 | Integer dilations preserve Haar probability on the torus; identification with the U3 norm | 2026-10-10T13:54:24-04:00
complete | lem:von-neumann, lines 1427-1429 | Kernel Fourier expansion, distribution of characters to slots 0 and 1, modulation invariance of the L^p and U norms | 2026-10-10T14:30:12-04:00
complete | lem:von-neumann, line 1429 | Identification of the real progression form with the torus average without wraparound | 2026-10-10T14:30:12-04:00
complete | lem:von-neumann, lines 1426, 1447 | L1 two-coordinate case and extension to L2 inputs by truncation | 2026-10-10T14:30:12-04:00
complete | Declaration von-neumann, line 1449 | THT.LocalForm.vonNeumannOneL2 (Lean: vonNeumannOneL2, vonNeumann_local_L2, vonNeumann_local_L1) | 2026-10-10T14:30:12-04:00
complete | lem:detection, lines 1465-1467 | Clipping of the three opponents and the clipped-form lower bound (Lean: detection_clipping, eLpNorm_sub_truncateNorm_le) | 2026-10-10T14:52:38-04:00
complete | lem:detection, lines 1469-1471 | Two successive decompositions and a bounded atom pair with a large form (detection_structured_slot twice in detectResidual) | 2026-10-10T15:34:52-04:00
complete | lem:detection, line 1473 | Separation of the atom pair, shell truncation and the A_r lower bound (detection_atom_pair, localProgressionForm_pair_expansion, exists_large_retained_term, exists_pad_chart) | 2026-10-10T15:34:52-04:00
complete | lem:detection, line 1473 | Kernel separation and extraction of a large normalized moment of R (separated_moment_extraction) | 2026-10-10T15:17:46-04:00
complete | lem:detection, line 1473 | Quasipolynomial budget of the detection constant (QPLe calculus, detection_budget; absolute degree, q only in the coefficient) | 2026-10-10T15:34:52-04:00
complete | Declaration detection, line 1475 | THT.LocalForm.detectResidual (Lean: detectResidual) | 2026-10-10T15:34:52-04:00
complete | lem:predictors, proof line 1531 | Single-scale square function for modulated mean-zero bumps on disjoint cells (cell_bump_square_function) | 2026-10-10T15:59:41-04:00
complete | lem:predictors, proof lines 1539-1541 | Multi-scale Bessel bound from band multiplicity, lem:height and center separation (multiscale_meanZero_bessel, rational_center_multiplicity, card_le_of_one_separated) | 2026-10-10T17:17:34-04:00
complete | lem:predictors, proof lines 1521-1523 | Elementary L1 bound for bounded time modifiers, depth energy of opponents and single-phase scale sums (separatedLocalForm_sup_le, HasDepthEnergy, depth_weighted_energy_sum, single_phase_scale_sum) | 2026-10-10T17:17:34-04:00
complete | lem:predictors, proof line 1529 | Mean-zero tensor decomposition of the kernel in (y_a,y_b) (slotPairKernel_meanZero_tensor, meanZeroWave_props, admissibleKernel_fourier_weighted) | 2026-10-10T16:32:50-04:00
complete | lem:predictors, proof lines 1534-1542 | Linear-phase scale sum against admissible opponents given frequency multiplicity M (waveRow_bessel, waveRowFamily, linear_phase_scale_sum) | 2026-10-10T16:57:45-04:00
complete | lem:predictors, proof lines 1517-1542 | Core band scale sum from per-depth chart expansions: exceptional depths, clump representatives and coefficients (band plateau Fourier decay), replacement errors, catalog tails (band_scale_sum_core, clump_coefficient_le, clump_cell_bound, exists_clump_representatives) | 2026-10-10T17:41:50-04:00
complete | lem:predictors, lines 1489-1494 and proof lines 1517-1542 | eq:band-scale-sum: band scale sum e^-m C (2+m+log H)^C Ka Kb ‖1_J Fa‖ ‖1_J Fb‖ for one separated chart time factor and admissible opponents with depth energy (band_scale_sum; chart_depth_expansion, band_exceptional_depths, band_tiny_sum, catalog_tail_le, band_scale_sum_assembly, bandBracket_poly) | 2026-10-10T18:28:58-04:00
complete | lem:predictors, proof line 1533 | Square-energy and fixed opponents are admissible with depth energy (isAdmissibleOpponent_squareEnergy, isAdmissibleOpponent_fixed, hasDepthEnergy_fixed) | 2026-10-10T19:35:00-04:00
complete | lem:predictors, proof line 1532 | Current projection opponents are admissible via lem:compression (ColumnDepthFamily.current_admissible, columnSpatialCompression with one layer) | 2026-10-10T21:03:03-04:00
complete | lem:predictors, proof line 1535 | Finite predictor list eq:predictors with explicit parameters: per-cell pair expansion, band/shell/catalog discards, regrouping into (q, M, σ) (predictor_list_param, pair_expansion_cell, predictor_grouping, predictor_sum_bound, expansion_catalog_tail, weighted_shell_tail, pd_shell_budget, pd_band_budget, pd_catalog_budget) | 2026-10-10T19:35:00-04:00
complete | lem:predictors, line 1514 | Quasipolynomial budget log D_pred ≤ poly(1+B, log H) for list size, coefficient norm, complexities and |λ|r² (qp_pdCard, qp_pdH0, qp_pdLE_exp, qp_pdK0, qp_tailCT) | 2026-10-10T19:35:00-04:00
complete | Declaration predictors, line 1536 | THT.Base.finitePredictorList (Lean: finitePredictorList) | 2026-10-10T19:35:00-04:00
complete | lem:delay, lines 1549-1562 | eq:delay-telescope with dyadic conditional expectations, delayed row sums, chirp expansion of e(λt²)-1 and eq:delay-error for scalar delay data (delay_cell_telescope, delay_rows_sum, chirp_fourier, delay_error_bound) | 2026-10-10T20:43:15-04:00
complete | lem:delay, lines 1549-1553 | Column partition projections with predictor label give the delay data (ColumnDepthFamily.delayData, moment_ae, setIntegral_proj_le, increment_energy) | 2026-10-10T20:57:05-04:00
complete | lem:delay, lines 1563-1565 | Rolling differences have square energy K₀²‖1_J F‖², hence are admissible square-energy opponents (ColumnDepthFamily.rolling_energy with isAdmissibleOpponent_squareEnergy) | 2026-10-10T20:57:05-04:00
complete | Declaration delay, line 1566 | THT.Base.delayedPredictorReplacement (Lean: delayedPredictorReplacement) | 2026-10-10T20:57:05-04:00
complete | adaptive-fit, lines 1572-1574 | Greedy insertion with detection oracle and energy gain ≥ ρ²|I|/4 per insertion (fitStep, fitGreedy, fitEnergy_gain, fit_detect, FitSetup.Hyp.oracle) | 2026-10-10T21:44:13-04:00
complete | adaptive-fit, line 1574 | Nested fit ranges: energy telescoping over generations and integrated insertion mass ≤ 4ρ⁻²|J| (fitEnergy_split, fitEnergy_telescope, fitWeightedMass_le) | 2026-10-10T21:44:13-04:00
complete | adaptive-fit, lines 1574-1575 | First stopped roots cost ≤ |J|/4, restarts with total root length ≤ 4/3|J|, segment assignment, retained cells small (FitSetup.Hyp.next_length_le, roots_length_le, segment_exists, retained, inherited) | 2026-10-10T21:44:13-04:00
complete | adaptive-fit, line 1575 | Coefficient ℓ² ≤ 1 from private weight one, |g_I| ≤ √M, ‖g_I‖_(2,I) ≤ 1, bounded chart atoms (fitCoeffSq_le, Hyp.g_coeff, Hyp.g_norm_le, Hyp.phys_sq_le, Hyp.atoms_good) | 2026-10-10T21:44:13-04:00
complete | Declaration adaptive-fit, line 1579 | THT.Base.inheritedAdaptiveFit (Lean: inheritedAdaptiveFit) | 2026-10-10T21:44:13-04:00
complete | stagger, lines 1589-1594 | eq:stagger pair replacement: more accurate projection against the other's supremum, then the less accurate against the actual L^q input (StaggerCell.term_bound, repl_input, repl_bounded, FormSmall.apply_pair_bounded) | 2026-10-10T22:07:40-04:00
complete | stagger, line 1596 | Index cases u < t-4 (early slot tested against its old projections) and u ≥ t-3 (all levels ≥ t-7): full pairs ≤ 8e^(-k_(t-7)) (StaggerCell.tuple_pairSmall, early_pair, late_pair) | 2026-10-10T22:07:40-04:00
complete | stagger, line 1587 | Exact grouping at a finite cutoff into eq:base-tuple, single-increment and four-residual terms (StaggerCell.expansion via time telescoping) and remainder decay (remainder_four, remainder_one), tuple L² sizes (tuple_L2) | 2026-10-10T22:07:40-04:00
complete | stagger, lines 1581, 1596 | Accuracy schedule k_(t+1) = k_t^A, A = C+1, θ₀ = 1/(2A⁷), cyclic adaptive fits and root-length bound for unions of segment families (stagAcc, budget_le_exp, eight_exp_le) | 2026-10-10T22:07:40-04:00
complete | Declaration stagger, line 1598 | THT.Base.twoEarliestIncrements (Lean: twoEarliestIncrements) | 2026-10-10T22:07:40-04:00
complete | prop:base, proof lines 1626-1631 (opponents) | Adaptive fits packaged per attempt root as ColumnDepthFamily over Fin M (labels born at the root, private weight one, leaf-piecewise scalars, masks m < count); current projections equal the fits, hence admissible opponents by lem:compression with depth energy one (FitSetup.treeData, treeMask, depthFamily, treeProjection_eq, current_ae_fit, ColumnDepthFamily.current_ae_proj, current_depthEnergy) | 2026-10-10T22:20:16-04:00
complete | prop:base, proof lines 1626-1631 | Low-pair predictor expansion of X_i, X_k into atom pairs grouped by joint birth cells (antichain), finitePredictorList on both sides, Cauchy-Schwarz over joint births (LowList, jointBirth, predictorDelay_group, lowDelayedReplacement, sum_sqrt_energy_le) | 2026-10-10T22:53:07-04:00
complete | prop:base, proof lines 1626-1631 | High families with conjugate predictor columns (weight ε) and delayed replacement X_e → Y_e: predictor systems, low lists (fitLowList_exists with padded charts, LowList.reroot/mono/sub), replaceSlot/replaceTuple, per-pair packaging baseRoot, per-first-root baseSegments/baseFirstRoot (accurate fits rooted at the first-level root, packing 8/3|R|, explicit error baseErr), stagger wrapper baseTuple (first-level roots refining the six fit segment families, packing 64/3|J|, bottom levels by pair smallness), parameters baseParams (B_p = L², K₀ = ⌈L^{d+1}⌉, ε = e^{-L^{d+2}}, L = k^{C+2}) | 2026-10-11T04:33:37-04:00
complete | prop:base, proof lines 1634-1641 | Tuple-specific accurate high fits: AccSetup.accurateFit, pair control (YCell.Y_pairSmall with η₀ + (2+2S)(δ_a+δ_b) + (1+S_a)δ_b, so the second precision dominates the first catalog), slots4_pairSmall, accuracies k_a = ⌈L²⌉, k_b = ⌈L^s⌉ in baseParams | 2026-10-11T04:33:37-04:00
complete | prop:base, proof line 1643 | Local sizes, eq:basic-side from orthogonal rolling increments, the two-U term on one root (PathColumnSystem.rolling_cells, cur_sq_le, AccSetup.Hyp.basicSide, U_sq_le, U_eLpNorm_le, coef_le; baseRoot: Σ|I|‖U_e‖² ≤ K₀²|R|, two-U ≤ η₀K₀²|R|, sizes ≤ 1+S₀) | 2026-10-11T02:47:00-04:00
complete | prop:base, proof lines 1645-1653 | Active-scale argument eq:triple-tail: transpose identity and Cauchy-Schwarz (localProgressionForm_transpose, tripleTranspose_sq_eq, localProgressionForm_le_six: \|H_I\| ≤ ‖F_m‖ A_I with A_I = tripleNorm = (∫θΨ)^{1/2}), six-atom chart (sixChart, sixPsi_eq_sixChart), Weyl+chartfourier in three variables (mvSeparatedPhase), single-scale tiny/large estimate with the kernel marginal (sixTheta_expansion_bound), lem:height scale count (sixTheta_count_thresholds, sixTheta_scale_count, tripleNorm_count) and the dyadic summation (tripleTail) | 2026-10-11T00:46:07-04:00
complete | prop:base, proof lines 1655-1660 | Active cells and path multiplicity, inactive-cell error, eq:min-subadd reduction to eq:active-min (ActiveSetup.reduction, active_count, inactive_sum, pattern_le), instantiated with the base data (baseActiveSetup and its characterization lemmas) | 2026-10-11T04:33:37-04:00
complete | Declaration base, line 1662 | THT.Base.activeCellReduction (Lean: activeCellReduction in SecBaseReductionBaseAssembly.lean; standard axioms) | 2026-10-11T04:33:37-04:00
complete | lem:graph, lines 1680-1690 | Tags (θ_v, C_v, λ_v) (ChartTag), the edge relation at length r (tagEdge: WeylSplitData of the difference data tagDiffV, tagDiffC, tagDiffΛ), slot multiplier invariance (WeylSplitData.of_smul) | 2026-10-11T04:49:35-04:00
complete | lem:graph, proof line 1692 | Same-slot separation: translated, dilated and conjugated pure columns (quadraticChart_translation_tag, productQuadraticChart), trapezoid smoothing of the interval indicator (unitTrapezoid, integral_unitTrapezoid_error), lem:weyl at frequency zero (graph_sameSlot) and the tag form (graph_sameSlot_tag: no edge ⇒ normalized inner product ≤ τ) | 2026-10-11T04:49:35-04:00
complete | lem:graph, proof lines 1694-1702 | Distinct-slot separation (graph_distinct_core, graph_distinctSlot_tag): proved via lem:separation (exact pair expansion, time factor with matrix S_l c_l C, S_l = (l-a)(l-b)) and the single-scale bound separated_form_le, a retained term of controlled size (exists_large_retained_term), lem:weyl in one variable (weylSplit_of_oneVar), and the identity c_i S_i = -c_k S_k (slotCoeff_time_identity, from Σ c_l l^u = 0) which makes the time factor σ times the difference data; this replaces the blueprint return/Bessel argument by the already formalized separation lemma | 2026-10-11T05:07:11-04:00
complete | lem:graph, proof line 1704 | Short paths (tagEdge_path): vector form of eq:weyl-splitting (weylSplitData_iff, chartAltForm), stacked rational edge constraints on the concatenated horizontal space (stackedConstraint, mem_stackedConstraint_kernel), distance to the kernel via a rational right inverse (rational_rowSpace_projection_le), common fast components with isotropic edge corrections, telescoping of the node potentials (sum_castSucc_sub_succ), rational isotropic endpoint image (rational_restrict_subspace) and the budget exp(100000((L+1)(d+1))^8 log 2B) (shortPath_budget) | 2026-10-11T05:44:30-04:00
complete | Declaration graph, line 1709 | THT.Localization.curvatureGraph (Lean: curvatureGraph in SecCurvatureLocalization.lean, bundling graph_sameSlot_tag, graph_distinctSlot_tag and tagEdge_path with one threshold exp(D(1+log H+log τ⁻¹)^D); standard axioms) | 2026-10-11T05:44:30-04:00
complete | coloring, lines 1714-1727 | Rounds, marking and the round potential (RoundWinner, roundPot_mono, roundPot_eq); dyadic cohorts (cohortLevel, cohortPrefix, lt_cohortPrefix_of_le); profiles, clipping and the context pseudometrics d^{(l)} (prof, clipW, lowMet, lowMet_succ_le); balls and floor logarithms (ballVec, flog32, ballSel); the color data (colorData) | 2026-10-11T07:18:05-04:00
complete | coloring, lines 1728-1730 | Change counter and nonincreasing colors: lexicographic potential (pot1..pot4, potential_step), change count bounded by the potential (chgN_le), metadata encoding (metaCode, metaKey), color with counter (color, color_mem, color_anti, metaKey_eq_of_color_eq) | 2026-10-11T07:18:05-04:00
complete | coloring, lines 1732-1734 | Choice of the delays: truncated geometric weights, single-round marking probability ≥ 1/66 by the raise-the-top-scorer injection (round_unmarked_le), independent rounds (rounds_unmarked_le), deterministic ball selection (ballSel_pos), primary/high situations counted by monotone potentials along paths (ppot_anc, hpot_anc, card_situations_le), conditional union bound (chain_fail_le), averaging over the root (delays_exist), failure bound ≤ 100·2001⁷/D (failBound_le) | 2026-10-11T07:18:05-04:00
complete | Declaration coloring, line 1755 | THT.Localization.monotoneColoring (Lean: monotoneColoring in SecCurvatureLocalization.lean; d₀ = ⌈1000 log 2D⌉, L ≤ d₀^30; standard axioms) | 2026-10-11T07:18:05-04:00
complete | lem:masks, lines 1760-1762 | Use ball (mem_mask_of_dist), rival bound eq:rival-bound via the ball comparison (center_close, rival_bound), neighbor closure (mask_neighbor), short path to the winner (mask_short_path), persistence (mask_mono) | 2026-10-11T07:18:05-04:00
complete | lem:masks, lines 1767-1771 | Separation of distinct groups of one color on overlapping usable endpoints (mask_separation: earlier winner in the later frozen prefix; equal winners with distinct high winners force far historical centers, high_far) | 2026-10-11T07:18:05-04:00
complete | Declaration masks, line 1774 | THT.Localization.historicalMaskSeparation (Lean: historicalMaskSeparation; standard axioms) | 2026-10-11T07:18:05-04:00
complete | lem:whole-ranges, proof lines 1785-1788 | Analytic core (wholeRanges_core): group outputs Σ_v a_{v,G}Φ_v in ℂ ⊕ ℓ²(V), private coordinates disjoint on overlaps, cross physical pairings ≤ τ∫|a||a′|, pointwise Cauchy–Schwarz over at most N present group-label pairs and inverse weights ≤ W₀² | 2026-10-11T07:43:32-04:00
complete | lem:whole-ranges, proof line 1785 | Grid argument: combined coefficients of endpoint cells are constant on the cells of the last separating depth (pairing_of_cellwise_constant, cells_meeting_finite) | 2026-10-11T07:43:32-04:00
complete | Declaration whole-ranges, line 1791 | THT.Localization.usableRangeBessel (Lean: usableRangeBessel; hypotheses: separation depths of overlapping endpoint cells (lemma masks) and per-cell pairings at that depth (lemma graph); standard axioms) | 2026-10-11T07:43:32-04:00
complete | same-tag, line 1813 | One-term bound: plane change of variables, slot triple as convolution form, kernel Fourier expansion (slotTriple_form_le) | 2026-10-11T08:45:32-04:00
complete | same-tag, lines 1800-1810 | Exact phase transfer: discrete carry indicators mod 9, four-slot phase identity, tuple factorization, pointwise expansion into same-tag factor charts (tag_transfer_pointwise), unit-piece decomposition of the source (tag_unit_decomposition) | 2026-10-11T08:45:32-04:00
in progress | same-tag, line 1810 | Periodized source expansion with quasipolynomial coefficient mass; form assembly into sameTagTemplateTest | 2026-10-11T08:45:32-04:00
not started | Declaration closure, line 1832 | THT.Localization.catalogClosure | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration localize, line 1856 | THT.Localization.binaryGroupExpansion | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration variation, line 1879 | THT.Localization.certifiedVariation | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration first-match, line 1936 | THT.Modes.firstMatchExpansionAndLift | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration mode-schedule, line 1976 | THT.Modes.chooseSchedule | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration tiny-space, line 2000 | THT.Modes.exceptionalBlocksAndTinySpan | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration stabilize, line 2029 | THT.Modes.heightStabilization | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration coherence, line 2047 | THT.Modes.goodPredicateCoherence | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration mode-rows, line 2059 | THT.Modes.separatedProjectionRows | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration lift-composition, line 2077 | THT.Modes.composeLiftWithMainHistories | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration linear-side, line 2120 | THT.Modes.linearSideSquareEnergy | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration offset-selection, line 2157 | THT.Modes.selectOffsetsByMajorant | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration side-caps, line 2166 | THT.Modes.retainedSideCaps | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration helpers, line 2169 | THT.Localization.instantiateHelperCatalog | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration representatives, line 2194 | THT.Modes.hereditaryRepresentatives | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration component-sizes, line 2210 | THT.Modes.componentSizeComparison | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration tops, line 2231 | THT.Modes.firstTopCount | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration transfer, line 2265 | THT.Sides.transferComplementaryFilters | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration shortblock, line 2369 | THT.Sides.shortBlockComparison | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration power-costs, line 2390 | THT.Sides.threeSidePowerAndFreezing | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration fixed-stacks, line 2423 | THT.Sides.fixedStackRepresentation | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration side-estimate, line 2456 | THT.Sides.completeSideEstimate | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration common-height, line 2480 | THT.Core.firstSuccessfulHeight | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration frequency-tests, line 2585 | THT.Core.principalFrequencyTests | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration sparse-count, line 2705 | THT.Counting.sparseProgressionMass | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration tested-counts, line 2744 | THT.Core.testedTupleCounts | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration distribution, line 2769 | THT.Counting.distributionPower | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration core-estimate, line 2822 | THT.Core.poweredCoreEstimate | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration normalized, line 2904 | THT.LocalForm.normalizedAbsorption | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration uniform-local, line 2932 | THT.LocalForm.uniformEstimate | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration main, line 3010 | THT.trilinearHilbertTransform_L3_L3_L3_L1 | 2026-10-08T21:50:31.6115335-04:00
