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

Equivalent proof organization, recorded 2026-10-10T00:47:14.989179-04:00: lem:inverse, lines 1225-1237. Normalize a strict closed-set Hahn--Banach separation level, which is positive since zero lies in the set, instead of normalizing the supremum over the set. For the L1 dual bound test with h times measurable-set indicators, which remain in L2, instead of approximating the phase by simple functions. Set-integral comparison yields sigma*|h|^2 <= |h| almost everywhere and hence the same essential supremum bound. Both routes are Lean checked and leave all theorem hypotheses and conclusions unchanged.

## 2026-10-10T08:44:51-04:00

Conventions in lem:weyl, lines 1304-1333 (no change of mathematical content). The hypothesis sup_xi |...| >= delta is stated as "for every t < delta some xi has |F^(xi)| > t", avoiding junk values of a real supremum. "Quasipolynomial in H, delta^{-1}" is expressed as exp(D(1+log H+log max(1,delta^{-1}))^D), since delta > 1 is allowed by the source; the proof uses min(delta,1). The Lipschitz norm of theta uses the coordinate sup norm, and the box is [-R,R]^k with D depending only on the fixed Gevrey order c0 and R. The ambient dimension is restricted to 1 <= k <= 3 exactly as in the already accepted shortReturnSplitting. Proof route: instead of "first M multiples" of one return, the one-return Fourier estimate is iterated at shifted frequencies (equivalent); ball volume is bounded below by an inscribed coordinate cube; Plancherel on L1 n L2 is adapted from ../lean-dfr. Resolved; full build and standard-axiom audit pass.

## 2026-10-10T08:58:39-04:00

Equivalent proof organization for lem:chartfourier, lines 1355-1361: the printed proof splits the lattice sum into residue classes n = a mod P_0 and fixes the residue phase e(-n^T C_sy n/2). Because P_0 is even and P_0 C_sy is integral, this phase is itself invariant under n -> n + P_0 m, so it is kept inside the periodic two-variable amplitude and the families are indexed by the slow value N = P_s n alone. The family count only decreases; frequencies, heights and coefficient bounds are unaffected. No statement change.

## 2026-10-10T10:20:52-04:00

Formal conventions for lem:chartfourier, lines 1338-1377 (no change of mathematical content). The splitting hypothesis eq:weyl-splitting is used only through what the proof needs: a rational symmetric Q_s with height <= B, isotropy (1-Q_s)^T (C - C^T)(1-Q_s) = 0 and ||P_s V|| <= B (the Λ_* bound is not needed for the expansion, so omitting it strengthens the theorem). "Quasipolynomially many families with at most 2d integer indices" is an explicit finite index type ι times Z^(2d); "quasipolynomial in H,B" is exp(D X^D) with X = 1 + log H + log B, D depending only on the fixed Gevrey order, the box [-R,R]^k and k. The shell bound D_J T^(-J(d+1)^2) is stated as (shell mass) * T^(J(d+1)^2) <= exp(D_J X^(D_J)), together with the pooled pointwise envelope |a_l|(1+|l|)^(J(d+1)^2) <= exp(D_J X^(D_J)); the frequencies σ and family index are chosen before the amplitude and slow velocity, which expresses the uniform/pooled envelope assertion; the tail statement is pooled_shell_tail_bound. The zero Fourier mode is bounded separately from shells, as in lem:fourier-foundation. Resolved; full build and standard-axiom audit pass.

## 2026-10-11T09:16:09-04:00

same-tag, lines 1800-1810 (no change of statement). The exact smooth equality cutoffs imposing the carries are replaced by exact discrete Fourier sums over residues mod 9 (the carries are integers in [-4,4]); the base lifts are the source slot and an adjacent partner slot, and the source amplitude is first split into unit pieces, so templates are rho(d)e(R.d/9) with R mod 9, independent of H. The fixed templates are stated concretely (tagTemplateData), H0 = exp(D(1+log H)^D), and the conclusion is |H_I| <= H0 * |moment| for some template and linear modulation, equivalent to the blueprint moment >= t0/H0. Resolved; builds and standard axioms.

## 2026-10-11T09:41:08-04:00

lem:variation, lines 1861-1882. Formalized for positive shared products and individual ball projections; the reduction of complements and pad averages (expansion and Jensen, cost absorbed in G0) is not formalized separately. eq:whole-ranges and lem:compression enter as explicit hypotheses for the specific row families (their abstract consequences), as for usableRangeBessel. Open: instantiation from the concrete column model.

## 2026-10-11T09:59:21-04:00

first-match, lines 1891-1936. The O(δ_c) error of eq:firstmatch does not occur: the cut-off branch is an exact chart (branchChart_atom) and the expansion is the exact absolutely convergent series; truncation is left to the users. Frequencies are rational in (θ_v, θ_z) rather than (θ_v, θ_z/Q₀) (equivalent up to the clearing integer). The Gevrey complexity of the branch chart (slope 1/δ_c) is a hypothesis, not proved. Open.

## 2026-10-11T10:30:16-04:00

