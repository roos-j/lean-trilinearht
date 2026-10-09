# Main theorem overview

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
not started | thm:main, lines 2934–2941 | Uniform L3 trilinear Hilbert transform estimate | 2026-10-08T21:50:31.6115335-04:00
not started | thm:main, lines 2984–2992 | Pointwise principal value on Schwartz inputs | 2026-10-08T21:50:31.6115335-04:00
not started | thm:main, lines 2999–3009 | Unique bounded extension to L3 triples | 2026-10-08T21:50:31.6115335-04:00

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

The rational height bounds needed throughout the finite coefficient constructions are absent from pinned Mathlib: its rational heights, determinants and projections do not provide the required uniform counting, inverse, pivot right-inverse and projection estimates. Effective rational linear algebra via common denominators and Cramer's rule is a substantial reusable development, including real scalar extension and operator norms. The complete development moves together to TrilinearHT/Auto/RationalLinearAlgebra.lean; all statements and local definitions depend only on Mathlib. This invokes the reusable-prerequisite exception, not a split along machine-generated blueprint sections. Verified references are blueprint lem:rational-linear, lines 416–420, and the pinned Mathlib rational, matrix adjugate, rank and orthogonal-projection developments.

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

# Main proof ledger

status | exact source location | brief mathematical step | ISO 8601 timestamp with offset
--- | --- | --- | ---
complete | lem:budget-rules, lines 82–101 | Sums and products of quasipolynomial bounds | 2026-10-08T21:53:39.6248575-04:00
complete | lem:budget-rules, lines 82–101 | Positive fixed powers and compositions | 2026-10-08T21:53:39.6248575-04:00
complete | lem:budget-rules, lines 82–101 | Polynomial logarithmic bounds and parameter-uniform degrees | 2026-10-08T21:58:59.7690527-04:00
complete | lem:budget-rules, lines 82–101 | Compression overhead bound in logarithmic k | 2026-10-08T21:58:59.7690527-04:00
complete | lem:budget-rules, lines 82–101 | Domination by every positive power of P | 2026-10-08T21:58:59.7690527-04:00
complete | lem:gevrey, lines 110–114 | Quantitative derivative bounds for expNegInvGlue | 2026-10-08T22:14:53.8863812-04:00
complete | lem:gevrey, lines 116–117 | Normalized compact bump and interval cutoffs | 2026-10-08T22:24:10-04:00
complete | lem:gevrey, lines 117–125 | Locally finite partition of unity | 2026-10-08T22:24:10-04:00
complete | lem:gevrey, line 126 | Rescaling and multidimensional products | 2026-10-08T22:24:10-04:00
complete | lem:fourier-foundation, lines 130–146 | Coordinate Fourier coefficient decay | 2026-10-08T22:44:53-04:00
complete | lem:fourier-foundation, lines 134–146 | Nonzero shell counting, tails, and uniform convergence | 2026-10-08T22:44:53-04:00
complete | lem:fourier-foundation, lines 137–157 | Separated-frequency rows, multipliers, finite Schur test, and Hilbert duality | 2026-10-08T23:05:08-04:00
complete | lem:fourier-foundation, lines 143–158 | Quadratic oscillatory integral | 2026-10-08T23:10:30-04:00
complete | cube-definition, lines 162–175 | Mixed cubes, squared-face identity, positivity, nonnegative roots, and probability counting measure | 2026-10-08T23:24:00-04:00
complete | lem:finite-fourier, lines 177–200 | Signs with constant 2 sqrt(p) and double randomization | 2026-10-08T23:38:00-04:00
complete | lem:finite-fourier, lines 183–209 | Independent-copy symmetrization and sampling convolution bound with constant 4 | 2026-10-08T23:38:00-04:00
complete | lem:finite-fourier, lines 190–213 | Finite cyclic Fourier inversion, Parseval, and convolution | 2026-10-08T23:48:00-04:00
complete | lem:finite-fourier, lines 192–213 | U2 Fourier identity and U3 recursion | 2026-10-08T23:48:00-04:00
complete | lem:cube-foundation, lines 216–231 | Coordinate reflection Cauchy–Schwarz and mixed cube bound | 2026-10-08T23:55:00-04:00
complete | lem:cube-foundation, lines 218–232 | Homogeneity, triangle inequality, and bundled U3 seminorm | 2026-10-09T00:00:00-04:00
complete | eq:cube-L2, lines 223–237 | Independent vertex halves and eight L2 bounds | 2026-10-09T00:15:00-04:00
complete | lem:cube-foundation, lines 227–237 | Continuous extension to eight L2 inputs | 2026-10-09T00:24:23.8312378-04:00
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
not started | column-data, lines 470–481 | Finite private-coordinate column data and inherited masks | 2026-10-09T06:18:23.3127599-04:00
not started | column-data, lines 480–483 | Cell-supported L2 columns and finite-dimensional projection ranges | 2026-10-09T06:18:23.3127599-04:00
not started | column-data, lines 480–483 | Restriction to descendants preserves old column combinations | 2026-10-09T06:18:23.3127599-04:00
not started | column-data, lines 480–483 | Nested orthogonal projections on refining stopping partitions | 2026-10-09T06:18:23.3127599-04:00
not started | column-data, line 483 | Row-family square bound and exact decision-cell locality interface | 2026-10-09T06:18:23.3127599-04:00
not started | Declaration coeff, line 505 | THT.Columns.coefficientsAndKernel | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration prefix, line 535 | THT.Projections.nestedPrefixRows | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration compression, line 599 | THT.Projections.spatialCompression | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration height, line 619 | THT.Frequencies.heightBins | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration chart-definition, line 640 | THT.Chart.QuadraticAtom | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration chart-operations, line 654 | THT.Chart.affineAndProductClosure | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration four-paths, line 681 | THT.Additive.denseGraphFourPaths | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration BSG, line 699 | THT.Additive.energySmallDifference | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration sumset-growth, line 728 | THT.Additive.minimalGrowthIteration | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration Chang, line 764 | THT.Additive.spectrumDissociatedSpan | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration almostperiods, line 784 | THT.Additive.samplingAlmostPeriods | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration dense-Bohr, line 820 | THT.Additive.denseBogolyubov | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration derivative-graph, line 863 | THT.Gowers.derivativeGraphEnergy | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration local-frequency, line 893 | THT.Gowers.locallyAdditiveFrequency | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration Bohr-weight, line 926 | THT.Additive.smoothBohrWeight | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration local-symmetry, line 1017 | THT.Gowers.localSymmetry | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration local-chart, line 1086 | THT.Gowers.locallyQuadraticChart | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration finite-inverse, line 1161 | THT.Gowers.finiteChartInverse | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration inverse, line 1241 | THT.Chart.continuousInverseAndDecomposition | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration return-splitting, line 1302 | THT.Chart.shortReturnSplitting | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration weyl, line 1335 | THT.Chart.weylSplitting | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration chart-fourier, line 1379 | THT.Chart.splitFourierExpansion | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration separation, line 1413 | THT.Chart.progressionSeparation | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration von-neumann, line 1449 | THT.LocalForm.vonNeumannOneL2 | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration detection, line 1475 | THT.LocalForm.detectResidual | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration predictors, line 1536 | THT.Base.finitePredictorList | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration delay, line 1566 | THT.Base.delayedPredictorReplacement | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration adaptive-fit, line 1579 | THT.Base.inheritedAdaptiveFit | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration stagger, line 1598 | THT.Base.twoEarliestIncrements | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration base, line 1662 | THT.Base.activeCellReduction | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration graph, line 1709 | THT.Localization.curvatureGraph | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration coloring, line 1755 | THT.Localization.monotoneColoring | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration masks, line 1774 | THT.Localization.historicalMaskSeparation | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration whole-ranges, line 1791 | THT.Localization.usableRangeBessel | 2026-10-08T21:50:31.6115335-04:00
not started | Declaration same-tag, line 1817 | THT.Localization.sameTagTemplateTest | 2026-10-08T21:50:31.6115335-04:00
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