lem:stabilize, lines 2002-2029. Formalized abstractly (stabilize_witness, height_stabilization, stable_heights_card): K_rat is an arbitrary rational subspace with an inclusion ι of the ϑ-coordinates, L_h = 6^h, and U_S = smallKernelSpan K ι S. The expansion a = Σ_j (β_j/Q) a_j in a defining basis of the stable V_{h-R'} with common denominator Q < 2^(R'-Δ), and the size bound S_h for the cleared difference, are hypotheses (the C_* coefficient bound is not derived). The bad-height count is (2d+1)R' for heights below N, where the extra R' counts the discarded h < R'. The witness bound is 6^(R'-Δ) Σ|b_j||m_j| + n S_{h-R'}; the final comparison with E_{h-Δ} via the choice of A_0 is left to the users. Gap step (CURRENT relation ⇒ membership in K_rat) is tiny_span_closed. Open: instantiation.

## 2026-10-11T10:35:00-04:00

coherence, lines 2031-2047. The PRE/CURRENT graphs enter abstractly as height-indexed component maps (ModeComponents: self-membership, component determination, PRE ⊆ CURRENT, monotone in height); the conclusion of lem:stabilize enters as the hypothesis hstab on good primaries. The common good height uses J ≥ 2 and ⌈4δJ⌉ ≤ J; the 2δ bad proportion on the upper heights uses δ ≤ 1/16 (blueprint: implicit in the smallness of δ_*). Resolved; builds and standard axioms.

## 2026-10-11T10:40:28-04:00

mode-rows, lines 2049-2059. Formalized as its analytic components: cell_cross_pair_le (slope variation plus the existing first-derivative bound quadratic_oscillatory_integral_bound gives normalized integral ≤ 8/(θr)), fourier_sum_tail_le (coefficient sum D, tail τ), mode_combination_cross_le (finite Cauchy–Schwarz), almost_orthogonal_synthesis and rows_bessel_of_synthesis (duality). The assembled separated_projection_rows takes the cross-pair bound, overlap multiplicity and private-coordinate diagonal bound as hypotheses on the row outputs; the instantiation from the concrete (ζ^ρ)² expansion on the ϑ torus is not formalized. Constant (1 + η D³) with η = D_*^{-199} is the blueprint's 1 + D_*^{-196}. Open: instantiation.

## 2026-10-11T10:48:10-04:00

lift-composition, lines 2062-2077. compose_lift_with_main_histories: the compression of the outer main ball projection at u_e (cost C_c, with the restored average) and the insertion of the shared histories (cost C_h) enter as hypotheses in the form of lem:compression consequences, eq:whole-ranges as a hypothesis (as for certifiedVariation). The per-group Bessel bound through the fixed contractive lift and the joint Bessel bound are proved (joint_bessel_of_wholeRanges_const). Open: instantiation.

## 2026-10-11T10:48:10-04:00

linear-side, lines 2080-2120. Formalized components: the elementary first-entry fact (sum_frac_le_harmonic, sum_frac_le_log, with the sharper harmonic number H_{|S_n|}), both logarithmic telescoping bounds (sum_log_shift_le, sum_log_chain_le), the chain-length algebra eq:bad-density (chain_length_bound), and the energy assembly (linear_side_square_energy: almost-orthogonal subtotals, ε-approximation by projection rows, Bessel rows, #events·ε² ≤ B, giving Σ‖V‖² ≤ 4cB). The event/link/level construction on the block tree and the counting of failed predicate incidences are not formalized. Open: instantiation.

## 2026-10-11T10:51:29-04:00

offset-selection / side-caps / helpers, lines 2123-2169. offset-selection: physical_error_sq_le (pointwise majorant), majorant_offset_mean (pointwise offset mean ≤ 8dδ|Z|² + 2δ²K via offsetMean, with proved integrability), select_offsets_by_majorant (first moment method; the selected offset meets the mean itself, sharper than the blueprint's factor 2). The Tonelli exchange of the offset mean with the sum over used cells enters as the mean hypothesis. side-caps: rolling_side_budget (each V_b counted at most K times); the application of lem:cuts (DyadicStopping) to the integrated budgets is not re-instantiated. helpers: the universal helper part is Auto.catalogClosure, already stated for arbitrary fixed bases g; no separate declaration. Open: instantiation.

## 2026-10-11T10:54:28-04:00

representatives / component-sizes / tops, lines 2171-2231. representatives: the counting core (early_late_good_common: 9/20 + 9/10 + 9/10 > 2), nesting via the stabilization join (early_predecessor_nested, join as hypothesis), the majority intersection for consistency (majority_subsets_inter), and eq:representative-separation from one large derivative and slope variation (affine_separation_on_cell). The chronological inheritance construction on the block tree is not formalized. component-sizes: component_size_comparison (σ² ≤ 6c(‖PZ‖² + ε² + ‖V‖²) + 2η). tops: top_measure_absorb (absorption with σ² ≥ 2CD^{-50}); the Markov/first-crossing cuts over polynomially many choices reuse DyadicStopping and are not re-instantiated. Open: instantiation.

## 2026-10-11T10:57:42-04:00

transfer, lines 2239-2265. eq:transfer is proved exactly (transfer_identity) for arbitrary filters Q_{l,p} with Q_0 = 0, Q_{P+1} = 1 and any form bilinear in the two transferred slots; the band indices are shifted by one (bands p = 0..P). The retention of |p - q| ≤ 2 is transfer_near_bands, with the far-pair estimates (helper test, main test, different-tag pair estimate) entering as the hypothesis that each far pair term is at most η. The expansion of complements into 2^{O(log L)} products and the rank bookkeeping are not formalized. Open: instantiation.

## 2026-10-11T11:02:45-04:00

shortblock, lines 2275-2369. Only components are formalized: the fast-form invariance Σ m_j²/c_j = 0 (fast_form_quadratic_invariance), the pairing count behind eq:fourth-moment (pair_eq_of_sum_sq, fourth_moment_pairing: the quadruple sum surviving the w- and γ-averages is ≤ 2(Σ|a|²)²), the Hölder exponent arithmetic (shortblock_exponents), the designated-disjointness Hölder sum (position_holder_sum via sum_rpow_le_card_rpow), and the deletion bound (large_window_deletion). The rectangle partition of leaf depths, both kernel-sampling errors, the continuous comparison through eq:CN and eq:mixed-Mq, and the limiting arguments are not formalized; eq:shortblock itself is open.

## 2026-10-11T11:05:57-04:00

power-costs / fixed-stacks / side-estimate, lines 2372-2457. Formalized components: eq:three-sides (three_sides_power, via Hölder 3/(3/2), Cauchy–Schwarz and ℓ^{3p} ⊆ ℓ², sum_rpow_le_sum_sq_rpow), eq:min-power (min_le_rpow_mul), the binary prefix partition with one interval per dyadic length and exact telescoping (binary_prefix_expansion), and the pointwise hull-maxima Cauchy–Schwarz (hull_maxima_cauchy_schwarz). Update 2026-10-11 19:59 ET: eq:stack-energy is proved as a Hilbert-space core (stack_energy_linear: base plus disjoint-interval bands ≤ (1 + m² L^{2(m-1)})‖V‖²; stack_energy_rolling: exact increment split, direct term and fixed-input product jumps with J inner intervals, constant 2 from (x+y)² ≤ 2x²+2y²). The side-estimate assembly is proved in abstract form: freeze flags (freeze_flag_le), Rademacher selection for one and two independent sign families (rademacher_select, rademacher_select_two), the sparse stopping split with next roots of total length ≤ |Q|/8 (sparse_two_stacks_volume_le), and eq:near-band summation (near_band_summation, near_band_total: 7 Σ term ≤ 8 C √(AB) |R|, with pointwise joint caps). The concrete instantiation (actual stacks, hulls, configurations and the per-piece application of short_block_comparison) is carried by the prop:normalized attempt rows.

## 2026-10-11T11:07:56-04:00

common-height / frequency-tests, lines 2464-2585. common-height components: first_success_weights_sum (exact weight one via the geometric series), all_good_proportion (union bound 1 - m₀β), assignment_series_summable. frequency-tests component: the finite Schur test (schur_test) used for eq:side-windows. Not formalized: eq:core-torus-form, the torus-annihilator application, eq:Haar-four, the Fourier tests eq:four-tests and the kernel decay; open. Update 2026-10-11 20:17 ET: eq:Haar-four is proved as the all-exponents-two case of the torus eq:absolute (haar_four); the tiny/huge character averages (character_average_tiny: error ≤ |a|; character_average_huge: ≤ 2/|a|), the kernel decay near a zero by the mean value theorem and rapid decay (vanishing_decay_bound: |f p| ≤ 2^J A min(1, ‖p-p₀‖)(1+‖p‖)^{-J}), and the Hölder moment bound E Π a'_j ≤ C^{m₀} ((2δ)^n)^{1/m₀} Π σ_j (core_moment_bound) are proved. The concrete construction of eq:core-torus-form and the test functions is carried by the prop:normalized attempt rows.

## 2026-10-11T11:17:15-04:00

sparse-count / tested-counts / distribution / core-estimate, lines 2587-2822. distribution (lem:distribution) is proved exactly as stated (distribution_power, layer-cake integral with the split at t₀; constant c/(c-ε)). sparse-count components: the minimal-growth iteration |X + mB| ≤ r^m|X| re-derived from Mathlib's public Plünnecke–Petridis inequality (minimal_growth_iteration), the packing bound (packing_card_le), and eq:count-balance (count_balance_bound with constant 85). The four-step-path graph lemma, the difference covers, the small-growth scale, the slab cover and the separation argument are not formalized; eq:sparse-count is open. Update 2026-10-11 22:25 ET: lem:sparse-count is proved in full (sparse_count) with C = 3·10¹¹ and C_res = 7.2·10⁶. Route: (i) the real data are rounded to the grid 6hℤ for a step h fixed by the finite data (gridLabel, shift_round_err), with relaxed constants μ/2, 2ν, Σ/2 and gap [μR/100, 100νR]; (ii) on the grid (SparseCountData.sparse_mass_bound): counting blocks by ⌊G(s)/(τ²M²)⌋ (mass ≤ 2τ²M² instead of τ²M²), four-step paths (many_four_paths, constants ηM/3 and η⁵M³/160000), difference covers (difference_cover_of_sequences, cover_family, K₁ = 160000η⁻⁵), nonfuture pairs (nonfuture_pair_sum, side incidence), combinations keyed by block, future triple and future subsets, three mass ranges by upper-mass cuts and residue-class selection of middle scales (in place of greedy selection), the small-growth scale (exists_small_growth_scale), minimal growth with one anchor translate giving the sharper packing bound |P'| ≤ (2|P|/|B₀|)^m |B₀| (growth_packing_bound), the slab cover and separation of translated triples (triple_count_bound, column_packing_bound, translated_triples_gap), and eq:count-balance. Deviations: the per-combination bound is ρ⁷ ≤ C δ g K₁⁷ L⁶, weakened to ρ¹⁰ ≤ C δ g K₁⁷ L⁹ as in the blueprint; the logarithmic margin g = ⌈log₂(6.12·10⁸ (d+1)² ν/μ)⌉ + 1 ≤ 32ℓ replaces C ℓ. tested-counts: nothing beyond these components (pair determination, eq:triple-test, eq:total-count are open). core-estimate components: powered_count_exponents (ε = c/4 bookkeeping, 4/3, 3/4, (1-c)/2) and amplitude_factor_le_one; the Hölder product over groups and the band sums are open. Update 2026-10-11 22:40 ET: eq:powered-count (powered_count, from distribution_power), the Hölder product over groups for exponents with Σβ ≥ 1 (sum_prod_rpow_le, via weighted AM–GM after normalization), the band-sum convergence for a natural power C (band_sum_summable) and the minimum step of eq:core-final (min_sum_le_rpow, with finite subadditivity rpow_finset_sum_le) are proved. The instantiated core estimate is carried by the prop:normalized attempt rows.

## 2026-10-11T11:20:02-04:00

normalized / uniform-local / main, lines 2826-3010. Formalized components: exists_exponent_near_two (choice of q), absorption_power_bound (η^ε P^{C₄} ≤ 2^{C₄} η^{ε/2}), first_stops_length, uniform_constant_absorption (C_N ≤ 2 + 2CA), kernel_reconstruction (eq:kernel-reconstruction, proved for compactly supported ψ = φ''' with continuous compactly supported derivative), lattice_boundaries_nested, three_term_telescope. Not formalized: the attempt/restart recursion, eq:before-absorption and eq:active-final, the update-level sum, the recursive stopping in thm:uniform-local, the lattice/translate decomposition of the kernel, the principal-value limit, the L¹ duality and the Schwartz-density extension. thm:main is open.

## 2026-10-11T11:23:11-04:00

tested-counts, lines 2707-2744. Formalized components: pair determination for a 2×2 integer system with nonzero determinant (pair_determination, pair_difference_eq_zero; divisibility of the reserved shifts by the determinant is a hypothesis) and both counting bounds of eq:total-count (total_count_le, scale_count_le). eq:triple-test, the side incidence via Parseval and the application of lem:height and lem:sparse-count (eq:applied-sparse) are not formalized; open. Update 2026-10-11 22:27 ET: the side incidence via Parseval is proved (side_incidence_count: disjoint windows each with normalized Fourier mass ≥ σ² number at most |I|⁻¹‖S‖²_I/σ², from Mathlib's hasSum_sq_fourierCoeffOn); eq:applied-sparse is the statement of the proved lem:sparse-count (sparse_count). The instantiation (representative values, eq:triple-test from eq:four-tests, lem:height for L₀) is carried by the prop:normalized attempt rows.

## 2026-10-11T11:29:42-04:00

thm:main, lines 2984-2992 (principal value). Proved for Schwartz inputs (SchwartzMap ℝ ℂ) in the form: for every real x the symmetric truncations ∫_{|t|>ε} f₁(x-t)f₂(x-2t)f₃(x-3t) dt/t (thtTruncated) converge as ε → 0⁺ (thtTruncated_tendsto). Resolved; standard axioms. The L¹ bound and the unique L³ extension remain open.

## 2026-10-11T11:35:58-04:00

thm:main, lines 2999-3009 (extension). Proved as an implication: any trilinear Schwartz-to-L¹ operator with ‖T(f)‖₁ ≤ C Π‖f_j‖₃ has a unique bounded trilinear extension to L³ with the same bound (schwartz_L3_unique_extension, via trilinear_dense_extension). Route change: Mathlib's LinearMap.extendOfNorm, applied one variable at a time, replaces the explicit Cauchy-sequence argument; uniqueness is by density. The L¹ bound itself (lines 2934-2941) remains open, so the extension of the trilinear Hilbert transform is not yet instantiated.

## 2026-10-11T12:01:34-04:00

thm:uniform-local, lines 2906-2932. Proved as an implication: NormalizedAbsorption (prop:normalized as a hypothesis on FiniteDepthLocalData, normalization on all hull cells between the root and the used cells) at every N with fixed A, c and (4/3)16^{4/q} c ≤ 1/2 gives C_N ≤ 2 + 2(4/3)16^{4/q} A (uniform_local_of_normalized). Route changes: the recursive restart on stopped roots is replaced by stopping generations and the deepest stopping ancestor of each used cell; vanishing root sizes are handled by the limit ε → 0 of the normalized bound for f/(b + ε) instead of the vanishing-form argument; local L^q norms use closed intervals and cells are half-open (equal a.e.). Roots are the depth-firstDepth cells. prop:normalized itself remains open.

## 2026-10-11T12:32:08-04:00

thm:main, lines 2970-2974. The derivative bound is proved with the explicit admissibility constant C = 3C₀ + 34 + D (rescaledW_derivative_bound) from Gevrey bounds ‖g⁽ʲ⁾‖ ≤ (C₀(j+1))^{C₀(j+1)} for both factors ω and φ, in place of the blueprint's D^{u+1}(C(u+2))^{C(u+2)} (equivalent after absorbing D). The Gevrey bound for φ = S³χ(S) is not yet instantiated.

## 2026-10-11T12:48:27-04:00

thm:main, lines 2966-2970. Admissibility is proved for a fixed kernel class with margin μ and derivative constant 3C₀ + 34 + D (rescaledW_admissible), with the cell given by any c whose μ-interior contains the coordinate interval [a(m₀-1-3R), a(m₀+1+3R)]; the cell choice uses two of the three lattices (exists_lattice_cell_with_margin, margin r/24 when the interval length plus r/12 is below r/3). φ = S³χ(S) Gevrey bounds: cubic_cutoff_gevrey. Not yet done: identifying the three lattices with RealDyadicGrid instances (origins r_s(σ_s j/3)) and the bounded number of translates per cell; these enter the next row.

## 2026-10-11T12:58:35-04:00

thm:main, lines 2957-2976. Proved for each fixed b > 0 and every finite set of scale-translate pairs (n, m) in N consecutive scales: Σ |∫ a⁻¹W(x/a - m, t/a) Π f_j(x + jt)| ≤ 3(D+1) C_N ∫ Π M_q f_j for the fixed class with margin 1/24 and derivative constant 3C₀ + 34 + D, provided D > 8 + 24R (truncated_scale_sum_bound). Departures: the blueprint's three lattices are realized by interlacedGrid with base length D b at depth -n; all three lattice indices j ∈ {-1,0,1} are summed (factor 3 instead of selecting two); the bounded translate families are produced by peeling one representative per cell (factor D + 1). The progression variable uses x + jt (blueprint's form after t ↦ -t). The integration in b and the sum over all translates are not yet done.

thm:main, lines 2934-3009, recorded 2026-10-11T13:53:48-04:00. Proved as an implication from thm:uniform-local in the form "every admissible class has some q ∈ [2,3) with sup_N C_N(q) < ∞" (tht_main_of_uniform), and from prop:normalized via uniform_of_normalized. The principal value is the explicit odd-part integral thtPV (limit of thtTruncated, thtTruncated_tendsto_thtPV). Route: ω = gevreyPartition, φ = S³χ with χ = gevreyIntervalCutoff(-2,-1,1,2) (even by its formula), φ'''(0) = 6, D = 57, R = 2. The scale integral is split at the dyadic points a = b 2ⁿ by an exact lintegral change of variables on [2ⁿ, 2ⁿ⁺¹) (setLIntegral_Ico_scale), with the weight db/b bounded by db on [1,2) instead of integrated to log 2. The scale limit takes A = 1/n, B = n along integers; the kernel is used in the explicit form (ψ(nt) - ψ(t/n))/t and the dominated convergence runs on ℝ² after pairing t with -t through the measure-preserving reflection. Inputs are truncated to [-(T+3Rn), T+3Rn] (all four, which leaves the form unchanged since the kernel vanishes for |t| > Rn) to meet the compact-support hypotheses of the finite-depth constant. Duality uses the test 1_[-n,n] conj(T)/|T| and monotone convergence over n; T is uniformly bounded and measurable (thtPV_bound, thtPV_measurable). The trilinear L¹ operator is built from thtPV and extended by schwartz_L3_unique_extension. Standard axioms. Remaining: prop:normalized (and through it the open §12-§15 assemblies listed above); thm:main is not proved unconditionally.

lem:shortblock, lines 2302-2326, recorded 2026-10-11T14:28:54-04:00 (equivalent organization). The fast variables are kept on the unit cell [0,1)² (latticeSampled_form_lift) and the fast circle of length 16 enters only through trigonometric polynomials e(m w/16); eq:fourth-moment (fast_fourth_moment) and the invariance of the fast form (fast_form_invariance, fast_form_eval) are proved for finite Fourier sums, with γ ∈ [0,3) and c = (-1,3,-3,1). The passage to general L² fast data is deferred to the end of the lemma, using continuity of the fast form in L² (the torus case of eq:absolute) exactly as the blueprint's closing limiting remark (line 2369).

lem:shortblock, lines 2302-2369, limiting route, recorded 2026-10-11T16:40:24-04:00 (equivalent organization). All multiplied-picture estimates (fourth moment, deletion, interval comparison, mixed Hölder) are applied to the Fourier partial sums S_N F_j(n, ·) of the fast windows on the circle of length 16, with ‖S_N F‖₂ ≤ ‖F‖₂ = e(n) uniformly in N. The only quantity passed to the limit N → ∞ is the fast lattice-torus form Φ, which is unchanged by the multipliers and continuous in L² of each slot (latticeTorus_eLpNorm_bound at exponents (2,2,2,2)); S_N F → F in L² (Mathlib hasSum_fourier_series_L2). This replaces the blueprint's "difference version of eq:fourth-moment" limit at line 2369 with the same conclusion.

lem:shortblock, lines 2276-2283, recorded 2026-10-11T19:43:38-04:00 (statement choices, resolved). short_block_comparison proves eq:shortblock with exponent 1 on (1+log(K+2)) (stronger than the unspecified C). The randomization hypothesis is used only at the fourth moment (the only finite moment the proof uses); the inputs may take values in any normed group (only norms enter); the support-on-R hypothesis is not needed (all forms are localized to internal cells inside R) and is omitted. These make the Lean statement stronger than the source. The tree piece is the structure ShortBlockTree (disjoint leaves inside and covering R; internal cells meeting a leaf are strictly coarser). The heavy slot of a repeated-minimum rectangle is its least attaining slot; no clipping of random values is performed, as in the source.

## 2026-10-11T23:50:00-04:00

prop:normalized, attempt construction (lines 1800-1882 applied in the proof, lines 2838-2840). Finding: `ActiveSetup` (prop:base output, SecBaseReductionBaseAssembly.lean) records each basic argument only as per-cell coefficients times chart atoms, plus sides U with per-cell size bounds. The attempt needs more of the prop:base data: the catalog tests (eq:catalog-test) and certified variation (eq:variation) act on "a fixed signed sum of averaged products of main projections acting on F_l" (line 1859), with the energy ‖1_R F_l‖² ≤ C|R|, and with B_l a difference of at most two current basic projections (prop:base, lines 1611-1613), and the basic sides need eq:basic-side (Σ|I|‖U_{e,I}‖² ≤ C(1+K₀)²|R|). Plan revision: extend the active setup with a column-system representation of the basic arguments (column tree data on the tree below R, inherited masks, inputs F_l in ColumnL2 with root energy bound, B_l(I) = physical part of a difference of two depth projections on I) and the basic-side energy, established from the base construction (Pa/Pb high systems, low lists, accurate fits) where these quantities already exist. Open.

## 2026-10-12T00:31:50-04:00

Resolution of the 2026-10-11T23:50 finding. `IsFitOpponent` now also exports the projection form of each opponent (a column depth family rooted at the attempt root on the same grid, applied to F = 1_J f; blueprint line 1570, g_I = P_I F). `BasicProjection G R CF` (column depth family whose root contains R, augmented input with ∫_R ‖Z‖² ≤ CF|R|, value = physical part of the current projection) and `ActiveSetup.HasColumnRep CF` (each B_l is a.e. on every cell the difference of two basic projections; blueprint lines 1611-1613) are proved for every setup of `activeCellReduction` with CF = 1: low slots are g_u − g_{u−4} (or g_u − 0), high slots are the current high-system projection of Sa.Z minus the previous fit. The basic-side energy eq:basic-side was already part of the conclusion. Resolved; full build, standard axioms.
- 2026-10-12 04:17 ET, implementation (prop:normalized, blueprint lines 1805-1809): the attempt catalogs (`catProj`) use fresh template columns only, whereas the blueprint's rank-r main projections also contain the original (rank-0) basic columns of the mask. The localization (`attempt_localization`) is proved with fresh-only catalogs; for the downstream compression/variation arguments the catalog projections are transported into a column tree whose labels are basic ⊕ fresh with separate masks (instructions.md, row 2b). Resolution in progress.

## 2026-10-12T10:05:00-04:00

prop:normalized, certified variation and whole ranges on the attempt (lem:variation, lem:whole-ranges applied at lines 1859-1867, 2066-2072, 2149). Finding: the rolling histories `Z_{l,G,s}` are evaluated at all depths between the decision depth and the used cells, and the whole-range separation (lem:masks) is only available at admission cells of the attempt (`ActiveSetup.cells`). The formal `ActiveSetup.cells` is an arbitrary finite set of cells below `R`; the arguments need it closed under ancestors below `R` (the hull of the used cells), so that every endpoint of a depth interval containing a certified use is an attempt cell. Plan: (1) use the ancestor closure as a hypothesis in the variation/side-cap statements; (2) establish it for the setups produced by `activeCellReduction` (segments of the stopping decomposition are convex below their roots) when the attempt is assembled. Open.

## 2026-10-12T13:32:53-04:00

prop:normalized, summing the update levels and the cutoff limit (lines 2893-2904), with prop:base (lines 1643, 1655). Two findings for the final assembly of `NormalizedAbsorption` from `activeCellReduction`:

1. Initial levels. `activeCellReduction` produces active setups only for update pairs `u < t` with `12 ≤ t` (where pair-smallness holds). The blueprint also needs the finitely many initial levels `t < 12`: there the same base reduction runs without the `η` factor, and the active-scale argument (eq:triple-tail with path multiplicity `D_base^C`) gives a depth-independent bound `Σ_I |I| |H_I(tuple u t)| ≤ A |J|` (line 1655: "the finitely many initial levels have fixed budgets and so a depth-independent bound"). No Lean statement covers these levels yet. Plan: a variant of `activeCellReduction` for `t < 12` with `η` replaced by a fixed bound and the active cells' multiplicity, then the trivial four-`L²` bound on active cells.

2. Normalization on the tree. `activeCellReduction` assumes `‖f_p‖_{q,I} ≤ 1` on every cell of `dyadicFiniteTree G J N`, while `NormalizedAbsorption` (as consumed by `uniform_local_of_normalized`) only gives it on `dyadicHullCells` (cells containing a used cell). Descendants of used cells that contain no used cell are unconstrained. Plan: either prove the base reduction on the hull subtree (stopping decomposition restricted to hull cells), or strengthen the hypothesis of `NormalizedAbsorption` to all cells of the finite tree below the root up to the deepest used depth and re-derive `uniform_local_of_normalized` (its stopping argument normalizes on the whole intervening subtree, blueprint lines 2912-2916, which is a full subtree minus the stopped subtrees, so a second stopping step at the used depth is needed). Open.

Resolution of finding 1 (2026-10-12 14:08:38 ET): baseTuple now holds for every update pair 1 <= u < t (slots without a previous update use the empty low list and an a.e. zero opponent); activeCellReduction takes any pair bound eta0 >= e^{-2 k^theta0} of the tuple as a hypothesis and exports 1 <= H; pairSmall_trivial gives the fixed bound 4 C_kappa for the initial levels, and ActiveSetup.total_le / setups_total_le give the depth-independent bound W * Phi(E, eta0, X) (reduction + active_count at delta = 1/2). Finding 2 remains open.

Resolution of finding 2 (2026-10-12 14:53:34 ET): the base reduction now assumes the L^q normalization only at the root and on the kernel hull (tree cells containing a cell with a nonzero kernel; the zero kernel is admissible, so unused cells carry w = 0). kernelHull is threaded through FitSetup/AccSetup (insertions only happen at hull cells), IsAdaptiveFit (per-cell bounds on hull cells), IsBasicOn (energies on hull cells), fitLowList, baseRoot/baseSegments/baseFirstRoot/baseTuple (active setups contain only hull cells) and activeCellReduction. NormalizedAbsorption only normalizes dyadicHullCells, which contain the kernel hull.

## 2026-10-12 16:36:01 ET

prop:normalized, sides on the attempt (blueprint lines 1859-1867, 2120-2160: "for a basic B slot, B_{l,s}B_l is a fixed signed sum of averaged products of main projections acting on F_l"; "original labels have rank zero", line 1805). Finding: the attempt (AttemptParams, attempt_localization) feeds each cell its own input `cellLp A.G I (ap.z I l)`, whose basic arguments B_l(I) have cell-dependent coefficients, while the global history lemmas (globOut, attempt_variation, attempt_rolling_variation, attempt_side_caps, attempt_linear_side via hfrozen) take one global input z. No single z restricts to every cell input, so the rolling sides Z_s - Z_{u_b} of the actual leaf outputs are not covered by eq:variation as formalized. This is the open 04:17 item (basic + fresh column tree). Plan: (1) by linearity split each basic slot input B_l = P1.val - P2.val (HasColumnRep, a.e. on cells) and bound energies of each piece separately (energies are subadditive; the decomposition Z = A + S + E stays on the whole output); (2) for one BasicProjection (family Psi on V, input Z) build the combined column depth family on V + Fin Mc (basic labels with the mask of Psi, catalog labels with the inherited catalog masks), prove that catalog projections ignore basic private coordinates, and that the cell-local leaf output with input cellLp (P.val I) is the restriction to I of the global output whose innermost factor is the rank-0 basic projection at depth I.1 applied to the embedded Z; (3) re-run the variation/side-cap arguments on the combined family with the extra innermost layer. U slots are mandatory sides and need no variation. Open.
Resolution (2026-10-12 17:20:45 ET, without a combined tree): the basic input of the cells of depth h is the physical part of the depth projection P_h Z of a basic family (ColumnDepthFamily.restrict_physEmbed_proj, leaf_ball_eq_globOut); the fixed-input attempt lemmas are used as Bessel row bounds and the rank-zero factor is inserted by the basic family's own compression (basic_insert, basic_variation, globOut_joint for the jump term with constant 1 + tau N, not the group count). Proved: attempt_variation_basic, attempt_rolling_variation_basic, attempt_event_rows_basic, attempt_linear_side_basic, side_caps_of_rolling. Resolved for variation, rolling sides, linear sides and side caps; slots with B = P1 - P2 use linearity.

## 2026-10-12T21:38:14-04:00

first-match / eq:gauge-cancel (blueprint lines 1938-1944), with sec:core line 2479 (R_z). The blueprint enlarges the true branch cutoffs to cutoffs equal to one on their supports and zero at the cuts, so that the four-slot gauge product is a smooth periodic multiplier. In the formalization the true cutoff `branchProfile δ = gevreyIntervalCutoff 0 (2δ) (1-2δ) 1` is positive on the whole open branch region (0,1) and vanishes (to infinite order) only at the cuts, so no smooth enlargement equal to one on its support exists. Planned repair (proof-route change, no change of any main statement): use enlarged cutoffs `branchProfile δ''` with δ'' ≪ δ; off the layers fract < 2δ'' or > 1-2δ'' the carry identity (gauge_cancel) holds exactly with the enlarged cutoff equal to one, and on these layers the true cutoff is Gevrey-small, giving a uniform additive error that is made ≤ D_*^(-300) by the choice of δ''; the multiplier's derivative and Fourier costs are polynomial in 1/δ'' and absorbed in D_*. Status: open (to be proved in the first-match row).

## 2026-10-12T22:08:54-04:00

Resolution of the eq:gauge-cancel cutoff entry above (blueprint lines 1938-1944, 2479): proved with the thin enlargement. gaugeMult (cutoff parameter δ'') is smooth (gaugeMult_contDiff), 1-periodic in (ϑ y_l', ϑ t) (gaugeMult_periodic), bounded by one, with offset-uniform derivative bounds (gaugeMult_deriv_le) and Fourier truncation (gaugeMult_truncate); gauge_factors_eq_mult shows the four true cutoffs times the gauge phases equal the true cutoffs times gaugeMult up to 8 d δ'' profR δ 1 (first-order layer bound from branchProfile_le_edge). The blueprint's exact identity on the true supports is replaced by this additive error, chosen negligible via δ''. Standard axioms only.
- 2026-10-14T03:16:14-0400: LEDGER DISCREPANCY (not a source error): automation/Status.md overstated completion for 51 rows in lines 2464-2904 (components marked complete while their attempt-level hypotheses were unverified). Resolved by downgrading to in progress (PARTIAL); a full audit of the remaining complete rows is open.

## 2026-10-14T03:50:08-04:00

Full audit (Status.md rebuilt from scratch at 2026-10-14 03:49:26 ET). Formalization gaps that keep rows in progress or not started. These are Lean mismatches, not source errors, unless marked otherwise.

1. lem:budget-rules, line 83. The q-uniform clause (coefficient C_q, exponent fixed independently of q) is not stated, because QuasipolynomialBound hides its degree under an existential.
2. lem:chart-operations, line 651. The translation calculation for several-variable charts with real linear V: R^k -> R^d has no Lean counterpart.
3. lem:chartfourier, lines 1349 and 1377. splitFourierExpansion gives the envelope for one splitting only. The sum over all splittings of height <= B and the count B^(C(d+1)^2) are missing.
4. lem:separation, line 1383. progressionSeparation assumes chart dimensions d, e >= 1, but def:chart allows d = 0. The padding exists_pad_chart is applied only inside detection_atom_pair.
5. prop:base, lines 1600-1607. activeCellReduction has the error e^-k (64/3)|J| + eta0 k^Cb |J|, because the bottom K0 levels are bounded by pair smallness, not replaced. The blueprint states C e^-k times the root length. The inverse private weights of the basic projection families are not exported.
6. Global budgets (lines 1835, 1859, 1861-1879, 1932, 1934, 2062-2077, 2080-2118). The following are counts over the whole attempt tree, not the path counts of eq:columnbudget:
   - catTree sets the catalog column budget to max 2 M_c, where M_c counts all retained cells;
   - attemptLift sets eps_m from the global mode count;
   - level_rows, class_rows, linear_budget and cell_component_sizes use card Md.
   Every compression constant, and every bound depending on D_*, then grows with the size of the tree. This is the main structural blocker; see item 13.
7. lem:closure, lines 1820 and 1828-1830. At attempt level, n_r and Tmax come from exists_prefix_fixed with no bound in k.
8. Catalogs, line 1805. catProj contains only fresh same-tag templates. The rank-0 original columns of the blueprint catalogs are inserted separately by basic_insert. This is the deviation recorded at 2026-10-12T04:17, still open.
9. eq:offset-mean, lines 1895-1901. branchProfile = gevreyIntervalCutoff 0 (2 delta) (1 - 2 delta) 1 is positive on (0,1). The blueprint cutoff vanishes within delta_c of each branch cut. This is why gauge_factors_eq_mult holds only up to 8 d delta R_delta (line 1944).
10. Line 1967. The retention rule for v_b-cells ("retain only if a descendant actual use occurs in the block") is not defined: LeafSplit.cells is a free field.
11. lem:stabilize, coherence and representatives (lines 1996-2044, 2172-2185, 2466).
    - hstab_of_primaryGood is never instantiated, and its numeric conditions are never derived from ModeSchedule.Valid.
    - The exceptional-block count is about 2(3H^2)^d, not C d_max.
12. sec:sides and sec:core leaf statements (lines 2252-2456 and 2461-2822).
    - Inputs are hypotheses (caps, budgets, test passes, AncClosed, CellCoreData, TorusData, ThreeData).
    - CellCoreData.hRb bounds the truncated multiplier for every coefficient vector, which forces W >= |box|; the blueprint needs the uniform sup of the specific R_z.
    - core_leaf_split excludes three-core patterns with a basic U side.
    - near_sum uses C_K rather than C_N.
13. sec:completion, lines 2839-2866. The coloring uses vertex bound 4|L|+1 (vtxBound) instead of D_base, so the failure fraction is not small. eq:before-absorption, the degree bounds and RetainedMin are unproved.

## 2026-10-14T04:04:36-04:00

lem:budget-rules, blueprint lines 82-99. Departures in TrilinearHT/Auto/QuadraticCharts.lean. All concern domains or edge cases; none is a source error.
1. Line 82 says a "positive quantity". `QuasipolynomialBound` (:38) and `QuasipolynomialBoundOfDegree` (:200) require only `0 <= f t`.
   Reason: this is more general; zero values (for example empty sums) are allowed.
2. Line 83, "compositions preserve" the bound. `quasipolynomialBound_comp` (:169) and `QuasipolynomialBoundOfDegree.comp` (:302) assume the inner function takes values >= 2 for t >= 2.
   Reason: the definition bounds the outer function only for arguments t >= 2. Without this domain condition the printed rule has no meaning and is false.
3. Line 83, polynomial bounds in the logarithms. `polynomial_majorant_add/_mul/_comp` (:4699, :4710, :4720) are pointwise. They assume the logarithmic size u >= 1 (true for t >= 2), nonnegative coefficients, and nonnegative quantities.
   Reason: these are the source's positivity conventions, made explicit.
4. Lines 85-89. `compression_overhead_bound` (:4611) was restated at this time; its old hypotheses k >= 2, D >= 1, A >= 1 and C >= 1 are removed.
   - k and the coefficient A are arbitrary reals.
   - m is a natural count.
   - The fixed constants are positive (0 < B, 0 < C). The source uses the same letter C for the bound on m and for the bound on F; Lean allows two separate constants, which is more general.
   - The only added hypothesis is 1 <= 2D. Reason: this is exactly when the printed real power (C(m+1) log(2D))^(C(m+1)) has a nonnegative base. For 2D < 1 the source expression is undefined, and the Lean statement would be false.
   - d' = 2, absolute.
5. Line 89. `fixed_power_eventually_le_ceiling_power` (:4730) now allows every real power p; the old hypothesis 0 <= p is removed.
   The parameter k ranges over the reals (atTop), which is more general than the source.

## 2026-10-14T05:35:26-04:00

Departures in complete rows before blueprint line 651 that were not yet logged. All are minor conventions or edge cases; Lean locations are in TrilinearHT/Auto after the 2026-10-14 file reorganization.
1. lem:absolute, lines 384-385, torus variant: "a connected torus". `rationalTorus_absoluteBound` (Sec03LocalFormsFiniteConstants.lean:815) states it for rational annihilator subtori of (R/Z)^d with Haar probability measure.
   Reason: these are exactly the closed connected subtori of the standard torus (lem:torus-annihilator, lines 347-358), the only tori on which the blueprint later uses the estimate (eq:Haar-four, line 2498).
2. lem:absolute, line 385, lattice variant ("normalized at its scale, kernel bounded and supported in a fixed scale-sized box"). `integerProgression_absoluteBound` (Sec03LocalFormsFiniteConstants.lean:994) takes the scale N > 0, supports of cardinality at most B*N, the normalization N^-2, and constant B^2 W.
   Reason: this is a precise reading of "a fixed scale-sized box".
3. lem:chart-operations, lines 642-650.
   - Affected declarations, all in Sec05QuadraticCharts.lean: `productQuadraticChart_complexity` (:827), `finiteQuadraticChartProduct_complexity` (:913), `translatedChartAmplitude_derivative_bound` (:1249), `quadraticChart_translation_closure` (:1418), `quadraticChart_affine_closure` (:1438).
   - Departure: these assume the Gevrey order satisfies c0 >= 1.
   - Reason: an unimportant edge case. For c0 = 0 the bound of def:chart (lines 633-635) is ||∂^α χ|| <= 1 for all α. A compactly supported smooth χ with this bound is analytic and hence zero, so the class is trivial.
4. lem:compression, line 550, averages. `columnSpatialCompression_averages` (Sec04ColumnProjections.lean:4163) assumes AE strong measurability of the averaged integrand.
   Reason: this is the well-definedness condition for the Bochner average that the source writes.
5. Cube forms and lem:cube-foundation, lines 163-174 and 216-236.
   - `cubeAverage` (GowersCauchySchwarz.lean:88) integrates h outside x. This equals the printed iterated expectation by Fubini for bounded measurable inputs.
   - `gowersThreeSeminorm` (GowersCauchySchwarz.lean:732) is the U^3 seminorm on bounded measurable functions, the source's domain. It is extended to L^2 by the continuity statement eq:cube-L2.
