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

## 2026-10-14T05:43:41-04:00

lem:chart-operations, blueprint line 651 ("The same calculation works with any real linear map V: R^k -> R^d in place of y -> theta y").
- Formalized in TrilinearHT/Auto/Sec05QuadraticCharts.lean:
  - `chart_lattice_sum_translate` (:1562): the translation calculation of lines 646-650 at an arbitrary horizontal position.
  - `mvTranslateChart_atom` (:1680): the translate of a several-variable chart.
  - `mvLinearChart_atom` (:1726): linear substitution.
  - `multivariableQuadraticChart_affine_closure` (:1750): every real affine substitution z -> M z + z0 of a several-variable chart is again such a chart. The complexity bound chartTranslationBudget H is independent of M and z0, and boundedness is preserved.
- Departure: the Gevrey order must satisfy c0 >= 1, as in the one-variable closure. This is the same unimportant edge case as entry 2026-10-14T05:35:26 item 3: for c0 = 0 the chart class has only zero amplitudes.
- Organizational change: `MultivariableQuadraticChartComplexity` and `multivariableChartAlongLine_complexity` were moved from Sec09_1 back to Sec05. They are part of the several-variable chart definition (lines 656-660) and are needed here.

## 2026-10-14T06:07:00-04:00

lem:chartfourier, blueprint line 1349 with the pooling step of the proof, line 1377. Formalized as `splitFourierExpansion_pooled` (TrilinearHT/Auto/Sec09_2ChartFourierSeparation.lean:2850). Precise reading of the wording, not a change of content:
- "the coefficient envelope pooled over all splittings of height at most B": S is exactly the finite set of rational symmetric splittings of height <= B that satisfy eq:weyl-splitting's isotropy. It has at most (3B^2)^(d^2) <= exp(3X^3) elements.
- "uniformly over the allowed amplitudes and bounded slow values": a single envelope env J l, depending only on the integer index l, dominates every coefficient of every splitting in S, every family, and every admissible chart (matrix C, complexity H, slow velocity <= B).
- The pooled shell mass, summed over all splittings and families, is at most exp(D_J X^D_J) T^(-J(d+1)^2), and the pooled tail is <= eps once 2^K >= 2E/eps, with 2^K <= max 1 (4E/eps).
- "separately for each resulting frequency and quadratic part": this is a regrouping. The envelope of a coefficient obtained by summing terms with the same frequency and quadratic part is at most the sum of their envelopes, so every grouped shell and tail bound follows from the per-term bounds above.

## 2026-10-14T06:27:50-04:00

Resolution of the eq:separation gap, lem:separation, blueprint lines 1382-1388. Item 4 of entry 2026-10-14T03:50:08: progressionSeparation required chart dimensions d, e >= 1.
- `progressionSeparation_all` (TrilinearHT/Auto/Sec09_2ChartFourierSeparation.lean:7725) proves eq:separation for charts of every dimension d, e >= 0, as def:chart allows.
- Proof: both charts are padded to positive dimension by `exists_pad_chart` (:5050), which does not change their atoms. Then `progressionSeparation` is applied, and the padded budget X' = 1 + log(max(H, W0)^6) <= N X is converted back into a quasipolynomial in X = 1 + log H.
- The conclusion states the blueprint's items explicitly:
  - exact absolutely convergent expansion;
  - bounded factor atoms fixed independently of scale;
  - total mass <= D;
  - shell tails <= D T^-100;
  - factor dimension <= log D;
  - factor complexity <= (D T)^6 at a fixed Gevrey order;
  - in addition, a count of terms per shell.
- Generalizations, not restrictions: the atoms need not be bounded, and the slots are any integers of absolute value <= 3 with a != b.
- Organizational change: `quadraticChartComplexity_order_mono`, `exists_unit_chart` and `exists_pad_chart` (chart operations) were moved from Sec10Detection to Sec09_2, before their new consumer.

## 2026-10-14T06:46:31-04:00

lem:von-neumann, blueprint lines 1419-1426: "b, c in L^infty(I)".
- Gap found while checking complete rows strictly: `vonNeumannOneL2` assumed pointwise bounds ||b(y)|| <= M_b and ||c(y)|| <= M_c for all y in I. That is a stronger hypothesis than b, c in L^infty(I).
- Resolved by `vonNeumann_essSup` (TrilinearHT/Auto/Sec10Detection.lean:2399): |H_I(R,g,b,c)| <= C ||R||_(2,I) ||g||_(U(I)) ||b||_infty ||c||_infty, where ||.||_infty is the essential supremum on I and C depends only on the kernel class.
- Proof: b and c are replaced by their truncations at the essential supremum. These agree with b and c almost everywhere, so the form is unchanged by `localProgressionForm_update_congr_ae`; then the pointwise version applies.
- The L^1 assertion of the lemma (second conjunct of `vonNeumannOneL2`) already used essential suprema; it needed no change.
- Five over-long generated file titles (Sec11_2a/b/c, Sec14_2a/b) were shortened. This is cosmetic.

## 2026-10-14T07:03:38-04:00

Conventions in complete sec:base rows (blueprint lines 1482-1596), logged for transparency. Neither changes mathematical content.
1. Admissible sequences, lines 1482-1486. The blueprint defines admissible sequences as three concrete types (a fixed F, a current inherited projection P_I F, a square-energy Z_I) and finite sums of them.
   - Lean defines admissibility by the properties the later proofs use: `IsAdmissibleOpponent`, a Bessel transfer against cell row families, and `HasDepthEnergy` (TrilinearHT/Auto/Sec11_1aPredictors.lean). Both are closed under finite sums.
   - Each of the three blueprint types is proved admissible, with constants 1, a polynomial in log(2 D_h), and L respectively.
   - So lem:predictors and lem:delay, proved for the property-defined class, apply to every blueprint-admissible sequence. This is a generalization, not a restriction.
2. eq:base-tuple expansion, lines 1586-1587. The blueprint groups the remaining terms as "four terminal residuals" or "one whole terminal projection and three terminal residuals".
   - Lean (`StaggerCell.expansion`) keeps the one-increment-and-three-residuals terms separate, one per increment.
   - Summing them over the increments of a slot gives the blueprint's whole-terminal-projection term, by linearity of the form in that slot.
   - Each separate term is bounded by 32 e^(-k_(T-3)) (`StaggerCell.remainder_four`), so the remaining terms still vanish in the limit, as eq:stagger requires.

## 2026-10-14T08:02:12-04:00

prop:base, blueprint lines 1600-1607 (eq:Y and the budgets). Resolves gap 5 of 2026-10-14T03:50:08.
1. Departure (edge case of the finite truncation). eq:Y uses P^new_(e,s+K0) at depth s. In a finite tree of depth N, for the last K0 levels (s + K0 > J.1 + N) the cells of depth s + K0 lie below the tree, where the Lean column families have no cells. The blueprint does not treat this truncation.
   - Lean (TrilinearHT/Auto/Sec11_2cFiniteBaseDataAssembly.lean: `baseBottom`, used in `baseTuple`): these cells are grouped below fresh normalized roots at depth max(J.1 + N + 1 - K0, depth of the first-level root), at most K0 levels above them. On each group the new high families are empty at depth s and the identity at depth s + K0. So Y = X there (no replacement error), B_e = -g_prev (zero projection minus the previous fit) and U_e = F_e.
   - The conclusions of prop:base hold on these setups: sizes and pair smallness are those of the tuple; eq:basic-side holds below every sub-root with constant K0 <= (1 + K0)^2, since at most K0 levels occur; the two-U term is at most eta0 K0^2 |R| by pair smallness of the low pair; each B_l is a difference of two current basic projections.
   - Consequence: the extra error 4 eta0 K0 |J| of the earlier formalization is gone. `baseTuple` and `activeCellReduction` now give eq:Y with error e^-k times root length, as stated.
   - Packing: the fresh roots have total length <= 9|J| (first-level roots <= 8|J|; one depth layer <= |J|, `sum_tree_depth_le`). All setup roots now total <= 91/3 |J| (was 64/3 |J|); the blueprint asserts only bounded packing. Sec16_3SummingUpdateLevels (`normalizedAbsorption_of_activeFinal`) uses 91/3.
2. Inverse private weights, line 1607 ("Counts, complexities and inverse private weights are exp(k^O(1))"): now exported.
   - `ActiveSetup.colBudget` = 2 + |L| (1 + D_c). `HasColumnRep` and `ColumnRepBelow` require both basic projections to have column budget <= colBudget. A column budget X bounds the inverse private weights by X^2 (`BasicProjection.inv_privateWeight_le`). With |L|, D_c <= E = exp(k^Cb) from `activeCellReduction`, all inverse private weights are <= (2 + E + E^2)^2.
   - Sources: the fit-opponent families have budget max(2, M), now recorded in `IsFitOpponent` (Sec11_2bFiniteBaseDataPairs.lean) and carried by `IsBasicOn`; the high systems have budget <= 2 + |W| + |W| eps^(-1/2) (`PathColumnSystem.budget_le`), and D_c = eps^(-1/2).
Full `lake build` passed (9080 jobs). baseBottom, baseTuple, activeCellReduction, BasicProjection.inv_privateWeight_le, normalizedAbsorption_of_activeFinal use only propext, Classical.choice, Quot.sound.

## 2026-10-14T08:19:15-04:00

sec:localization, blueprint lines 1668-1673 (P and small overheads). `localization_largeParameter` (TrilinearHT/Auto/Sec12_1TagsAmbientGraph.lean): with eta = e^(-k^theta) (prop:base, line 1607) and P = ceil(eta^(-alpha)), for every fixed 0 < alpha < 1, eventually in k: 2 <= P <= e^k, exp(C_q (1 + log(2k))^C) <= P^eps for every eps > 0 (G0 = P^o(1)), and k^p <= P^eps.
- Generalizations, not restrictions: theta <= 1 is allowed (the blueprint has 0 < theta < 1), and k ranges over the reals (the blueprint's k is a natural number; the statement for natural k follows along the cast).
- The remark "an exponential exp(P^C) is not a small overhead" (line 1673) is a convention and has no formal content.
Full `lake build` passed (9080 jobs); standard axioms only.

## 2026-10-14T08:55:24-04:00

prop:base, blueprint line 1607 ("Counts, complexities and inverse private weights are exp(k^O(1))"), complexities of the basic projections. Addendum to 2026-10-14T08:02:12-04:00.
- Gap found after that entry: the basic projections of `HasColumnRep`/`ColumnRepBelow` carried no chart data for their columns, so their complexities were not exported (only the expansion labels A.L had charts). These charts are also the tags of the original basic columns in sec:localization (line 1676).
- Resolved: `BasicProjection.HasChartsOn` (TrilinearHT/Auto/Sec11_2cFiniteBaseDataAssembly.lean): every column available at a cell of the setup is a bounded quadratic chart atom of order c0 and complexity at most A.H on that cell. `HasColumnRep` and `ColumnRepBelow` require it for both basic projections. With A.H <= exp(k^Cb) from `activeCellReduction` the complexities are exp(k^O(1)).
- Sources: fit families record the charts of their atoms in `IsFitOpponent` (Sec11_2bFiniteBaseDataPairs.lean, from `Hyp.atoms_good` and `atoms_leaf`) and carry them in `IsBasicOn`; high systems use `PathCharts` with `PathColumnSystem.scalar_eq`.
Full `lake build` passed (9080 jobs); standard axioms only.

## 2026-10-14T09:39:07-04:00

sec:localization, catalogs, blueprint lines 1803-1815. Resolves gap 8 of 2026-10-14T03:50:08 (catalogs omitted the rank-0 original columns of line 1805). New file TrilinearHT/Auto/Sec12_3bCatalogsMainColumns.lean.
- Main projections (line 1805): `mainSel`/`mainRange`/`mainProj` span, at a cell, the original columns of the basic families available there whose vertex lies in the vertex mask (rank zero, with their own private weights) and the templates of rank <= r born above the cell with tag in the mask (private weight one). The template-only `catProj` of Sec12_3FiniteSameTagCatalogs.lean is superseded from line 1803 on.
- Vertices (line 1676): `ActiveSetup.BasicFamilies` fixes the two basic projections of each slot from `HasColumnRep`. A vertex is (slot, family, label) with its admission cell; it is available when the label lies in the family mask; tags come from the family charts (`BasicProjection.HasChartsOn`). The vertex bound D = floor(8 colBudget) + 1 bounds the present columns through the family path budgets (`admT_X_card_le`).
- Colors and masks: `coloring`, `colorSetup` and `masks` re-instantiated on these vertices. Cumulative masks `cmask` and ball masks `bmask` grow in depth and in the pad. Ranks L-m+1, L+j and helper L+5; base pads 10P(L-m+1) and 20P(L+1)+10(j-1)P. The field `pads_le` (20P(L+1)+31P+2 <= H_max) records that all needed neighbor enlargements lie below H_max.
- Filters: `cumFilt` and `ballFilt` average P main projections with pads base+p, 1 <= p <= P. They are nested in the pad (`cum_nest_pad`, `ball_nest_pad`) and in depth (`cum_nest_depth`, `ball_nest_depth`: the restriction of the range at a cell to a subcell lies in the range there). Averages and complements are contractions.
- Tests: `MainTest` with an augmented base, `hist`, `resid`, `Pass` at level tau times the normalized norm of the base on the cell. The level tau_3/(D sqrt(n_(r-1))) with tau_3 = D^(-C_tau) is `catLevel`. Spectators are arbitrary normalized L^2 functions. `avg_history_pass`: if the tests of all individual pad choices pass, the averaged history passes.
- Formulation note (not weaker than the blueprint): `Pass` bounds the form against every pure source chart whose tag lies in the mask, not only against lower-rank ones. Pure sources of a tag are the same class of charts at every rank.
- Consequence: later rows whose Lean objects are the superseded template-only catalogs or the vertex model on the expansion labels are downgraded to old incomplete (separate entry).
Full `lake build` passed (9081 jobs); standard axioms only.

## 2026-10-14T09:45:20-04:00

Ledger consequence of the catalog redefinition (2026-10-14T09:39:07). An audit of all complete rows after line 1815 classified their cited Lean declarations. 11 rows are no longer faithful: their declarations are instantiated on the superseded template-only catalogs (`catProj`, `CatTest`, `VTest`, `catLabels`, `catAtom`, `AttemptParams`, `LeafSplit`) or on the vertex model built on the expansion labels A.L (`A.Vtx`, `A.vtag`, `A.admT`).
- The 11 rows: lem:closure 1819-1828; prop:localize 1838-1856; line 1888; eq:firstmatch 1903-1910; eq:sides 2124-2133; lines 2135-2150; line 2159; lines 2167-2169; eq:transferred-main 2257-2263; line 2464; eq:four-tests 2506-2520.
- Status: they are marked old incomplete, except lem:closure 1819-1828, which is now the first non-complete row and is in progress.
- Unaffected: the other 44 complete rows after line 1815 cite generic declarations (arbitrary Hilbert spaces, projection families, mode systems, real inequalities) and stay complete.
- Caveat: `ModeSystem` fixes its primary type to Fin Mc. Reusing those generic rows on the main columns needs a reindexing or a generalization of the primary type. Their statements remain correct as stated.

## 2026-10-14T10:20:26-04:00

lem:closure, blueprint lines 1819-1828, on the main columns (TrilinearHT/Auto/Sec12_3bCatalogsMainColumns.lean). Replaces the closure on the superseded template-only catalogs (`cell_closure`, `tree_closure`, `catalogs_exist`, `catalogs_counted`).
- Gain (lines 1823-1827): `MainTest.gain`. If a main test fails at a cell, the same-tag test (line 1797) gives a same-tag template born at the cell, with the test's rank and a tag in its mask. Inserting it grows the target projection on the old history value by more than tau/(2 H0) times sqrt|I| times the normalized base norm on the cell. The new template coordinate is absent from the old state (`MainFresh`, `hist_fresh`), so the moment is an increment of the target projection (`mainProj_gain`).
- Nesting (line 1828): `mainProj_append_irrel`, `MainTest.pass_append_irrel`. Templates born at cells that do not contain I leave the projections and the tests at I unchanged.
- Cell closure (line 1828): `main_cell_closure`, via `local_closure` and the prefix inequality eq:prefix. The rank-r insertions at one cell number at most |W| 4^m L_T^(2m) (2 H0 / tau_r)^2, and fewer than T are inserted, when these allowances sum to less than T. The bases must be supported on the cell and have no coordinates on template labels beyond a fixed prefix catalog s0 (s0 is empty for the main closure and the main catalog for the helper closure).
- Tree closure: `main_tree_closure`, processing the cells coarse first (`exists_coarse_first`).
- Attempt level (line 1820): `ActiveSetup.BasicFamilies.FamParams.main_closure`, on every active cell (`A.cells`), for slot catalogs over the main columns of the basic families.
  - Thresholds are tau_3/(D sqrt(n_(r-1))) of eq:catalog-test (`catThreshold`, with D = `famVtxBound`).
  - Rank-r insertions at one cell number at most K n_(r-1), where K = K_t 4^m L_T^(2m) (2 H0 D / tau_3)^2 (`closureRatio`).
  - The main labels of rank <= r <= L+5 at any cell in at most M_p active cells number at most n_r (`mainLabels`, `card_mainLabels_le`; originals counted by `card_avail_le`).
  - These hold when n_0 >= 2 colBudget, n_(r+1) >= (1 + (L+6) M_p K) n_r, and T >= n_(L+5).
  - `exists_pathCounts` shows such n and T exist for all data (n_r = exp((r+j) X^C2) from `closure_parameters`), so the hypotheses are not vacuous.
  - No bound involves the edge threshold H_ed (line 1820, "degrees are independent of H_ed").
- Helper closure (lines 1815, 1820): `helper_closure`. For any slot catalogs and any finite families of rank-(L+5) helper tests on fixed whole bases supported on the cells, with no coordinates beyond the catalog (private coordinates disjoint from fresh helper labels), helper templates of rank L+5 close the helper tests. They number at most K n_(L+4) per cell.
- Formulation notes (none weakens the blueprint):
  1. Named tests. The closure is proved for every finite family of named main tests: any target ranks 1 <= r <= L+5, any masks, any histories of length <= m, any bases supported on the cell without template coordinates, and at most K_t names per cell and slot.
     - The concrete named histories of line 1809 are those required by prop:localize and the transfer. They are instantiated there.
     - The count exp(k^O(1)) of line 1823 is the size of K_t. It is quantitative and is moved to the row for lines 1820, 1823 and 1828-1830, which also bounds log n_(L+5) <= k^O(1).
  2. Path counts. They count the available original labels (rank 0) together with the templates, so n_0 >= 2 colBudget.
  3. Label capacity. The template labels are indexed by Fin M_c; M_c >= |cells| T (main) is a formal capacity, chosen after T. The blueprint uses unboundedly many fresh labels.
  4. `Pass` tests every pure source of a mask tag, not only lower-rank ones (as in the 09:39:07 entry).
- Moved: the generic counting lemma `length_filter_le_sum` moved from Sec14_1TransferPairedDefects.lean to Sec12_3bCatalogsMainColumns.lean. Sec12_4BinaryLocalizationVariation.lean now imports Sec12_3bCatalogsMainColumns.lean, so the later rows can use the main columns.
Full `lake build` passed (9081 jobs, no warnings); standard axioms only (propext, Classical.choice, Quot.sound).

## 2026-10-14T10:44:02-04:00

lem:closure, blueprint lines 1820, 1823 and 1828-1830: sizes of the main closure (TrilinearHT/Auto/Sec12_3bCatalogsMainColumns.lean). The previous attempt-level counts came from `exists_prefix_fixed` with no bound in k (gap 7 of 2026-10-14T03:50:08); they are replaced.
- Names (line 1823): `FamParams.MaskName`, `maskOf`, `TestName`, `testOf`, `HelperName`, `helperOf`.
  - A mask name is a cumulative split m <= L with a pad h <= H_max, or an original vertex present at the cell (naming its group) with a pad. Names involve original vertices, ranks, pads and the history length; they involve no graph distances and no inserted sources.
  - A test name is a target rank 1 <= r <= L+5, a mask name, a history of at most m factors (rank, mask name, complement flag) and a base name. All filter masks are named (`cmask_named`, `bmask_named`).
  - Count: `card_testName_le` gives (L+5) (L+1+D)(H_max+1) (m+1) (2 (L+6)(L+1+D)(H_max+1))^m |Bn| per cell. `names_count_poly` bounds this by exp(k^(c+2)).
- Color sizes (line 1828, "L+5 = k^O(1)"): `colorSizes_poly`. For 1 <= D <= exp(k^c) and P <= e^k, the choices of line 1715 (L = d0^30 with d0 = ceil(1000 log 2D), and H_max = 100 P (L+1)) give L+6 <= k^(30c+31) and H_max+1 <= exp(k^(30c+32)).
- Path counts (lines 1820, 1828): `pathCounts_poly`, from `closure_parameters`. The counts are n_r = exp((r+j) k^C2) with n_0 >= the required n_0. The ratios satisfy n_(r+1)/n_r >= 1 + (L+6) M_p K for the closure ratio K of the trial cap T, so the binary-prefix factor is below the ratio and no cap is attained. Also n_(L+5) <= T and log T <= k^C.
- Same-tag constant and thresholds: `closureData_le` bounds 1 + (L+6) M_p K_t (2 H0 D / tau_3)^2 by exp(k^(c Dst + c + 1)) when H0 = exp(Dst (1 + log H)^Dst), log H <= k^c and 1/tau_3 <= exp(k^c).
- Assembly: `FamParams.closure_poly`. For fixed c and Dst there are C and k0 such that, for k >= k0 and every attempt with k^c-bounded sizes:
  - the main and helper test names number at most K_t per cell, with log K_t <= k^C;
  - path counts and a trial cap satisfy all hypotheses of `main_closure` and `helper_closure`, including the helper allowance K n_(L+4) < T;
  - log n_(L+5) <= k^C and log T <= k^C.
  The sizes bounded by exp(k^c) are the vertex bound, H_max, the path multiplicity, two column budgets, the base-name counts, 1/tau_3 and the source complexity (log H <= k^c); also L+6 <= k^c and m <= c(1 + log k).
  C and k0 are chosen before the attempt, so the degrees do not depend on H_ed or any later precision (lines 1820, 1830). The count is fixed before tau_2 and H_ed: no bound involves them.
- Formulation notes (none weakens the blueprint):
  1. The size hypotheses of `closure_poly` are supplied where the attempt parameters are fixed:
     - L and H_max by `colorSizes_poly`;
     - D, the column budgets, the path multiplicity and the source complexity by prop:base (exp(k^O(1)), line 1607; path multiplicity D^C, line 1623);
     - P <= e^k by `localization_largeParameter` (line 1668);
     - tau_3 = D^(-C_tau);
     - the history length m = O(log L) by the binary search of prop:localize (line 1848).
  2. The named family is universal: all histories of length <= m over the named masks. The histories required by prop:localize and the transfer are among them.
  3. The trial cap is the integer ceiling of n_(L+5), since template labels are indexed by naturals.
Full `lake build` passed (9081 jobs, no warnings); standard axioms only (propext, Classical.choice, Quot.sound).

## 2026-10-14T11:05:35-04:00

sec:localization, blueprint line 1835: main budget and expansion cost on the main columns (TrilinearHT/Auto/Sec12_3bCatalogsMainColumns.lean). Resolves the line-1835 part of gap 6 of 2026-10-14T03:50:08: the old catalog budget max 2 M_c counted all retained cells of the tree.
- Expansion: `mainRange_exists_coeff`. Every vector of a main range is a combination of the columns of the main labels of rank <= r at the cell.
- Coefficient bound: `mainCoeff_sum_le` (via `mainCombination_coeFn`, `inner_single_privateColumnValue`). Distinct labels have distinct private coordinates, so on the cell the coordinate of label w is c_w sqrt(eps_w). Bessel gives |I| sum |c_w|^2 eps_w <= ||x||^2. If all inverse private weights are at most D^2, Cauchy-Schwarz gives sum |c_w| <= sqrt(N) D ||x|| / sqrt|I| for N labels.
- Attempt level:
  - `inv_mainWeight_le`: original columns have inverse private weight at most colBudget^2 (`inv_privateWeight_le` with the family budgets); new labels have weight one ("only original columns have small private weights").
  - `primal_expansion`: the rank-r main projection of any input expands with coefficient sum at most colBudget sqrt(N) ||z|| / sqrt|I|.
  - `primal_expansion_count`: for inputs supported on the cell and at most n_r labels (the path counts of `main_closure`), the coefficient sum is at most colBudget sqrt(n_r) ||z||_(2,I).
- The denominator of eq:catalog-test:
  - `catThreshold_mul_cost`: tau_3/(D sqrt n_(r-1)) times D sqrt n_(r-1) equals tau_3.
  - `colBudget_le_famVtxBound` and `expansion_cost_le_threshold`: the expansion cost times the threshold is at most tau_3.
- Common budget: `ActiveSetup.mainBudget T U` = colBudget^2 T U, with trial cap T and use-count bound U.
  - `mainBudget_spec`: D_m dominates the catalog sizes (T >= n_(L+5)), the inverse private weights, the expansion cost colBudget sqrt(T) and the use counts.
  - `log_mainBudget_le`: log D_m <= 2 k^c + k^C + k^C' when colBudget <= exp(k^c), log T <= k^C (`closure_poly`) and log U <= k^C'.
- Formulation notes (none weakens the blueprint):
  1. The use counts are defined in prop:localize (line 1854: counts of uses are fixed powers of D). D_m takes their bound U as a parameter; it is instantiated there.
  2. The coefficient bound is stated for the absolute coefficient sum. This is the coefficient norm charged at line 1854.
  3. The remark "a full coefficient sum will not be charged in retained main estimates" concerns how later estimates use the expansion. It has no separate content here.
Full `lake build` passed (9081 jobs, no warnings); standard axioms only (propext, Classical.choice, Quot.sound).

## 2026-10-14T12:04:51-04:00

prop:localize, blueprint lines 1838-1856, on the main columns (new section at the end of TrilinearHT/Auto/Sec12_4BinaryLocalizationVariation.lean). Replaces `attempt_localization` on the superseded catalogs (Sec14_2bShortBlockSummation.lean).
- Common column space (refines the objects of the rows 1803-1815, 1819-1828, 1820-1830 and 1835).
  - All slots now use one column space ColumnL2 (Lab + Fin M_c), Lab being all original basic column labels. `origCols l` makes available at a cell exactly the columns of the two basic families of slot l in their masks. The columns of other slots are never available for slot l.
  - Each slot's catalog uses its own template list. Template coordinates are indexed by Fin M_c in every slot, but a slot-l vector only ever carries coordinates of slot-l columns.
  - The slot-l projections therefore act exactly as in the slot-l column space; the projections, ranges and estimates are unchanged.
  - Reason: the generic leaf identities (`leaf_identity`, `leaf_localization`, `search_cell_min`) need one space for the four slots of the form.
  - `main_closure`, `helper_closure`, `primal_expansion`, `closure_poly` and the test names are restated on the common space and re-proved.
- Leaf histories are named tests.
  - `layerName` and `layerName_hist`: a layer list at a pad choice is a test name of `TestName`.
  - `layer_residOK`: if the layer tests of all pad choices pass, the averaged target residual of the averaged layered input passes (line 1811, "the tests also hold for averages").
- Generic leaf error: `ResidOK.form_le`, `ResidOK.combo_le` and `leaf_error_resid`. These are the old-source, matching, separation and residual bounds from passing residuals, in any column space.
- Attempt facts on the basic families:
  - `classify` (line 1850): a vertex of the upper cumulative mask is old (in every lower guard mask) or lies in the first ball mask of a current group.
  - `sep_pair` (lines 1851-1852): vertices of first ball masks of distinct current groups are pair separated, via `mask_sep` and lem:graph.
  - `origCol_source`, `templateCol_source`, `mainLabel_source`: main columns are pure sources.
  - `avg_expansion` (line 1835): averaged filter outputs expand in main columns with coefficient sum at most colBudget sqrt(N) S.
- Leaf and sum:
  - `leaf_bound` and `leaf_main` handle one cell and leaf. The upper guard is a cumulative main filter, or the basic slot expanded in its available original columns ("expand only this outer primal").
  - `localized_sum` sums over the cells and the leaves of the guarded search, using eq:min-subadd.
- Attempt theorem: `FamParams.attempt_localization`. For slot inputs supported on the active cells without template coordinates:
  - `main_closure` on the named tests of the inputs (at the thresholds tau_3/(D sqrt(n_(r-1)))) gives the catalogs.
  - On every set of active cells with path multiplicity at most M_p, no failed vertices, colors at most L, a basic guard input in its original columns, and local input sizes at most S, the weighted cell minima are at most the leaf current-group sums plus Sum|I| #leaves 9 (D+1) tau_3 S^4.
  - `leafErrM_le` checks the cancellation of line 1854. Each expansion cost D sqrt(n_(r-1)) meets a threshold tau_3/(D sqrt(n_(r-1))), and tau_2 = tau_3/(D^2 n_(L+1)) is chosen after the main count.
  - #leaves <= 2^fuel (`searchLeaves_length_le`), which is at most 4L for fuel = ceil(log_2 L) + 1 (`two_pow_clog_succ_le`), so poly(k).
- Formulation notes (none weakens the blueprint):
  1. The slot inputs are arbitrary augmented vectors. The basic guard slot only needs to be a combination of its available original columns, which holds for the augmented basic projection output on a cell. The concrete basic-slot inputs B_(l,s) B_l on F_l belong to line 1859, the next row.
  2. The total error is stated as Sum_I |I| times #leaves times 9 (D+1) tau_3 S^4. The blueprint's form "C e^(-k) |R|" follows when tau_3 = D^(-C_tau) with C_tau large (line 1854). The factors involved:
     - #leaves = O(L);
     - Sum_I |I| <= M_p |R| (path multiplicity);
     - D >= e^k;
     - S is the local input size.
     These are fixed powers of D. The choice is made with the attempt parameters.
  3. The hypotheses no failed vertex, colors <= L, H_ed large for tau_2 and the local sizes S are the blueprint's standing assumptions at this point. They come from lines 1720-1745, 1715, lem:graph and line 1854 ("local sizes and same-time contractions are bounded").
- Moved: generic helpers moved from Sec14_1TransferPairedDefects.lean and Sec14_2bShortBlockSummation.lean to Sec12_4 so that this section can use them; `cellForm_pair_le` is generalized from Fin M_c to any label type. Moved lemmas: `localProgressionForm_congr_support`, `cellForm_apply`, `localProgressionForm_smul`, `localProgressionForm_congr_cell`, `fin4_cover_of_distinct`, `thirdSlot_ne`, `searchLeaves_inv`, `sum_norm_le_sqrt_card`, `augPhys_normalized_le`, `cellForm_pair_le`, `otherTwo_spec`, `SearchLeaf.role_t/role_ge/role_le`, `searchLeaves_layers_length`, `leafAt_mem`, `searchLeaves_range`, `searchList_inv`, `leafAt_facts`, `searchLeaves_length_le`.
Full `lake build` passed (9081 jobs, no warnings); standard axioms only (propext, Classical.choice, Quot.sound).

## 2026-10-14T13:13:32-04:00

Blueprint line 1859 (basic-slot histories, compression loss, zero convention) on the main columns: new section "Basic-slot histories on the main columns" at the end of TrilinearHT/Auto/Sec12_4BinaryLocalizationVariation.lean.
- Global main column tree (`MainBudget`, `mainTree`).
  - Labels: the relevant main labels `RLab` (original basic columns available at some active cell, and the catalog templates), with the family scalars and private weights (templates: weight 1).
  - Births: the family birth cell of an original column, clamped to the attempt root R when it contains R; the birth cell of a template. Cells: the complete tree of depth `treeDepth` below R.
  - Budget: any B with 8 colBudget + (template path count) <= B.
  - Formalization note (not a weakening): main labels never available on the attempt are left out of the tree. They carry no column at any attempt cell, so no main projection uses them, but they would enter the path count of the tree. The full main space ColumnL2 (Lab + Fin M_c) is reached by the isometric relabeling `colRelabel rv` and its adjoint. `relabel_cellProj`: at an active cell the relabeled cell projection of the tree is exactly the cell-local main projection `mainProj`.
- Inherited masks `mainMaskT` (zero convention and retained projections, line 1859).
  - At a cell of the tree the masks are the main labels of its deepest active ancestor (`deepAnc`); they are empty when no active cell contains the cell.
  - `mainMaskT_labels_none`, `mainCellProj_none`, `gBall_zero_before`: on cells above the attempt the main projections, hence the ball outputs, vanish.
  - `mainMaskT_labels_retain`: between actual uses every cell of the tree, in particular every endpoint cell, keeps the masks (hence the inherited projections) of its last active ancestor.
- Global objects and bridges.
  - `gHist`: the shared cumulative history at depth h (layers of averaged global main depth projections or their complements). `gBall`: the global smeared ball filter.
  - `hist_bridge`, `ball_bridge`: at an active cell they restrict to the cell-local `cumFilt` and `ballFilt` of prop:localize.
- Basic inputs.
  - `famEmb` embeds the column space of the basic family (l, j) into the main space. `gBasic l h = P_{l,0,h} F_{l,0} - P_{l,1,h} F_{l,1}` (depth projections of the two basic families acting on their inputs). `basicIn l I` is its restriction to I.
  - `basicIn_phys`: its physical part is B_l(I) on I. `basicIn_fresh`, `basicIn_support`, `basicIn_comb`: no template coordinates, support in I, a combination of the available original columns. So the basic inputs satisfy the slot-input and guard hypotheses of `attempt_localization`.
  - Formulation note: F_l is the pair of inputs (F_{l,0}, F_{l,1}) of the at most two current basic projections of prop:base (line 1611); "the fixed signed basic sum" is P_{l,0} F_{l,0} - P_{l,1} F_{l,1}.
- The histories (first sentence of line 1859).
  - `basic_history`, `basic_history_expand`: on an active cell, B_{l,s} B_l is the restriction to the cell of Sum_j (-1)^j (uniform average over the pad tuples w of the complement products of |ls| global main depth projections) applied to the basic depth projection P_{l,j} F_{l,j}. The expression involves no group (shared across groups).
  - `basic_leaf_expand`: at a search leaf |ls| <= fuel with L - 1 < 2^fuel, i.e. O(log L) factors.
  - `basic_leaf_out`: the ball output L_{l,G,s} B_{l,s} B_l is the restriction of the global ball filter applied to the global history.
- The compression loss G_0.
  - `basic_compression`: rows that are Bessel with constant B and local to active decision cells stay Bessel after inserting, at the depth of each decision cell, the global history and the basic depth projection acting on F_{l,j}. The constant is B compressionC(main tree, |ls|)^2 compression1(basic tree)^2 ||F_{l,j}||^2. The basic projection is inserted by the one-factor compression of its own family tree, after the history.
  - `compression_loss_le`: this loss is at most G_0 = exp(C_q (1 + log 2k)^2), C_q = 4096 (c+1)(1024 (c+1) + c + 7), when log(2 budget) <= k^c for both trees and |ls| <= c (log k + 1).
  - `tmplPath_le`, `MainBudget.ofCounts`: B = 8 colBudget + n_{L+5} is a main budget when every active cell lies in at most M_p active cells (the closure counts of lem:closure). `log_two_mainB_le`: log(2B) <= k^(c+1) when colBudget, n_{L+5} <= exp(k^c) and k >= 4.
  - `attempt_localization` now also returns these closure counts of its catalogs (ranks <= L + 5, at most n_r main labels of rank <= r at cells in at most M_p active cells, length <= #cells T).
- Moved, unchanged: generic compression and locality lemmas from TrilinearHT/Auto/Sec13_3BesselRowsLinearSideEnergy.lean to Sec12_4 (`compression1`, `rows_projection_compression`, `rows_opAvg_le`, `layerFactor`, `layerPattern`, `layerOp_opAvg_expand`, `compressionC`, `rows_uniformAvg_le`, `rows_layer_compression`, `starProjection_restrict_eq`, `span_vanish_restrict`, `opAvg_commute`, `layerOp_commute`, `columnL2Restriction_idem`, `ColumnDepthFamily.proj_adjoint`, `ColumnDepthFamily.restrict_proj`, `layerOp_intertwine`, `opAvg_intertwine`, `globHist_compression`).
Full `lake build` passed (9081 jobs, no warnings); standard axioms only (propext, Classical.choice, Quot.sound).

## 2026-10-14T14:17:36-04:00

Blueprint lem:variation (lines 1861-1879) on the main columns: new section "Certified variation on the main columns" at the end of TrilinearHT/Auto/Sec12_4BinaryLocalizationVariation.lean.
- Whole endpoint ranges on the main columns (lem:whole-ranges as applied at line 1875).
  - `vWholeRanges`: `usableRangeBessel` for vertex-labelled main columns. The labels are original column occurrences (vertices, with their chart atoms) and templates (with their atoms). Private weights are those of the basic families; inverse weights are at most colBudget^2 = W_0^2. Separation comes from `endpoint_sep` (lem:masks), pairings from lem:graph (`Dg_same`).
  - `mainRange_wholeRanges`: vector form for sums of elements of main ranges at certified active cells. The main labels are split into vertices. Occurrences of one original column with distinct vertices have disjoint admission cells (`vtxAt_eq_of_meet`), so the norms are unchanged (`groupOutput_fiber_norm`).
  - Formalization note (not a weakening): the blueprint's labels with fixed tags are, for original columns, the vertices (column occurrences, line 1676). The inequality is proved for the vertex-labelled outputs and transferred to the main labels.
- Global objects:
  - `ballFamT`: the ball depth families.
  - `gOut`: L_{G,h} B'_h.
  - `basicOut`: Z_{G,h}. `basicOut_restrict`: its restriction to an active cell of depth h is the leaf output of prop:localize.
  - `histOut`: the shared history B'_h B_l.
- `main_wr1`, `main_wr2`: eq:whole-ranges for the interval rows and for the right-endpoint ball rows. The adjoints lie in whole main ball ranges at both endpoints; the right certificate certifies the left-endpoint ancestors (active by `AncClosed`).
- `main_variation`: certified variation for a common input. It uses `certifiedVariation_avg` with the history jumps `globHist_jump` and the compression `globHist_compression` of the main tree.
- `main_variation_basic`, `basic_variation`: the basic coarse output Z_{G,s} = L_{G,s} B'_s B_l.
  - Split: Z_t - Z_r = (T_t - T_r) P_r F + T_t (P_t - P_r) F (`emb_variation`).
  - The first term is bounded by compression of the basic projection (`emb_insert`). The second uses the joint Bessel bound (`main_joint`) and the orthogonal increments of the basic family.
  - The signed sum over the two basic families is taken, and F is restricted to R (`out_restrictR`).
- `basic_variation_G0`: Sum <= G_0 Sum_j 2 ||1_R F_{l,j}||^2 <= 4 G_0 |R|, with G_0 = exp(C_q (1 + log 2k)^2) and C_q = 4096 (c+1)(1024 (c+1) + c + 7) + c^2 + 3. Hypotheses: log(2 D_m) <= k^c, log(2 colBudget) <= k^c, |ls| <= c (log k + 1) and tau N colBudget^2 <= 1 (`variation_loss_le`, `compressionC_mono`, `famInput_energy`).
- `basic_history_variation`, `basic_history_variation_G0`: the shared-history assertion (no outer ball, no groups); the bound is 8 G_0 |R|.
- `basic_variation_overlap`: bounded overlap. Colour the intervals with M colours, same-coloured intervals disjoint; the bound is multiplied by M (`sum_le_of_coloring`).
- `basic_onetime`: intervals crossing the attempt start. With the zero convention the earlier outputs vanish (`gBall_zero_before`), leaving the one-time estimate at the right endpoint.
- Formulation notes (none weakens the blueprint):
  1. Depth intervals are offsets r <= t <= treeDepth below the attempt root.
  2. The pair threshold tau and the number N of group-label pairs present at a point are hypotheses. tau N colBudget^2 <= 1 is the blueprint's choice of tau_2 after the counts (lines 1787-1789, 1854).
  3. The endpoint cells are active cells, and the setup is assumed closed under ancestors (`AncClosed`), as planned in the open entry on certified variation and whole ranges. Establishing `AncClosed` for the assembled attempt remains open there.
  4. Certificates `Cert k G I`: an active cell inside I with a successful present vertex of color k and group G (downstream actual use).
- Moved, unchanged, to Sec12_4:
  - From Sec13_1: `dyadicGridCell_eq_of_meet`.
  - From Sec13_3: `ColumnDepthFamily.proj_comm_restrict`, `proj_vanish`, `norm_sq_partition`, `interval_rows`, `globHist_layer_jump`, `globHist_jump`, `columnL2Restriction_comm`, `AncClosed`, `sum_filter_fst_eq`, `cells_pairwiseDisjoint_of_depth`, `norm_sq_partition'`, `blk_of_commute`, `columnL2Restriction_vanish`, `Ioc_disjoint_shift`, `jumps_from_le`.
  - From Sec13_4: `certifiedVariation_gen`, `certifiedVariation_avg`, `Ioc_disjoint_of_mod`.
Full `lake build` passed (9081 jobs, no warnings); standard axioms only (propext, Classical.choice, Quot.sound).

## 2026-10-14T14:32:19-04:00

sec:modes, line 1888 (primaries and first-match cells on the main columns): new section at the end of TrilinearHT/Auto/Sec13_1OneExpansionAtFirstMatch.lean.
- `primaries l s G j d I`: the main columns available to the maximal pad P and the rank L + j of the role's outer ball (main labels with masks `bmask I G j P`).
- `ballLabels_subset_primaries`, `ballFilt_comb`: every individual ball projection of the role, and hence every outer-ball output at a cell, is a combination of the primaries' columns there.
- `primaries_desc`: primaries are nested in depth. This is "the mode lists, including primaries whose coefficients are zero, are nested"; a primary keeps its role on every active descendant (`primaries_of_firstCell`).
- `firstCells`: the first-match cells of a primary, i.e. the maximal cells of the family at which it is a primary.
  - `exists_firstCell`, `firstCell_unique`: each primary at a cell has a unique first-match cell above it.
  - `firstCells_disjoint`: distinct first-match branches of one primary are disjoint.
- Scope note: the choice of one expansion at the first match and keeping its modes on every descendant is the content of eq:firstmatch and the lift. Their main-column instantiation (the analogue of `attemptLift` with these primaries and first-match cells) is recorded in the Status row "eq:firstmatch, lines 1888, 1903-1910" and is redone there in ledger order.
Full `lake build` passed (9081 jobs, no warnings).

## 2026-10-14T14:43:37-04:00

eq:offset-mean, blueprint lines 1895-1901, in TrilinearHT/Auto/Sec13_1OneExpansionAtFirstMatch.lean.
- Correction of the audit item 9 of 2026-10-14T03:50:08-04:00. `branchProfile δ = gevreyIntervalCutoff 0 (2δ) (1-2δ) 1` already vanishes for `s ≤ δ` and for `s ≥ 1 - δ`: `gevreyIntervalCutoff a b c d` vanishes below `(a+b)/2` and above `(c+d)/2`. It is one on `[2δ, 1-2δ]`, so the cutoff vanishes within `δ` of each branch cut as the blueprint requires. The audit's statement "positive on (0,1)" was wrong; no definition changed.
- New: `branchProfile_eq_zero_near_cut` and `branchCutoffValue_cuts`. `ζ^ρ` takes values in `[0,1]`, vanishes when some coordinate `{u_i - ρ_i}` is within `δ` of an integer, equals one at distance at least `2δ` from all cuts, and equals one in horizontal dimension zero. Together with `offsetMean` (`E_ρ ζ^ρ = c_ζ ≥ 1/2` independently of `u`, `E_ρ |1 - (ζ^ρ)²|² ≤ 4 d δ`), the row is complete. The Gevrey regularity of the cutoff is `branchAmp_smooth`, `branchProfile_deriv_le`.
- The separate gap at line 1944 (gauge multiplier agreement only up to `8 d δ R_δ`) stays open in its own row.
Full `lake build` passed (9081 jobs, no warnings).

## 2026-10-14T14:54:29-04:00

eq:firstmatch, blueprint lines 1888 and 1903-1910, on the main columns: new section at the end of TrilinearHT/Auto/Sec13_1OneExpansionAtFirstMatch.lean.
- Short paths of lem:graph for the original basic columns: `BasicFamilies.tagWalk_path` and `BasicFamilies.tagEdge_of_dist`, ported from the catalog vertices.
- `FamParams.ballRadius`, `ballEdgeH`, `mask_tagEdge_center`: a vertex in a ball mask of a group is joined to the group center by a tag edge of the ball-radius height.
- `mainLabel_chart`: an available main label (original column occurrence or template) is, on the cell, a pure chart of its tag in the slot, of the common source complexity. `vTag_vKey`, `vOccurs_of_mainLabels` and `mainScalar_eq_vPhi` connect main labels with vertex labels.
- `mainFirstMatch_attempt`: the exact absolutely convergent expansion of the product chart of a primary with the branch chart of the group center. It has one curvature, rational frequency differences, and bounds `exp(D X^D)`.
- `mainFirstMatch_finite`: finitely many modes approximate `φ_v ζ^ρ e(-c_l p_ρ)` within `δ_c` on the whole cell.
- `mainFirstMatch_kept`: at each first-match cell `I₀` of a primary one expansion is chosen, and on every active descendant of `I₀` the label is still a primary and the same modes approximate within `δ_c` ("keep its modes and labels on every descendant").
- Formulation note: the primaries are those of the maximal pad `P` (`primaries`), so the ball radius in `X` is that of the pad `bbase j + P`.
Full `lake build` passed (9081 jobs, no warnings).

## 2026-10-14T15:17:43-04:00

Line 1932 (main-column lift `R_(l,G)`), new section at the end of TrilinearHT/Auto/Sec13_1OneExpansionAtFirstMatch.lean.
- Interface change in `LiftData`: the field `δ_sum : δ² Σ_Φ ε_Φ⁻¹ ≤ 1` is replaced by the pointwise field `q_sum : ∀ y, Σ_Φ ‖q_Φ(y)‖² / ε_Φ ≤ 1`.
  - Reason: the old field sums the inverse private weights over all primaries. On the main columns that is a global label count, not the local main budget of the blueprint, which charges the physical correction only for the primaries matched at `y`.
  - `modeLift_norm_sq_le'` proves the norm bound `√5` from the new field.
  - The catalog-only `attemptLift` derives the new field from its hypothesis `δ_c² M_c ≤ 1`; its statement is unchanged.
- `FamParams.card_matched_le`: the primaries matched at `y` (with a first-match cell containing `y`) are primaries at the deepest such cell. Hence they number at most the main labels there.
- `FamParams.mainAttemptLift`: the lift on the main columns `bf.Lab ⊕ Fin M_c` of a role, with modes indexed by (primary, first-match cell, mode) and the `q_Φ` of the blueprint.
  - Primary weights are the private weights of the main columns.
  - Mode weights are local: `ε_m = ε_Φ / (Σ_m' |a_(Φ,m')|² + 1)`. This gives the per-primary private bound pointwise, and `1/ε_m ≤ colBudget² (exp(D X^D)² + 1)`.
  - Physical correction: `Σ_Φ |q_Φ(y)|²/ε_Φ ≤ δ_c² N colBudget²` pointwise, `N` bounding the main labels of the rank at the cells. This is the blueprint's `δ_c D_m^C`.
  - Further exports: zero before the match; exact synthesis `R(Σ_Φ β_Φ main_Φ) = Σ_(Φ,m) β_Φ a_(Φ,m) ψ_m` at points where every primary with `β_Φ ≠ 0` is matched; the per-primary absolute coefficient sum `≤ exp(D X^D)`; mode counts `≤ N · bnd` at each point; one curvature per branch; rational frequency differences.
- Parameter note: the absolute norm bound of the lift uses `δ_c² N colBudget² ≤ 1`. This is the blueprint's choice of `δ_c = exp(-k^(C_c))` with `C_c` large after the main budgets, here passed as an explicit hypothesis on `δ_c`. The bound `log(1/ε_m) ≤ P^C` follows from the displayed bound once `X`, `log colBudget ≤ P^C`. That comparison is part of the next row (choice of `D_*`, line 1934).
Full `lake build` passed (9081 jobs, no warnings).

## 2026-10-14T16:07:04-04:00

Line 1934 (choice of the a priori budget `D_*`), new section at the end of TrilinearHT/Auto/Sec13_1OneExpansionAtFirstMatch.lean.
- `FamParams.modeStar D d_B H δ_c N k` is an explicit sum. Here `B = exp(D X_max^D)`, and `X_max` (`Xmax`) is the first-match size at the largest ball radius `b₁ d₀ + b₁ + bbase 4 + P`. The terms are:
  - `e^k`;
  - the modes of all groups along a path, `D (potMax + 1) (N + 1) M₁`, with `M₁ = B (4 max(1, 4B/δ_c) + 1)^(4 d_B)` the mode bound of one primary at one branch;
  - the rational heights of eq:mode-differences, `B (1 + 4 (2 d_B + 1) max(1, 4B/δ_c))`;
  - the inverse private weights, `colBudget² (B² + 1)`;
  - the clearing-integer bound `H_ed^(d_B²)`;
  - the coefficient sums `(√N + 1) colBudget B`.
- It does not involve the branch offsets. It is uniform over the groups with nonnegative top score, which are all actual groups (`ColorSetup.grp_top_nonneg`), and over the levels `j ≤ 4` (`ballRadius_le`, `X_le_Xmax`).
- `le_modeStar`: each quantity exported by `mainAttemptLift` is at most `D_*`. This covers mode counts per branch, per point and along a path across groups, main uses along a path, heights, inverse weights, coefficient sums, and `|λ||I₀|²`.
- `Q₀` (line 1893): `clearInt C`, the product of the denominators of `C`. It clears every entry (`clearInt_clears`, the hypothesis form used by `gauge_char_int` and `gaugeMult_periodic`), satisfies `clearInt C ≤ H_ed^(d²)` (`clearInt_le`), and `clearInt_le_modeStar` gives `Q₀ ≤ D_*`.
- Paths across groups:
  - `ColorSetup.card_grp_chain_le` / `FamParams.card_groups_path_le`: the groups of present central vertices at the active cells containing a point number at most `D (potMax + 1)`. The color-data change counter is monotone along ancestors and determines the group when it is unchanged (`changes_anc`).
  - `BasicFamilies.card_mainLabels_path_le`: the main labels along a path occur at the deepest cell, so there are at most `N` (`mainLabels_desc`).
- `R Z` coefficient sums on endpoint cells:
  - `lift_endpoint`: for the exports of `mainAttemptLift`, a main output with coefficients on the primaries of a cell `J` of the family lifts at every point of `J` to the mode synthesis with coefficients `c_Φ a_(Φ,m)`, of absolute sum at most `B Σ|c_Φ|`.
  - `endpoint_coeff_le_modeStar`: by private-coordinate recovery (`mainCoeff_sum_le`), `B Σ|c_Φ| ≤ D_* ‖x‖ / √|J|` at any depth.
- `log_modeStar_poly`: there is `C` (depending only on `c` and the first-match degree `D`) with `log D_* ≤ C (kP)^C`. The standing bounds are `k ≥ 1`, `L + 6`, `d_B`, `log H_ed`, `log H`, `log(1/δ_c)`, `log N`, `log colBudget ≤ k^c`, and `H_max + 1 ≤ (kP)^c`.
  - Formulation notes: "`P^C`" is read as a polynomial bound in `P` and `k` (blueprint line 1673).
  - The standing bounds are passed as hypotheses. They are the parameter choices of the attempt: `L, d_max ≤ k^{O(1)}`, `H_ed = exp(k^{O(1)})` by lem:graph, `δ_c = exp(-k^{C_c})`, `log D_m ≤ k^{O(1)}`, and `H_max` polynomial in `P, k` (pads `20P(L+1)+31P+2`).
  - Compared with `closure_poly`, which only assumes `H_max + 1 ≤ exp(k^c)`, the bound on `H_max` here is polynomial in `kP`. It enters through the ball radius.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T16:53:10-04:00

Line 1944 (gauge multiplier, enlarged `D_*`, common cutoff `B_*`), new section at the end of TrilinearHT/Auto/Sec13_1OneExpansionAtFirstMatch.lean.
- Resolution of the open gap recorded on 2026-10-12 and in audit item 9:
  - The true cutoff `branchProfile δ` vanishes within `δ` of each cut (`branchProfile_eq_zero_near_cut`, row eq:offset-mean). The enlarged cutoff `branchProfile (δ/2)` is one on `[δ, 1-δ]` and zero at the cuts.
  - `gauge_factors_eq_mult_exact` therefore proves the blueprint's exact identity. The four true cutoffs times the four gauge phases `e(c_j p_(ρ_j)(y_j))` equal the four true cutoffs times `gaugeMult (δ/2)` at the torus point.
  - This replaces the additive error `8 d δ'' R_δ` of `gauge_factors_eq_mult`, which is no longer needed.
- Fourier norms:
  - `periodic_fourierNorm_le`: a smooth periodic function with derivative bound `A` of order `d + 1` and sup bound `B` is the sum of its absolutely convergent Fourier series, and `Σ_v |ĉ_v| ≤ 5^d B + 2·7^d A √d^(d+1)`.
  - `periodic_truncate_full`: the same, with the box truncation stated for the coefficients `ĉ_v` themselves.
  - Instances: `gaugeMult_fourier` (bound `gaugeMultNorm`) and `gaugeSq_fourier` (bound `gaugeSqNorm`, the squared gauge `(ζ^ρ)²`).
  - In horizontal dimension zero both functions are identically one (`gaugeMult_dim_zero`, `gaugeSq_truncate'`).
- Uniformity in the center tag: `gaugeMultA_mono`, `gaugeMultTail_mono`, `gaugeMultNorm_mono`, `gaugeTail_mono`, `gaugeSqNorm_mono`. The clearing integer is `Q₀ = clearInt C_z ≤ H_ed^(d_B²)` and the entries satisfy `|C_ab| ≤ H_ed`.
- Enlarged budget `FamParams.modeStarG = modeStar + gaugeMultNorm d_B (H_ed^(d_B²)) H_ed (δ/2) + gaugeSqNorm d_B δ`. It dominates `e^k`, the line-1934 budget and both full norm bounds (`le_modeStarG`).
- Common cutoff: `K_* = ⌈log₂(2 (T_* + 1) D_*^300)⌉`, with `T_*` (`tailStar`) the uniform truncation constant, and `B_* = 2^(K_*+1)`. Then `tail_le_Kstar` gives tails at most `D_*^(-300)`, and `log_Bstar_le` gives `log B_* ≤ 301 log D_* + 3`.
- Final statements:
  - `gaugeMult_star`: for every center of dimension at least one, every anchor and all offsets in `[0,1]`, the multiplier with cutoff `δ/2` and `Q₀ = clearInt C_z` is the sum of its Fourier series. Its coefficients are at most 1, every coefficient sum is at most `D_*`, and the box-`B_*` truncation is within `D_*^(-300)`.
  - `gaugeSq_star`: the same for `(ζ^ρ)²` with cutoff `δ`.
  - `log_modeStarG_poly`: `log D_* ≤ C (kP)^C` and `log B_* ≤ C (kP)^C`, under the standing bounds of `log_modeStar_poly` together with `0 < δ_c`, `0 < δ` and `δ⁻¹ ≤ exp(k^c)` (the cutoff width is `exp(-k^{O(1)})`, blueprint line 1895).
- Moved (no change of statements): `fractProfile`, `gaugeSq` and their lemmas, `gaugeSq_truncate`, `gaugeTail` and `gaugeSq_truncate'` move from Sec13_3 to Sec13_1. Line 1944 needs `(ζ^ρ)²`, and Sec13_1 precedes Sec13_3.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T16:53:23-04:00

LEDGER INCIDENT (not a source error; no Lean change).
- At 2026-10-14 16:50:04 ET a ledger script opened automation/Status.md for writing before computing the new content. Its row-length assertion then failed and left the file empty.
- Repair: the file was rebuilt from the committed version (HEAD 82f5d2a) by replaying, in order and with their original timestamps, the 26 row replacements recorded in this session's transcript (05:36:17 to 16:07:04 ET).
- Checks: the rebuilt file agrees with every printout of the file in the transcript and with the recorded `git diff --stat` row counts (19, 22, 23 changed rows at 10:20, 13:13 and 14:44 ET). Line endings (CRLF) and the row count (587 lines) are unchanged.
- The line-1944 update of 16:53:10 ET was applied after the repair. Ledger scripts now compute all new contents before writing any file.

## 2026-10-14T17:19:22-04:00

Line 1967 (freezing at `u_b` and the retention rule), new section at the end of TrilinearHT/Auto/Sec13_1OneExpansionAtFirstMatch.lean.
- `FamParams.frozenZ`: the basic coarse output `Z_(l,G,u)` of the role at the depth `u`, set to zero at depths before the attempt root. On cells of the depth partition with no active ancestor it vanishes by the zero convention of line 1859 (`gBall_zero_before`).
- `gBall_cell_rep`, `basicOut_cell_rep`, `frozenZ_cell_rep`: on every cell `U` of the depth partition the frozen output is zero or a combination, with constant coefficients on `U`, of the main columns on `U` of the primaries at the deepest active ancestor `a` of `U` (retained inherited projections; `ballMaskT_labels_primaries`). Non-active cells are treated through their deepest active ancestor, so no ancestor-closedness of the active cells is assumed.
- `ActualUse`, `retainedV`: a `v_b`-cell (depth `b - 2K`) of the attempt tree is retained for `G` exactly when it contains a cell with an actual use of `G` (active, with a present central vertex of successful color data and group `G`) at a depth in `[b, b + K)`.
- `frozenLift`: `Z̃_(l,G,b) = R_(l,G) Z_(l,G,u_b)` restricted to the retained `v_b`-cells; `frozenLift_off`: it vanishes off them.
- `firstCell_contains`: a first-match cell of a primary at an active cell meeting a subcell `U` contains `U` ("a mode available at `u_b` has first match no later than `u_b`").
- `frozen_endpoint`, `frozenLift_retained`: for the lift of `mainAttemptLift` on the family of all active cells, on a retained `v_b`-cell inside a `u_b`-cell `U` the frozen lifted output is a combination of augmented modes with coefficients `c_(Φ(m)) a_m` constant on `U`, with absolute sum at most `D_*` times the normalized norm of the frozen output on `U`.
- Scope note: the slope oscillation bound `eq:slope-variation` that the blueprint states next (lines 1968-1975) is its own row.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T17:34:32-04:00

Line 1996 (exceptional blocks), new section at the end of TrilinearHT/Auto/Sec13_2TwoGraphsHeightStabilization.lean.
- `ExceptionalAt Θ H r₀ T K b`: the negation of `eq:gap` at the block start `b`: some rational vector of height at most `H` has `T⁻¹ / r_(v_b) < |a·Θ| < T / r_(t_b)`, with `r_n = r₀ 2^(-n)`. `ExceptionalAt.eval_ne_zero`: zero evaluations are always tiny.
- `exceptional_blocks_le`: lem:height (`rational_frequency_logarithmic_cover`) puts the logarithms `x(a) = log₂(|a·Θ| r₀)` of the nonzero evaluations into at most `dim Θ` packets of width `W = 8 (dim Θ + 1)³ log(2H) / log 2`. Exception at `b = b₀ + βK` forces `b - 2K - log₂ T < x(a) < b + K + log₂ T`, and with `W + 2 log₂ T ≤ K` a packet meets at most four block starts (`exceptional_blocks_count`). Hence each primary is exceptional in at most `4 dim Θ ≤ 8 d_B` blocks, which is `C d_max`. The blueprint's count of five starts per packet is improved to four.
- `ModeSchedule.exceptional_blocks_le`: the same at the chosen schedule. `K ≥ W + 2 log₂ T + C_K log₂ D_*` is the field `K_ge` of `eq:mode-parameters`, with `W` the lem:height packet width. `H ≥ 2`, `T ≥ 1` and `K > 0` are derived from the schedule inequalities and the inputs `d_max, D_*, B_* ≥ 2`, `Q₀ ≥ 1` of `chooseSchedule`.
- This replaces the earlier attempt bound of about `2 (3H²)^d` exceptional blocks.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T17:48:30-04:00

Lines 1997-1998 (the tiny span at a nonexceptional block), new section at the end of TrilinearHT/Auto/Sec13_2TwoGraphsHeightStabilization.lean.
- `tinyKB`, `mem_tinyKB`: `K_B = {w : (0, w) ∈ K_rat}` as the comap of the tiny span under `w ↦ (0, w)`.
- `tinySpan_const_le`: the spanning constant `(3H²)^d d! H^(d²+d)` of `tiny_of_mem_tinySpan` is at most `(d_max H)^(4 d_max⁴)` for `d ≤ d_max`. This is the blueprint's coefficient-sum bound `(d_max H)^(C d_max³)`, written with exponent `4 d_max⁴`, which suffices against `T`.
- `ModeSchedule.tiny_of_mem_tinySpan`: at the chosen schedule, at a nonexceptional block (`eq:gap` with `T⁻¹ / r_(v_b)` and `T / r_(t_b)`, `r_n = r₀ 2^(-n)`), every vector of height at most `⌊H⌋` in the span of the tiny height-`⌊H⌋` vectors is tiny. The smallness hypothesis of the earlier attempt is now derived: the threshold ratio is `T² 2^(3K)`, and `T > (d_max H)^(C_T d_max⁴) Ξ` (field `T_gt`) with `C_T ≥ 4` dominates the spanning constant. `C_T ≥ 4` is the choice of the absolute constant `C` in `eq:mode-parameters`; `H ≥ 2` and `T ≥ 1` are derived from `H_gt`, `T_gt` and the inputs `d_max, D_*, B_* ≥ 2`, `Q₀ ≥ 1`.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T18:09:51-04:00

Lem:stabilize (lines 2002-2028), TrilinearHT/Auto/Sec13_2TwoGraphsHeightStabilization.lean.
- `ModeSchedule.stabilize_pre` now concludes the direct PRE edge (`gapEdge` with threshold `Ξ/r_v` at height `h - Δ`), as the blueprint states ("directly adjacent in PRE"); `hstab_of_primaryGood` recovers the component form through `ofEdges_E_of_pre`. The hypothesis `hEcur` is replaced by its integer form (an integer `z` with `|z| ≤ #modes · E_h` has `|z| ≤ D · Eq h`), which is all the proof uses. This lets the witness bound be exactly `⌊D_* E_h⌋`.
- Elementary consequences of `eq:mode-parameters` (new block before `ModeSchedule.tiny_of_mem_tinySpan`): `Valid.two_le_Cstar`, `dmax_le_Cstar`, `one_le_A0`, `thirty_le_Rht`, `Cstar_lt_two_pow` (`C_* < 2^(R - 10)` from `R ≥ log₂ C_* + 30`), `base_le_A0`, `six_le_A0`, `H_ge` (`27 D_*⁴ (E_(J_*) L_(J_*))² < H`), `two_le_H`, `Dstar_lt_H`, `H_mul_Ξ_lt_T`, `one_le_T`, `tinySpan_small`. `ModeSchedule.tiny_of_mem_tinySpan` now uses `tinySpan_small`; its statement is unchanged.
- `blockGraphs`: the PRE and CURRENT components of the block with start `b` on the `v_b`-cell `[a₀, a₀ + r_(v_b)]`, `r_n = r₀ 2^(-n)`. `Ξ_div_lag_le`: `Ξ/r_(v_b) ≤ Ξ/r_(t_b)`.
- `witE`, `kerS`: the bounds of the spans `V_i` and `U_i` of the proof. `⌊D_*⌋ · witE i = ⌊D_* E_i⌋` (`D_mul_witE`), so for integer witnesses this is exactly `|m|_∞ ≤ D_* E_i`; `kerS i = ⌊C_*³ D_* E_i⌋`, exactly `|z|_∞ ≤ C_*³ D_* E_i` for integer vectors. `witE_succ` (`6 witE i ≤ witE (i+1)`) and `kerS_mono` give the monotonicity used in the rank count.
- `stabGood`: the height `h` is good for the primary when the primary is nonexceptional at the block (`eq:gap` at height `⌊H⌋`), `h ≥ R_*^ht`, and `V` and `U` do not change between `h - R_*^ht` and `h`.
- `Valid.stabGood_bad_card`: for a primary with `¬ExceptionalAt` at the block (line 1996), at most `3 d_max R_*^ht` heights are not good (`C = 3`).
- `Valid.stabGood_pre`: for `h ≤ J_*` good for the primary of `x`, a mode `x'` of the same primary in the CURRENT component of `x` at `h` is directly PRE-adjacent to `x` at `h - 10`. All side conditions of `stabilize_pre` are derived:
  - the expansion constant is `≤ C_* < 2^(R - Δ)` (`Valid.expandConst_le`, `Valid.Cstar_lt_two_pow`), and `(3D²)^d ≤ C_*` (`Valid.three_sq_pow_le`);
  - the cleared kernel vector has size `≤ C_*³ D_* E_h`;
  - the PRE witness has size `≤ E_(h-Δ)` by the fixed power `A₀ ≥ (C_* 6^R B_* D_*)^(C_A)` with `C_A ≥ 5` (`Valid.stab_le_A0`, `A0_mul_Eh_le`);
  - `D_* Ξ < T`;
  - the heights of the CURRENT and PRE relations are at most `⌊H⌋` for `h ≤ J_*` (`Valid.height_budget`, `Valid.ceil_budget`);
  - the tiny-span smallness comes from `T_gt` with `C_T ≥ 4`.
- `Valid.stabGood_mem_E`: the same in component form, as used by the coherence row.
- `Valid.stabilize`: the blueprint statement. For a nonexceptional primary `p`, at most `3 d_max R_*^ht` heights `h ≤ J_*` fail to have the property "`h ≥ Δ`, and two modes of `p` in one CURRENT component at `h` are directly adjacent in PRE at `h - Δ`".
- Inputs, all part of the blueprint's data:
  - the number of modes on the list is at most `D_*` ("covering all mode counts"; "a simple CURRENT path has at most `D_*` edges");
  - the frequency vectors `Θ_q = (θ_(v,q), ϑ)` have dimension at most `d_max`;
  - same-primary slope differences are `a·Θ_q` with `a` of height at most `D_*` (`eq:mode-differences`, which `D_*` covers);
  - heights range over `0 ≤ h ≤ J_*`, where `E_h` is defined, and `Δ = 10`.
- Choices of absolute constants: `C_A ≥ 5` for "a sufficiently large fixed power" and `C_T ≥ 4` for the `C` in `T`.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T18:20:32-04:00

Lines 2039-2044 (coherence of the good predicates), new section at the end of TrilinearHT/Auto/Sec13_2TwoGraphsHeightStabilization.lean.
- `ModeSchedule.heightGood`: the heights good for a primary within the height range `0 ≤ h ≤ J_*` of the schedule: `h ≤ J_*` and `stabGood` (nonexceptional at the block, and the spans of lem:stabilize stable). This is the predicate "nonexceptional and good for the primary at `h`" of `eq:good`.
- `Valid.heightGood_stab`: the `hstab` hypothesis of the generic coherence lemmas, now discharged at every height from `Valid.stabGood_mem_E` (lem:stabilize).
- `Valid.good_same_predecessor`: two good modes (`eq:good` with `Δ = 10` and `heightGood`) in one CURRENT component at `h` of the block graphs have the same PRE predecessor at `h - Δ`.
- `ModeComponents.core_iff_of_minimal_pre`: modes in one minimal PRE component have the same bad heights, so the core/side decision is constant there.
- `Valid.core_good_iff`: two core modes in one minimal CURRENT component have identical good predicates on `eq:upper-heights` (`⌈4 δ_* J_*⌉ ≤ h ≤ J_*`). The conditions `J_* ≥ 2` (`Valid.two_le_Jstar`, from `Jstar_ge` with `C_J ≥ 1`, `δ_* ≤ 1` and `D_m ≥ 2`, an input of `chooseSchedule`) and `⌈4 δ_* J_*⌉ ≤ J_*` are derived.
- `Valid.core_bad_proportion`: a core mode has bad proportion at most `2 δ_*` on the upper heights.
- Choices of absolute constants: `δ_* ≤ 1/16` for "a sufficiently small absolute `δ_*`", and `C_J ≥ 1` for the `C` in `J_*`.
- `ModeSchedule.sideParams` is redefined from the blueprint data: `D = ⌊D_*⌋`, witness bound `⌊D_* E_h⌋` (`witE`), kernel size `⌊C_*³ D_* E_h⌋` (`kerS`). It was previously unused, and its old witness bound `⌈D_*⌉ ⌈D_* E_h⌉` did not match the blueprint.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T19:20:23-04:00

Lem:lift-composition (lines 2062-2077), on the main columns. New section at the end of TrilinearHT/Auto/Sec13_3BesselRowsLinearSideEnergy.lean; one generalization in TrilinearHT/Auto/Sec12_4BinaryLocalizationVariation.lean.
- `basic_compression` (line 1859, Sec12_4) now takes an arbitrary input `Z` of the basic family instead of the fixed `F_(l,j)`; the statement is otherwise unchanged and it had no other callers. This allows the input `1_R F_(l,j)`, whose energy is at most `|R|`.
- `piLpSingle`, `norm_piLpSingle`: the isometric embedding of one summand into the `ℓ²` sum `PiLp 2 F`. The rows of different groups have different targets; this embedding puts them in one space for the compression lemmas.
- `cell_ballFamT`, `gBall_restrict_comm`, `gBall_adjoint`: the outer ball filter at the depth of an active cell is the cell projection after restriction, commutes with the restriction, and is self-adjoint.
- `main_rows_group`: for one group, `lem:compression` with one factor inserts the outer averaged ball projection at the depth of each decision cell (cost `C₁²` of the main tree).
- `gBall_row_adjoint_mem`: the adjoint of `Q L_(l,G,u)` takes values in the main ball range of `u` at the largest pad. Masks grow with the pad (`bmask_pad_mono`, `mainRange_mono`). This is "every term of `A_G^*` has outer factor `L_(l,G,u_e)`, so its range is a sum of whole usable main endpoint ranges".
- `main_rows_joint`: the rows of all groups of one color, local to active decision cells with downstream use certificates (`Cert`), are jointly Bessel after the outer ball projections, with constant `(1 + τ N colBudget²) c C₁²`. This combines `eq:whole-ranges` (`mainRange_wholeRanges`) with `joint_bessel_hetero`.
- `lift_rows_history`: compression again (`basic_compression`) inserts the shared history and the basic projections acting on the family input (cost `C_|ls|² C_(1,j_b)²`).
- `row_out_restrictR`: rows local to active cells see the family input only through `1_R F`.
- `lift_rows_bessel`, `lift_rows_local`: the lift `R_(l,G)` (any `LiftData` on the main columns, norm `≤ √5`) keeps per-group Bessel bounds (factor 5) and locality.
- `lift_composition_global`, `lift_composition`: for mode rows `P_(G,e)` with per-group Bessel constant `c` (the blueprint's `G₀`), local to sets `J_(G,e)` inside active cells `u_(G,e)` with downstream use certificates of `G`, the outputs `P_(G,e) R_(l,G) L_(l,G,u) B_(l,u) B_l` have joint squared sum at most `2 (1 + τ N colBudget²) 5c C₁² C_|ls|² (C_(1,0)² + C_(1,1)²) |R|`.
  - `lift_composition` uses the leaf output `ballFilt (layerOp cumFilt (basicIn))` at the cell, via `basicOut_restrict`.
  - `lift_composition_G0` gives `c G₀ |R|` with `G₀ = exp(C_q (1 + log 2k)²)` and `C_q = 6144 (c+1)(1024 (c+1) + c + 7) + 4`. It assumes `log(2 D_m) ≤ k^c`, `log(2 colBudget) ≤ k^c`, `|ls| ≤ c (log k + 1)` and `τ N colBudget² ≤ 1`, the hypotheses of `basic_variation_G0`.
  - Only main projections are compressed; the mode budget does not enter the loss.
- Scope, as in the completed lem:variation row:
  - one slot `l`, one color `k`, one ball level `j` and one shared history `ls`, i.e. one leaf of the color search; the groups at a leaf all have its color;
  - `eq:whole-ranges` is used with its point count `N` and the edge-height condition `hHed` as hypotheses.
  - The row modes need not come from the list available at `u_e`; the bound holds for arbitrary rows that are local to `J_e`.
- The earlier catalog-framework statements (`compose_lift_with_main_histories`, `lift_rows_joint`, `lift_composition_catalog`, `attempt_event_rows`) are superseded for this row.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T19:38:43-04:00

`eq:bad-density` (lines 2100-2112), TrilinearHT/Auto/Sec13_3BesselRowsLinearSideEnergy.lean. Part of the in-progress row prop:linear-side (lines 2080-2087); the statement row stays in progress until the proof rows 2114-2118 are done.
- `ModeSystem.chain_events_bound` generalized:
  - the label sets of the chain are bounded by a path-local count `M`, the number of keys of the modes alive at any cell (`hM`), instead of the global mode count `card Md`;
  - the exceptional-block hypothesis is required only for sets of blocks of the events themselves.
  - Its only caller, `group_event_rows`, passes `M = card Md`.
- `ModeSystem.exceptionalAt_of_not_nonexcAt` and `not_exceptionalAt_of_nonexcAt`: with the side parameters of the schedule, `nonexcAt` is exactly the negation of `ExceptionalAt` (`eq:gap`) with `r₀` the base length of the grid.
- `ModeSystem.chain_length_schedule`: at the chosen schedule, a linked chain of side events of one class has length `N ≤ 180 d_max log(2 D_m) / δ_*`, free of the height parameter. The class has blocks on the `K`-grid through `R₀`, at least `3K` apart. The ingredients are derived:
  - a key is exceptional in at most `4 dim Θ ≤ 4 d_max` blocks of the class (`ModeSchedule.exceptional_blocks_le`, line 1996, with the packet width `W ≥ 8 (d_max + 1)³ log(2H)/log 2`);
  - a nonexceptional key is height-bad at most `3 d_max R_*^ht` times at one event (`Valid.stabGood_bad_card`, lem:stabilize);
  - the absorption `2 (Δ + 10 Δ l + 10 A_h (1 + l)) ≤ δ_* (J_* + 1)` follows from `J_* ≥ C_J δ_*^(-2) d_max R_*^ht log(2 D_m)` with `C_J ≥ 340`.
- Inputs:
  - the label sets are at most `M ≤ 2 D_m` at every cell ("their sizes are at most `D_m`");
  - `δ_* ≤ 1`, and `C_J ≥ 340` as the choice of the absolute constant of `J_*`;
  - `d_max, D_*, B_* ≥ 2`, `Q₀ ≥ 1`, `D_m ≥ 2`, as for `chooseSchedule`.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T19:55:46-04:00

Lines 2114-2116 (level rows of the side events), as part of the in-progress row prop:linear-side. Files: TrilinearHT/Auto/Sec13_3BesselRowsLinearSideEnergy.lean and TrilinearHT/Auto/Sec13_1OneExpansionAtFirstMatch.lean; callers updated in TrilinearHT/Auto/Sec13_4SideStatesFixedOffsets.lean.
- `gaugeSq_truncate_full` (Sec13_1): the squared gauge is approximated within `2 B_ζ/2^K` by its Fourier sum over the box, with every finite absolute coefficient sum at most its full Fourier norm `gaugeSqNorm` ("expand `(ζ^ρ)²` with coefficient sum at most `D_*` and tail `D_*^{-300}`", lines 1944, 2055).
- `modeWave_pair_le_full`: the mode pairing bound of lines 2054-2056 with the full Fourier norm, `gaugeSqNorm · 8/(Θ r) + 2 B_ζ/2^K`.
  - `pairConst` is redefined to `gaugeSqNorm · 8/Ξ + 2 B_ζ/2^K`; `cellMode_inner_le` and `modeWave_rows` now use `modeWave_pair_le_full`.
  - The earlier box-count constant `(2·2^(K+1)+1)^d · 8/Ξ` could not reach `D_*^{-200}` in dimension above two. This was a gap in the D_*^{-200} claim of line 2055 (row lem:mode-rows); it is closed here.
- `ModeSchedule.pairConst_mul_le`: `pairConst · D_*^200 ≤ 1` when `gaugeSqNorm ≤ D_*` ("enlarge `D_*` to cover these full Fourier norms") and `2 B_ζ/2^K ≤ D_*^{-300}` ("only then truncate the Fourier series to tails at most `D_*^{-300}`"), with `Ξ = D_*^1000`.
- Path-local mode counts:
  - `ModeSystem.ptSet y` is the set of modes whose first-match cells contain `y`, i.e. the modes on the path through `y`.
  - `level_rows`, `class_rows`, `blockSide_norm_sq_le`, `group_side_energy` and `group_event_rows` now assume `|ptSet y| ≤ D` and `|ptSet y| ≤ ε D²` at every point, instead of the global `card Md`.
  - The multiplicity argument counts the events of one level through a point by their disjoint mode sets inside `ptSet y` (`card_le_of_pairwiseDisjoint_subset`).
  - The older catalog-framework callers convert their global bounds with `ptSet_card_le`.
- `ModeSystem.group_event_rows_schedule`: at the chosen schedule, for one group, the side-event rows (projections onto the spans of the modes of each event) are Bessel with constant `6 (⌊180 d_max log(2 D_m)/δ_*⌋ + 1)`:
  - three classes of blocks on the `K`-grid; longest-chain levels within each class;
  - lem:mode-rows on each level, with cross pairings `≤ D_*^{-200}` (so `η D_*³ ≤ 1`), at most `D_*` modes through each point and inverse private weights at most `D_*`;
  - chain length from `eq:bad-density`.
  - Inputs ("`D_*` covers ..."):
    - mode curvature `Λ ≤ D_*`;
    - `gaugeSqNorm ≤ D_*` and the truncation tail `≤ D_*^{-300}`;
    - the common cutoff `B_* ≥ Q₀ 2^(K_f+1)` covers the truncation box, so `E₀ = A₀ ≥ B_*` allows every retained shift.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T20:12:36-04:00

Line 2118 (exact side subtotals and their errors), as part of the in-progress row prop:linear-side. File: TrilinearHT/Auto/Sec13_3BesselRowsLinearSideEnergy.lean.
- `sum_sum_measureReal_le_of_count`: sets inside `R`, at most `N` of them through each point of `R`, have total length at most `N |R|`. This is the counting form of the path budget, for a family of families of sets.
- `ModeSystem.class_count`: within one class of blocks whose chains have at most `L` links, the side events through a point `y` number at most `(L + 1) |ptSet y|`. On one longest-chain level, the events through `y` have pairwise disjoint nonempty mode sets inside `ptSet y`, by `level_pair`.
- `ModeSystem.group_count`: at the chosen schedule, the side events of one group through `y` number at most `3 (⌊180 d_max log(2 D_m)/δ_*⌋ + 1) |ptSet y|`. This uses three classes and the chain length from `eq:bad-density`.
- `ModeSystem.side_errors_negligible` (the D_*^-190 bound and "these squared additive errors are negligible"): for the groups with frozen coefficients whose square sums are at most `B_c` on every pre-cell, assuming
  - at most `D_*` modes alive at each cell;
  - `gaugeSqNorm ≤ D_*` and truncation tail `≤ D_*^{-300}`, so cross pairings are `≤ D_*^{-200}`;
  - at most `D_*` modes through each point across all groups (the path budget, "all groups are included in the path budget");
  - pre-cells inside the root `R`;

  the following hold:
  - the error `eventErr` of each exact side subtotal (`event_subtotal_close`) satisfies `err² D_*^{397} ≤ B_c |J|`;
  - the total over groups, blocks, pre-cells and events satisfies `(Σ err²) D_*^{396} ≤ 3 (⌊180 d_max log(2 D_m)/δ_*⌋ + 1) B_c |R|`.
- The blueprint normalizes the complementary coefficient norm to `D_*` and the error to `D_*^{-190}`. Here the coefficient bound `B_c` is kept as a parameter (with `0 ≤ B_c`), and the error is relative to `|J|`, which is stronger. The specialization of `B_c` to the frozen coefficients of normalized attempt roots belongs to the assembly of `eq:linear-energy` (row prop:linear-side). As recorded earlier, the per-cell normalization of the root is available from `IsBasicOn` (Sec11_2c), while `HasColumnRep` exports only the root energy; the assembly must thread it.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T21:00:38-04:00

prop:linear-side (`eq:linear-energy`, lines 2080-2087, proof lines 2088-2118). The statement row is now complete. Files: TrilinearHT/Auto/Sec13_3BesselRowsLinearSideEnergy.lean and TrilinearHT/Auto/Sec13_1OneExpansionAtFirstMatch.lean; `cellMode_vanish` moved unchanged from Sec13_4SideStatesFixedOffsets.lean to Sec13_3.
- Sec13_1, frozen-mode data interface (lines 1971-1975):
  - `frozen_endpoint` and `frozenLift_retained` now also export that every mode with a nonzero frozen coefficient is alive on the `u_b`-cell ("a mode available at `u_b` has first match no later than `u_b`").
  - `LiftData.reindex` transports a lift along an equivalence of the primary labels.
  - `MainLiftExports` records the exports of `mainAttemptLift` for one role and group.
  - `exists_mainModeSystem`: the modes of `mainAttemptLift` form a `ModeSystem`, with primary labels relabeled by `Fin n`, whose waves and private weights are those of the lift `R_{l,G}`. It also exports the tag, the curvature bound `B = exp(D X^D)`, the dimensions, the inverse private weights, and the counts of modes through a point and alive at a cell. This makes `linear_energy` applicable to the lift constructed in `lem:first-match`.
- Sec13_3:
  - `liftConst_le_G0`: the arithmetic of `lift_composition_G0`, separated so it can be reused.
  - `lift_composition_finset` and `lift_composition_dep`: lem:lift-composition for row families indexed by finite sets `T_G` (also of group-dependent types). Each is padded with zero rows to one finite index type, and groups without rows are dropped.
  - `ModeSystem.frozenEval_eq_restrict`: a column function agreeing on `J` with `Σ_m β_m ψ_m`, with `β` supported on the modes alive at `u_b`, restricts on `J` to the frozen evaluation.
  - `norm_basicCell_le` and `norm_basicOut_cell_le`: on an active cell, the coarse basic output is at most the two family inputs on the cell.
  - `retained_decision`: the `u_b`-ancestor of a retained `v_b`-cell contains it, is active, and carries a use certificate of the group's color ("their decision cells are the containing `u_b`-cells").
  - `frozen_coeffs`: frozen coefficients on every retained cell. They represent `Z̃ = R_{l,G} Z_{l,G,u_b}`, are supported on the alive modes, and have square sum at most `4 D_*² C_F`.
  - `ModeSystem.eventProj_restrict`: the event projections are local to every cell containing the pre-cell.
  - `linear_energy`, the statement of prop:linear-side for one basic role, color, ball level and shared history: there are frozen coefficients `c_{G,b,J}` representing `Z̃_{l,G,b}` on all retained `v_b`-cells of the blocks `b ∈ Bs`, and the exact side subtotals satisfy `Σ_{G,b} ‖V_{l,G,b}‖² ≤ 24 (⌊180 d_max log(2 D_m)/δ_*⌋ + 1) (G₀ + 2 C_F D_*^{-394}) |R|`, with `G₀ = exp(C_q (1 + log 2k)²)`. The proof uses:
    - `group_side_energy`;
    - `group_event_rows_schedule`, whose Bessel constant is `6 (L + 1)`;
    - `lift_composition_dep` with the `u_b`-cells as decision cells;
    - `side_errors_negligible` with `B_c = 4 D_*² C_F`.
- Hypotheses of `linear_energy` and their blueprint sources:
  1. The mode systems carry the exports of `mainAttemptLift` (`MainLiftExports`; same private weights). `exists_mainModeSystem` provides such systems.
  2. Schedule coverings, i.e. the choices of the a priori budgets (line 1934 and lines 1944-1958):
     - `dvOf + dim ≤ d_max`;
     - label sets at a cell `≤ M ≤ 2 D_m`, as in eq:bad-density ("their sizes are at most `D_m`");
     - `Λ ≤ D_*`;
     - `gaugeSqNorm ≤ D_*` and truncation tail `≤ D_*^{-300}`, with `Q₀ 2^(K_f+1) ≤ B_*`;
     - inverse private weights `≤ D_*`;
     - alive modes `≤ D_*`;
     - modes along a path across groups `≤ D_*`;
     - `modeStar ≤ D_*` (the coefficient budget);
     - the label path count `N_q`, with `τ N_q colBudget² ≤ 1`, and the compression budgets of `lift_composition_G0`.
  3. Fresh normalized attempt roots: `‖1_U F_{l,j}‖² ≤ C_F |U|` on active cells `U`. The proposition is asserted "on fresh normalized attempt roots", and line 414 normalizes the inputs on every cell of the chosen subtree. As recorded earlier, `IsBasicOn` (Sec11_2c) provides per-cell energies on the tree, while `HasColumnRep`/`BasicProjection` export only the root energy. The final assembly must thread the per-cell bound.
  4. `A.AncClosed`, so that the decision cells `u_b` are active. This is the same formulation as `lem:variation` (row of 2026-10-14 14:17:36) and the open entry of 2026-10-12T10:05. Establishing `AncClosed` for the assembled attempt remains open there.
- `Bs` is any finite set of block starts on the `K`-grid; non-retained branches contribute zero. The bound is uniform in the offsets of the mode systems.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T21:13:02-04:00

`eq:sides` and `eq:core-side-error` (lines 2124-2133) on the main columns of the attempt. File: TrilinearHT/Auto/Sec13_4SideStatesFixedOffsets.lean. The earlier `LeafSplit` versions over the superseded `AttemptParams` remain in the file unchanged; they are not used for this row.
- `ModeSystem.blockCore`: the full core subtotal `A_{l,G,b}`. It is the sum, over the retained pre-cells, of the subtotals of the core components (minimal CURRENT components that are not side events) with the frozen coefficients.
- `ModeSystem.eq_blockCore_add_blockSide`: a column function that is supported on the disjoint pre-cells of a block and restricts on each to the frozen evaluation equals `A + V`. Every alive mode lies in exactly one minimal CURRENT component (`frozenEval_sub_side`).
- `retainedV_pairwiseDisjoint`, `frozenLift_eq_core_add_side`: `Z̃_{l,G,b} = R_{l,G} Z_{l,G,u_b}` on the retained branches equals `A_{l,G,b} + V_{l,G,b}`, for the frozen coefficients produced by `linear_energy`.
- `physMain`, `sideState`, `physError`:
  - the physical coordinate in the main column space;
  - the side state `S_{l,G,h} = Z_{l,G,h} - Z_{l,G,u_b} + V_{l,G,b}` (`eq:sides`), in physical coordinates, with the frozen output zero before the attempt;
  - the error `E_{l,G,b} = (Z_{l,G,u_b})_phys - (Z̃_{l,G,b})_phys`.
- `core_side_error` (`eq:core-side-error`): `(Z_{l,G,h})_phys = (A_{l,G,b})_phys + S_{l,G,h} + E_{l,G,b}` for every depth `h` of the block.
- Basic `U` roles take the whole output as the side state, with no core and no error. This is a convention of the blueprint; the decomposition is then trivial.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T21:50:07-04:00

Lines 2135-2150 (the physical error of the frozen lift and the selection of the offsets) and `eq:physical-error` (lines 2151-2156), on the main columns of the attempt. File: TrilinearHT/Auto/Sec13_4SideStatesFixedOffsets.lean. Sec13_1: `exists_mainModeSystem` now also exports the gauge `s = (ζ^ρ)²`; docstrings of `frozen_endpoint`, `frozenLift_retained` updated.
- `norm_mainScalar_le_one`: on an active cell, the scalars of its main labels are bounded atoms (`bf.charts`) or bounded templates, hence at most one.
- `frozenZ_main_rep`: on an active cell `U` the frozen main output is a main combination `Σ_Φ β_Φ (φ_Φ, √ε_Φ e_Φ)` of the primaries at `U` (line 2131). It satisfies:
  - `Σ|β_Φ| ≤ √N colBudget ‖Z‖_U/√|U|` (private-coordinate recovery);
  - its physical supremum on `U` is at most `Σ|β_Φ|`.
- `physError_majorant`: for every lift with the main private weights and gauge `s = ζ²`, on a retained `v_b`-cell the error is `E = (1 - ζ²) Z_phys - Σ_Φ β_Φ q_Φ`. Hence `|E|² ≤ 2|1 - ζ²|²|Z_phys|² + 2 δ_c² (Σ|β|)²`, with `|q_Φ| ≤ δ_c`. This generalizes the earlier template-only version (`ModeSystem.physical_error_le`, which assumed `ε_P = 1`).
- `exists_offsets_used`: for the actual main uses `I ∈ U_i` (fixed before the offsets, at most `N_use` through each point of the root), majorants `2|1 - ζ_i^ρ|² Z + C` with `Z ≤ M` a.e. on the used cells admit offsets in the unit cubes with total at most `(8 d_max δ M + C) N_use |R|`. The proof uses `eq:offset-mean` via `exists_offsets_physical` and the path count (`sum_sum_measureReal_le_of_count`).
- `ancAt_mem_retainedV`: the `v_b`-ancestor of an actual use of the block is retained.
- `physical_error_used` (`eq:physical-error`): there are offsets such that every choice of first-match lifts at these offsets satisfies `Σ_i Σ_{I ∈ U_i} ∫_I |E_{l_i,G_i,b(I)}|² ≤ (8 d_max δ + 2 δ_c²) · 4 N colBudget² C_F · N_use |R|`. Here "every choice" means: main private weights, gauge `(ζ_i^ρ)²`, corrections of size `δ_c`. The offsets are selected by the explicit majorant before the lifts are chosen, so no measurable selection of expansions is used.
- Formulation notes:
  1. The blueprint uses one parameter `δ_c` both for the cutoff width of `ζ^ρ` and for the size of the corrections `q_Φ`; here the cutoff width `δ` and `δ_c` are separate. With `δ = δ_c` the bound is the blueprint's `2 D_m^{C''} d_max δ_c |R|`, where `D_m^{C''}` covers `4 N colBudget² C_F N_use`.
  2. As in prop:linear-side, the hypotheses are:
     - `A.AncClosed` (decision cells `u_b` active; open entry of 2026-10-12T10:05);
     - fresh normalized attempt roots `‖1_V F_{l,j}‖² ≤ C_F |V|` on active cells;
     - the label count `N` at active cells;
     - the path multiplicity `N_use` of the actual main uses ("the main path multiplicity").
  3. Uses in blocks starting before `R.1 + 4K` have zero frozen output and zero error (the zero convention before the attempt).
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T22:04:18-04:00

Line 2159 (integrated budgets of the side states) on the main columns of the attempt. File: TrilinearHT/Auto/Sec13_4SideStatesFixedOffsets.lean. The earlier versions over the superseded catalogs (`rolling_budget`, `linear_budget`, `uslot_budget` in namespace `AttemptParams`) remain unchanged; they are not used for this row.
- `sum_block_le`: a quantity attached to the block start `K ⌊s/K⌋` of each depth is counted at most `K` times ("a fixed `V_{l,G,b}` is counted at most `K` times").
- `basic_variation_overlap_G0`: `eq:variation` with the loss `G₀` for depth intervals colored so that intervals of one color are disjoint.
- `FamParams.rolling_budget`: for blocks `[b, b + K)` on `R.1 + Kℤ` with `u_b = b - 4K` and the frozen output zero before the attempt, the rolling sides `Z_s - Z_{u_b}` on certified cells satisfy `Σ_{s,G} ≤ K (20 G₀ + 32) |R|`.
  - Depths `s ≥ 4K` use `eq:variation`, with the intervals `(u_b, s]` colored modulo `5K` (overlap `O(K)`).
  - The first `4K` depths use the one-time projection estimate (`basic_onetime`).
- `FamParams.uslot_budget`: in a basic `U` role the whole outputs of the inputs `w_s` on certified cells satisfy `Σ_{s,G} ≤ (1 + τ N colBudget²) Σ_s ‖w_s‖²` (current group Bessel, `main_joint`). This is at most `2 C_U |R|` given `eq:basic-side` in the form `Σ_s ‖w_s‖² ≤ C_U |R|`.
  - The identification of `w_s` with the basic `U` inputs `U_{e,s}` of prop:base (whose energy is `eq:basic-side`, proved in `activeCellReduction`) belongs to the attempt assembly.
- `FamParams.sideState_budget`: the side states `S_{l,G,s}` of a basic `B` role on certified cells satisfy `Σ_{s,G} ‖1_E S‖² ≤ 2 K (20 G₀ + 32) |R| + 2 K Σ_{b,G} ‖V_{l,G,b}‖²`. With the frozen coefficients of `linear_energy` (blocks on the `K`-grid through `R.1`), `eq:linear-energy` bounds the last sum ("`eq:linear-energy` gives the same bound").
- As before, the hypotheses include `A.AncClosed` (decision cells active; open entry of 2026-10-12T10:05) and the label path count `N` with `τ N colBudget² ≤ 1`.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T22:12:18-04:00

`eq:side-cap` (lines 2160-2163) for the side states of a search leaf. File: TrilinearHT/Auto/Sec13_4SideStatesFixedOffsets.lean.
- `norm_sq_restrict_biUnion`: the restriction to a disjoint union of cells has squared norm the sum over the cells.
- `side_cap`: `lem:cuts` (`side_caps_of_budgets`) for the cell weights `a(I) = Σ_{ν,G needed at I} ‖X_{ν,G,I.1}‖²_{2,I}` with integrated budgets `Σ_I |I| a_ν(I) ≤ A_ν |R|`.
- `cell_budget_eq` rewrites the budgets of `sideState_budget` and `uslot_budget` over the needed cells of each depth cell by cell.
- `side_cap_states` (`eq:side-cap`): from these budgets, one first-crossing cut of root length at most `ρ |R|` (an arbitrarily small fixed cost) gives, on every retained path, `Σ_{ν,s,G} ‖X_{ν,G,s}‖²_{2,I_s(y)} ≤ (Σ_ν A_ν)/ρ`. This holds simultaneously for all roles.
- `side_cap_le_pow` (the `P^C` form): if `ρ⁻¹ ≤ P` and each budget is at most `P^C`, the cap is at most `m P^(C+1)` for `m` roles.
- The budgets of line 2159 are `A = 2K(20 G₀ + 32) + 2K · 24 (L + 1)(G₀ + 2C_F D_*^{-394})` for basic `B` roles and `2C_U` for basic `U` roles. They are polynomial in `P` by the choices of the parameters:
  - `K` is polynomial in `P, k` (line 1958);
  - `G₀ ≤ P^{1/8}` for large `k` (line 2876, lem:budget-rules);
  - `L + 1 ≤ C d_max log(2D_m)/δ_*` with `d_max, log D_m ≤ k^{O(1)}`.
  The numeric instantiation of these sizes belongs to the final assembly (prop:normalized), as for the other `P^C` statements.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T22:24:26-04:00

Line 2164 (core and error sizes; terms containing a physical error) on the main columns. File: TrilinearHT/Auto/Sec13_4SideStatesFixedOffsets.lean.
- `core_error_sizes`: on a cell `I` inside a retained `v_b`-cell, the lift is pointwise bounded (`‖R‖ ≤ √5`), `Z_{u_b} = Z_s - (Z_s - Z_{u_b})` and `A = Z̃ - V` (`frozenLift_eq_core_add_side`). Hence:
  - `‖1_I E‖ ≤ (1 + √5)(‖1_I Z_s‖ + ‖1_I (Z_s - Z_{u_b})‖)`;
  - `‖1_I A‖ ≤ √5 (‖1_I Z_s‖ + ‖1_I (Z_s - Z_{u_b})‖) + ‖1_I V‖`.
  With the normalized coarse outputs and the side caps on retained paths, these are the `P^C` sizes of the blueprint.
- `cellForm_norm_le_L2`: `eq:absolute` with all exponents two for the cell form, `|H_I(x)| ≤ C_κ Π_j ‖(x_j)_phys‖_{2,I}`.
- `sum_uses_le`: Cauchy-Schwarz over the uses.
- `error_terms_le`: for uses whose error slot has normalized size `e_u` and whose other slots have sizes at most `M`, with `Σ_u |I_u| ≤ N |R|` and `Σ_u |I_u| e_u² ≤ ε |R|` (`eq:physical-error`), we get `Σ_u |I_u| |H_{I_u}| ≤ C_κ M³ √(N ε) |R|`.
- `eLpNorm_augPhys_cell_le`: the normalized size with `|I| e_I² = ∫_I |x_phys|²`, linking `error_terms_le` to `physical_error_used`.
- The bound is `O(e^{-k}|R|)` because `ε` carries the factor `8 d_max δ + 2 δ_c²` with `δ_c = exp(-k^{C_c})` and `C_c` chosen after the main budgets (lines 1897, 2156). The numeric choice belongs to the final assembly, as for the other parameter choices.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T22:34:50-04:00

Helper instantiation (lines 2167-2169) on the main columns. File: TrilinearHT/Auto/Sec13_4SideStatesFixedOffsets.lean. The earlier `helper_instantiation` over the superseded `VTest`/`CatTest` catalogs remains unchanged; it is not used for this row.
- `mainSel_append_highRank`, `mainProj_append_highRank`: catalog columns of rank above `r` do not change the main selections and projections of rank at most `r`.
- `MainTest.pass_append_highRank`: main tests with target and history ranks below the inserted columns keep passing.
- `ballFilt_append_helper`, `cumFilt_append_helper`: the ball filters of the levels `j ≤ 4` (ranks `L + j`) and the cumulative filters (ranks `L - m + 1`) are unchanged by helper columns of rank `L + 5`. Hence the main projections, and the outputs and side states built from them, are unchanged ("helper ranks exceed every main rank, so their insertion leaves all previously fixed main projections, offsets and side states unchanged").
- `helper_instantiation_main`: the universal helper part of `lem:closure` (`helper_closure`) applied to helper tests of rank `L + 5` on fixed whole bases at the active cells. It gives helper templates of rank `L + 5` such that:
  - all helper tests pass;
  - every main test of ranks at most `L + 4` still passes;
  - the ball and cumulative filters are unchanged;
  - the insertions per cell are counted by the closure ratio times `n_{L+4}`.
- `sideState_base`: the side states (any physical column function) restricted to an active cell are admissible helper bases. Their template coordinates vanish and they are supported on the cell ("the helper bases are these entire states").
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T22:47:46-04:00

Lines 2172-2185 (hereditary representatives and cross-mode non-adjacency). File: TrilinearHT/Auto/Sec13_5RepresentativesComponentSizesFirstTops.lean. This resolves the representatives part of audit item 11: the stabilization hypothesis is now discharged.
- `ModeSystem.blockComps_stab`: `lem:stabilize` for the frozen mode graphs at the schedule. The graphs `blockComps` are the block graphs of `ModeSchedule.blockGraphs`, and `goodP` with the side parameters is `stabGood`. So two alive modes of one key, good at a height `h ≤ J_*` and lying in one CURRENT component at `h`, are PRE-joined at `h - 10` (`ModeSchedule.Valid.stabGood_mem_E`). Its hypotheses are schedule constants and the `D_*` choices (lines 1932-1934):
  - the alive modes at the decision cell number at most `D_*`;
  - `d_v + dim z ≤ d_max`;
  - `2 (Q₀ (3 B_σ²)²)² ≤ ⌊D_*⌋` (heights of mode differences).
- The hypothesis `hstab` of `predecessor_nesting`, `attempt_representatives`, `attempt_representatives3` and `typed_representatives` is weakened to the single height `h` used ("a later nonexceptional height-good one").
- `nodeType1`, `nodeType2` and `typed_representatives` are moved from Sec15_4 to Sec13_5 (lines 2172-2174: "Fix height, role, group and type").
- `typed_representatives_sched`: for fixed height `h ≤ J_*` (the upper end of `H_up`, line 2041) and types, with `Δ = 10` and the side parameters of the schedule, representatives exist in the PRE predecessors. They are:
  - inherited under predecessor inclusion along comparable nodes;
  - for different representatives on comparable nodes, carried by disjoint predecessors with no shared or CURRENT-adjacent modes in the later graph.
  The node hypotheses (alive, good, distinct components) come from `classNodes_props`.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-14T23:13:04-04:00

`eq:size-comparison` (lines 2196-2209), instantiated at actual cells. File: TrilinearHT/Auto/Sec13_5RepresentativesComponentSizesFirstTops.lean. The setting is an actual cell `I` with `|I| ≥ r_{t_b}`, inside a pre-cell `J` (depth `v_b`) of the block `b`.
- `actualCell_inner_le`: two modes alive at `u_b` that lie in different minimal (height zero) CURRENT components pair on `I` by at most `η |I|`, where `η` is the pairing constant at `Ξ/2`. The proof goes through `alive_representative_separation` (`eq:slope-variation` halves the CURRENT threshold on the whole pre-cell) and `cellMode_inner_le_of_sep`. At the schedule `η ≤ 2 D_*^{-200}` (`pairConst_half_mul_le`).
- `compSizeSq` is `eq:component-size` with normalized norms:
  - the minimal CURRENT components `D ⊆ F_h(x)` are `minComps`;
  - the core subtotals are `A_D = Σ_{m core in D} α_m Ψ_{I,m}`;
  - core means `IsCoreAt`, i.e. at most `δ_*(J_*+1)` bad heights.
- `size_comparison`: `σ_F² ≤ 12 (‖P_{F,I} Z̃‖²_{2,I} + ‖V_F‖²_{2,I}) + 3 B_c D_*^{-59}`. Here `Z̃` on `J` is the frozen evaluation `Σ_{m alive} c_m Ψ_{J,m}`, which equals `R_{l,G} Z_{l,G,u_b}` on `J` by `frozen_coeffs`; `B_c` bounds `Σ |c_m|²`, and `B_c = 4 D_*² C_F` there. The pieces of the bound:
  - almost orthogonality of the `A_D` (lower half, `component_sizes`);
  - the coefficient floors, at most `D_*^{-59} B_c` (blueprint: `C D_*^{-58}`);
  - complementary pairing against the range of `P_{F,I}`: `‖P_{F,I} Z̃ - T_F‖² ≤ 4 D_*^{-397} B_c |I|` (blueprint: `D_*^{-190}`).
  The blueprint's `+ D_*^{-50}` is `12 C_F D_*^{-57} ≤ D_*^{-50}`, a `D_*` covering choice.
- Schedule hypotheses are those of `linear_energy`: `Λ ≤ D_*`; the Fourier norm and tail of the squared gauge are covered by `D_*`; inverse private weights `≤ D_*`; at most `D_*` alive modes.
- `side_comparison` and `side_comparison_block`: for any family of height-`h` CURRENT components (the successful ones), `Σ_F ‖V_F‖² ≤ 2 ‖1_I V_{l,G,b}‖²`. This uses:
  - `restrict_blockSide_actual`: the block side subtotal restricted to `I` is the side synthesis on `I`;
  - `sum_sideEvents_eq`: the side events partition the side modes, by `core_iff_of_minimal_pre`.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-15T00:08:28-04:00

prop:tops (`eq:top-count`, lines 2212-2229), instantiated on the successful components and their hereditary representatives. File: TrilinearHT/Auto/Sec13_5RepresentativesComponentSizesFirstTops.lean.

Representatives and nodes:
- `comp_cross_sep` (via `pred_nested_of_link`): the stronger cross-mode conclusion. Comparable nodes of one type class with different representatives have no mode of the earlier component equal or CURRENT-joined to a mode of the later component in the later graph.
- `succModes` and `succNodes`: the successful components (those containing a core mode good at `h`), one node per component, namely the good mode of least index. `exists_succMode` shows every successful component has its node; `succNodes_props` gives the node hypotheses.
- `exists_repClass`: for every height `h ≤ J_*` and type, the hereditary representatives of `typed_representatives_sched` on these nodes. Blocks are `K`-spaced and stabilization comes from `blockComps_stab`.
- The earlier `classNodes` needed a class-mode map into possibly empty alive sets, so it is not used here.

First tops (lines 2221-2222):
- `firstTops`: the maximal use cells of a representative above the threshold. `RepClass.pair_sep`: tops of one representative do not overlap; overlapping tops of different representatives have disjoint component mode sets separated at `(Ξ/2)/|I|` on the smaller cell. `RepClass.topRow_injOn`: distinct tops have distinct rows.
- `RepClass.firstTops_rows`: `lem:mode-rows` with the path counts (`tops_rows_path`, `ptSet`) in place of the global mode count; Bessel constant `2`.

Energy of the tops (lines 2222-2228, `tops_energy`):
- Decision cells are the containing `u_b`-cells. They are active and certified (`retained_decision` with `A.AncClosed`, the precedent of lem:variation), so `lift_composition_dep` and `liftConst_le_G0` give `Σ_tops ‖P_{F,I} Z̃‖² ≤ 2 G₀ |R|`.
- Side part: `RepClass.tops_side`, `Σ_tops ‖V_F‖² ≤ 2K Σ_{G,b} ‖V_{l,G,b}‖²`, by `side_comparison_block` at each cell and disjointness at each depth. `eq:linear-energy` then applies; `linear_energy` now also exports its coefficient bound `Σ |c|² ≤ 4 D_*² C_F`.
- Absorption: `RepClass.tops_absorb`, using `eq:size-comparison` and `6 B_c D_*^{-59} ≤ σ₀`.

Cuts and counts (line 2229):
- `tops_cut_many`: first crossings of the partial top counts for all choices at once, with cost split evenly over the `N` choices.
- `exists_firstTop_above` and `card_reps_le_firstTops`: each used representative has a first top above its use.
- `first_top_count` and `first_top_count_main`: from the hypotheses of `linear_energy`, the representatives, `24 C_F ≤ D_*^{55}` and finite sets of types and of thresholds `σ ≥ D_*^{-1}`, there are frozen coefficients, representative classes and cuts of length `≤ ρ|R|` such that off the cuts `Σ_G |A_G| ≤ min(D_*, M N/(ρ σ²))`. Here:
  - `M = 24 (2 G₀ + 2 K V₀)`, with `V₀` the linear-energy constant;
  - `N` is the number of choices of height, type and threshold. It is polynomial in `P, k` because heights are at most `J_*` and types and dyadic thresholds number `O(log D_*)`, with `log D_* ≤ P^C`;
  - `G₀ = P^{o(1)}` (budget rules).
- `usedReps_le_Dstar`: the `D_*` bound for every threshold, which covers the bins with `σ < D_*^{-1}`.
- `compSize_le`: `σ_F² ≤ 12 (‖Z̃‖²_{2,I} + 2 ‖V‖²_{2,I}) + 3 B_c D_*^{-59}` (projection contraction and `eq:size-comparison`). With the `P^C` sizes of `Z̃` and `V` on uses (line 2164, side caps), component sizes are at most `P^C`, and bins above that are empty. `eq:side-cap` is `side_cap_states`.

Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-15T00:20:24-04:00

Lines 2236-2237 (the helper rank on the side states). File: TrilinearHT/Auto/Sec14_1TransferPairedDefects.lean.
- `sideState_restrict_base`: the side state `S_{l,G,s} = (Z_s)_phys - (Z_{u_b})_phys + (V_{l,G,b})_phys` (`sideState`), restricted to an active cell, is an admissible helper base. Its template coordinates vanish ("their extra private directions are distinct from the fresh helper directions"), and it is supported on the cell.
- `helper_sides`: for fixed degrees there are `C` and `k₀` with the following property. For `k ≥ k₀`, take every attempt whose closure data are `exp(k^{O(1)})` (as in `closure_poly`), with at most `exp(k^c)` groups, and with room for `exp(k^C)` helper insertions per active cell in the main columns. Consider the helper tests of rank `L + 5`: all target masks and named histories (`HelperName`), on the whole side states of the groups. They close with helper templates such that:
  - every main test of ranks at most `L + 4` still passes;
  - the ball and cumulative filters are unchanged;
  - the helper insertions per cell number at most `n_{L+5}`, with `log n_{L+5} ≤ k^C` ("the helper count still has logarithm `k^{O(1)}`, independently of the mode count").
  The bases are entire side states, never individual modes, heights or amplitudes. The proof combines `closure_poly` with `helper_instantiation_main`.
- The room in the main columns, `|cat_l| + |cells| exp(k^C) ≤ M_c`, is the choice of `M_c`, as for the main closure.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-15T01:46:26-04:00

Lines 2252-2256 (far bands) and eq:transferred-main, lines 2257-2263, on the main columns. File: TrilinearHT/Auto/Sec14_1TransferPairedDefects.lean.

Moved declarations (no mathematical change). The transfer section precedes the short-block file, so these generic lemmas moved from Sec14_2bShortBlockSummation.lean to Sec14_1: `opAvg_const`, `chainDefectSel`, `chainDefectSel_le`, `operatorComplementProduct_succ_shift`, `rankMerge_length`, `posExpand_mem_length`, and `chainDefect_split` from Sec14_5CommonCutsHullMaximaSummation.lean.

Merged transfer steps on the main columns (lines 2240-2252):
- `filtAvgM`, `toStepM`, `mergeStepsM`: helper pads of rank `r_H` on the side slot, main pads of the filter rank on the complement slot.
- `chainVal_mergeStepsM_c/d`, `chainSide_mergeStepsM`, `mergeStepsM_decomp`: ports of the template-catalog versions.

Far bands (lines 2252-2256):
- `far_stepM`: one step, from `far_term_main`.
- `chainPair_farM`: a whole merged chain. The main levels `β_m(r)` depend on the removed rank `r` and the coefficient sums `C_o(r')` on the outer rank `r'` of the other complement (`r' = 0` when it is unfiltered). The step bound is needed only for `r' < r`: by `rankMerge_decomp` and distinct ranks across the two slots, the other complement has a strictly lower-rank outer primal (line 2241).
- Leaf ingredients:
  - `slotFiltM`: the ball filter of the role level, then the cumulative layers. `slotFiltM_suffix_cons` and `slotFiltM_suffix` give the suffix structure.
  - Neighbor closure: `filtOK_cum` (triangle inequality) and `filtOK_ball` (lem:masks, at pads below `H_max` by `bbase_le`).
  - Sources of the other complement: `srcDataM_basic` (its available original columns, coefficient sum `D √(2D) S`) and `srcDataM_filt` (`avg_expansion`, coefficient sum `D √N S`).
  - Main tests of a removed filter: `chain_passM` (`layer_residOK` on single-target named tests).
  - Helper tests of a step: `helper_stepPass` (`avg_history_pass` on the named helper tests on the fixed base).
- `leaf_farM`: the far defects of a chain pair are at most `#steps (P + 1)² 8 τ₃ S_z² S_a S_b` (`far_numeric`), under three conditions:
  - `τ_r D √n_{r-1} ≤ τ₃` for the main thresholds. `catThreshold_cancel` shows the closure thresholds satisfy this, since `colBudget ≤ D` (line 2256: the coefficient factor is canceled by the denominator in eq:catalog-test).
  - `τ_H D √n_{L+4} ≤ τ₃` for the helper threshold.
  - `τ₂ D² √n_{L+4} √N_H ≤ τ₃` ("fixed powers of the main and helper budgets were included before choosing `τ₂`").
- `leaf_far_search`: the chain hypotheses hold at the leaves of the guarded search:
  - splits lie in `[1, L]` (`leafAt_layers_ge`, `posExpand_mem_sub`);
  - splits are distinct across slots (`leafAt_layers_distinct`);
  - ball levels are distinct (`SearchLeaf.role_injective`);
  - there are at most `2 fuel + 2` steps.
- From `τ₂`-bound to `D^{-C₃}`: with `τ₃ = D^{-C_τ}`, polynomially many steps, `(P+1)²` band pairs and `S_z` bounded, the bound is `D^{-C₃} S_a S_b` once `C_τ` is large. `C_τ` is fixed at assembly, as in prop:localize.
- Assembly obligation: the helper threshold `τ₃/(D √n_{L+4})` needs path counts `n` that dominate the main label counts at rank `L + 4`. One sequence from `closure_poly` for both the main and the helper closures meets this, because its `K_t` covers both name types.

eq:transferred-main (lines 2257-2263):
- `leaf_transferM`: the form of the sides and the whole leaf outputs is the signed sum over pairs of positive chains of the transferred main term plus `chainDefect`. `chainDefect_split` separates the near and far band pairs.
- The side operator `D_{a,s}`: by `chainSide_mergeStepsM_eq` it is the product of the helper averages of the steps. By `leaf_steps_le` it has at most `2 fuel + 2 = O(log L)` factors.
- Restoration: `Ucol` is the basic side `U_l` in the main columns. `basicIn_add_Ucol` shows `B_l + U_l` is `Y_l` on the cell. `leaf_transferred_mainM` gives `H(D S_a, S_b, Y_c, Y_d)` minus three corrections, each with an extra basic side `U`, plus the defects.
- Line 2263:
  - `slotFiltM_suffix_shared` and `slotFiltM_cum_inner`: a remaining complement either has the positive ball outermost or is the same for every group, and a removed cumulative filter has only shared layers inside.
  - `terminal_band` splits the terminal band.
  - `chainDefectSel_eq_sum` (Sec14_3) arranges the sum at fixed offsets.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-15T01:59:31-04:00

Line 2373 and lines 2382-2384 (power costs, the transferred main term, restoration errors). File: TrilinearHT/Auto/Sec14_3PowerCostsFrozenComplements.lean.

Line 2373:
- `poly_budget_caps`: at most `P^{C₁}` families of nonnegative cell weights, each with integrated budget at most `P^{C₂}|R|`, are capped simultaneously at `P^{C₁+C₂}/ρ` by one first-crossing cut of length at most `ρ|R|` (from `side_caps_of_budgets`, i.e. lem:cuts).
- The sizes `P^C|R|` of the individual budgets named after line 2373 are proved in their own rows (frozen complements line 2386, flags line 2388, stack energies lines 2393-2399).

Lines 2382-2384, on the main columns:
- Integrating the path caps and the fourth strong factor are covered by `power_cost_bound` and `prod_four_le_of_three` (generic).
- `norm_Λc_le_sizes`: the main-column cell form is bounded by `C_κ` times the product of the normalized sizes.
- `Λc_pair_smallM`: with a pair-small pair in the slots `c, d`, the cell form is at most `τ S_a S_b`.
- `main_restoredM`: the transferred main term with `Y_c = B_c + U_c`, `Y_d = B_d + U_d` (`Ucol`, `basicIn_add_Ucol`) is at most `η S_a S_b`. Pair-smallness of `(Y_c, Y_d)` at the active cells is an input from the exported base data: the final base-data theorem gives `PairSmall ... (Y I s) (Y I s') (2 η₀)` for `s ≠ s'`.
- `restore_corrM`: a restoration correction is at most `C_κ S_a S_b S_u S_v`, with one of `u, v` a basic side `U`.
- `leaf_main_groupsM`, with `norm_chainSide_mergeStepsM` (the helper product is a contraction) and `group_pair_le` (Cauchy-Schwarz in groups): at one cell and chain pair, the restored main terms of the current groups sum to at most `η √(Σ_G ‖x_G a‖²) √(Σ_G ‖x_G b‖²)`. With path caps, `pair_small_main_bound` gives the absolute cost `η √(C_a C_b) |R| = η P^C |R|`.
- `leaf_corr_groupsM`, with `group_triple_shared_le`: the restoration corrections of the groups sum to at most `C_κ √(Σ_G ‖x_G a‖²) √(Σ_G ‖x_G b‖²) S_u S_v`. This is three strong factors with the group sum taken first; `power_cost_bound` gives `eq:three-sides`.
- The numerical transfer errors are the far band defects of `leaf_far_search`: `8 τ₃ S_z² S_a S_b` per step and band pair.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-15T02:24:32-04:00

Lines 2386 and 2388 (frozen complements and flags) on the main columns. File: TrilinearHT/Auto/Sec14_3PowerCostsFrozenComplements.lean.

Single-mask certified variation (lem:variation for an individual pad choice, line 1871: "couple individual pad choices across times"). The chain of `basic_variation` is generalized from the averaged ball output to one outer main projection with an arbitrary inherited mask `M_G`:
- `gOutM`, `gOutM_commute`, `gOutM_rows_blk`, `main_blkM`.
- `main_variationM` comes from `certifiedVariation_gen` in place of `certifiedVariation_avg`. The whole-range conditions are hypotheses `hwr1`, `hwr2` with constant `C_w`.
- `main_jointM`, `main_variation_basicM`, `basicOutM`, `out_restrictRM`, `basic_variationM`, `basic_variationM_le` (`G₀ · 4|R|` for `C_w ≤ 2`).
- Instances:
  - `basic_variation_ballP`: one ball pad of the groups. The whole-range conditions are `main_wr1` and `main_wr2` for that pad, with `C_w = 1 + τ N colBudget²`. This gives joint group budgets for positive ball ranges.
  - `basic_variation_cumP`: one cumulative pad, shared (a single family, `C_w = 1`). This gives shared budgets for group-independent histories.
- Bridges: `basicOutM_ball_restrict` and `basicOutM_cum_restrict` restrict the global pad outputs to an active cell; there they equal the cell pad projections of the layered history of the basic input.

Line 2386:
- `band_stack_le`: the current complementary band stack at a cell has total square at most `‖basic input‖²` (pad bands are orthogonal, `padFamC_bessel`; inner histories are contractions). The other complement is a contraction (`norm_applyAll_filtAvgM_le`).
- Differences from the block start have integrated square budgets `G₀|R|`:
  - for each ball pad, jointly over groups (`basic_variation_ballP`);
  - for each cumulative pad, shared (`basic_variation_cumP`);
  - the shared identity part of the terminal band (`terminal_band`, `slotFiltM_suffix_shared`) via `basic_history_variation_G0`;
  - the other complement with its ball outermost via `basic_variation_G0`, or shared via `basic_history_variation_G0`.
  The polynomial number of bands (`P + 1`) and the `O(K)` overlap of the intervals `[b, s]` (one disjoint family per offset, `sum_le_of_coloring`) multiply these bounds.

Line 2388:
- `freeze_split` and `freeze_four` (generic): the freeze errors and the split of an unbounded frozen complement.
- `flag_ind_le`: the length-weighted indicator of a frozen value above twice the current bound `C₀` is at most `‖u - v‖² / C₀²`.
- `flag_energy_le`: flags set at a cell or at an ancestor at most `K` depths above have total length at most `K C₀^{-2} Σ_J ‖u_J - v_J‖²` (`flag_propagation_le`). With `norm_sq_restrict_biUnion` this is the variation sum over the certified ancestors.
- Ancestors of uses carry downstream certificates (`Cert.mono`). Ancestor closure of the active cells (`AncClosed`) is part of the final base-data theorem.

Assembly obligation: the current uniform bound `C₀` is the normalized size `S_z` of the basic inputs, as in `attempt_localization`, where it is a hypothesis. A bound on the main-column norm of `basicIn` by `D^{O(1)}` must be supplied at assembly.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-15T02:55:16-04:00

eq:stack-energy (lines 2393-2399), the rolling base terms (lines 2415-2419) and the configuration count (line 2419), on the main columns. File: TrilinearHT/Auto/Sec14_4FixedStacksTwoVaryingSides.lean.

Global helper objects in the main column space:
- `gProjC`: a global depth projection of the main base of a catalog with an inherited mask, conjugated by the relabeling of the relevant labels (`colRelabel`, an isometric embedding).
  - It is a projection (`isStarProjection_conj`), nested in the pad (`gProjC_mask_nested`) and commutes with restrictions to coarser cells (`gProjC_commute`).
  - On an active cell it agrees with the cell main projection on inputs in the range of the relabeling (`gProjC_bridge`); physical vectors lie in that range (`physMain_mem_range`, `colRelabel_physEmbed`).
- Transfer descriptors:
  - `slotDescM` and `stepMaskM` give the cell masks of a descriptor; `slotFiltM_eq` and `rankMerge_slotFiltM` show the merged slot filters of a cell are the merged descriptors with their cell masks.
  - `mergeDescM` merges the descriptors of the two slots.
  - `hMaskM` is the helper mask of rank `L + 5` (`mainMaskT_labels_mono` gives pad monotonicity).
- Global helper prefix and band family:
  - `gPreR`: the global history of the helper averages of the prefix descriptors.
  - `gBandR` and `gBandC`: the pad family of the current step after the prefix, conjugated into the main columns.
  - `gBandC_bessel`: the bands are Bessel ("on the banded side pay at most `P + 1` indices").
  - `gBandC_commute`: they commute with restrictions.
  - `gBandC_jump`: the jumps of a fixed input over disjoint intervals cost `(|D| + 1) Σ_{m ≤ |D|} C_m²` (`globHist_jump` with the current pad as a top layer of constant pad family; `layerOp_congr`).
  - `gBandC_bridge`: on an active cell the global band family acts as the cell helper pads after the cell helper prefix, i.e. on the actual transfer values.

eq:stack-energy (lines 2393-2399):
- `varCap_basicOut`: the physical global coarse outputs of a basic slot for a set of groups of one color have variation capacity `G₀ · 4|R|` (`basic_variation_G0`).
- `bandStackM_all`: the banded side. The generic `bandStack_all` is instantiated with `gBandC`, giving the bound `N (2B + 16 (P+2) C_j E_W + 16 (P+2) N C_j N B) + E_W`.
- The untouched side is the generic `posStack_all` with the same capacity and block energy (`N B + E_W`).
- With `B = 4 G₀ |R|`, `C_j` and `E_W` of compression-loss type and `N = O(log K)` levels, these are the bounds `P G₀ |R|` and `G₀ |R|`, logarithms and configurations absorbed in `G₀`.
- The stacks are built from the fixed global objects before any cut.

Lines 2415-2419 (rolling base terms):
- The block input is `W = Z_b - Z_{u_b} + V_{G,b}` (`sideState` at the block start). Its energy `E_W` on the block-start ancestors of the uses is `sideState_budget`: `rolling_budget` (lem:variation on `[u_b, b]` with bounded overlap, the zero convention before the attempt) and the linear-side energy `linear_energy`.
- The certificates are `Cert.mono` on ancestors; ancestor closure is part of the final base-data theorem.

Line 2419:
- `leaf_chain_counts`: at most `2^fuel` leaves and `2^fuel` chains per slot.
- `leaf_steps_le`: at most `2 fuel + 2` steps.
- `config_count_le`: with `fuel, N ≤ c X`, `X = 1 + log 2k`, the total number of configurations is at most `exp((7c + 6) X²)`, a constant of the type of `G₀`.
Full `lake build` passed (9081 jobs, no warnings); standard axioms.

## 2026-10-15T03:44:08-04:00

Lines 2426-2443 (hull mass, joint caps of the actual stacks, `eq:near-band`) on the main columns. File: TrilinearHT/Auto/Sec14_5CommonCutsHullMaximaSummation.lean.

Moved generic lemmas (no change of statement):
- `exceptional_roots_le`, `two_hull_caps`: from Sec16_1 to Sec14_5 (used by line 2428).
- `stackDens` and its lemmas, `useHull` and its lemmas, `unPhase`, `gluedStack_norm_sq_mono`, the depth stacks, `energyAverage_band_le`/`_single_le`, `gluedStack_sum_mono`, `bandStack_outer`, `posStack_outer`, `near_real`: from Sec16_1 to Sec14_5. They are generic in the active setup and the column type.

Line 2426 ("`Σ_ν |Ω_ν| ≤ M₀ |R|` by active multiplicity, the main group count, and the number of configurations"):
- `hull_mult_le`: if the uses of `ν = (G, configuration, block)` lie in a cell set `Act` of point multiplicity `M_p`, carry the group `G` (`fp.groupsAt`), and distinct blocks have disjoint uses, then every point lies in at most `|configurations| M_p D` uses.
- `hull_mass_main`: with `hull_mass_le`, `Σ_ν |Ω_ν| ≤ |configurations| M_p D |R|`.
- `hull_mass_active`: for `Act` = active cells, `M_p` is the path multiplicity of `active_count`, uniform in the setup and in the depth.
- Departure from the superseded attempt route: `near_band_cut` bounded the hull mass by the number of indices, which grows with the number of blocks, i.e. with the depth. The new route uses the point multiplicity, as in the blueprint.

Line 2428 (joint caps of the actual stacks):
- `useHull_max_sub`: the maximal hull cells are use cells.
- `near_band_cutM`: two hull caps `C_{ρ/2} E (1 + log(2 + M_u))` from `two_hull_caps`, with the hull mass `M_u |R|` taken from the point multiplicity `M_u` of the uses.
- `near_band_stacksM`, `near_band_positionsM`, `near_band_positions_UM`: the main-column ports of the configuration and position layers. The hull mass of the indices `(m, k_a, k_b)` is `|K_a| |K_b| M_u`.
- `near_band_actualM`: the actual stacks.
  - Banded side: the global helper bands `gBandC` of the step after its helper prefix, applied to `S_a = Z_a - Z_a(b) + W_a`.
  - Untouched side: `S_b`.
  - Energies: `bandStack_outer`/`posStack_outer` (eq:stack-energy), with the Bessel, commutation and jump properties of `gBandC` proved, not assumed.
  - Use multiplicity: `hull_mult_le` gives `|Ω| M_p D`.

`eq:near-band` (lines 2438-2443):
- `near_band_criticalM`: for a near offset `|o| ≤ 2`, the transfer coefficient `o/P` times the near-band sums is at most `4 C_q (1 + C_N) (1 + log(K+2)) (K+2)^{2(q-2)/(q-1)} (64 B_c B_d) G₀ P^{-1/2} |R|`, with `G₀ = C_{ρ/2} (N+1) (1 + log(2 + (N+1)² |Ω| M_p D)) √(Γ_a Γ_b)` (`near_coeff_le`: `(2/P)(8/7)√(P+2) ≤ 4/√P`).
- `stackEA_le`: the banded stack energy is `(P + 2)` times a `P`-free quantity, which gives `Γ_a`.
- The finite-depth constant is now `C_N` for any `N_d ≥ K` (the original depths). This resolves the `C_K` item of entry 12 of the 2026-10-14 discrepancy list.
- `B_c, B_d` are the unflagged complement bounds; the flags and freeze errors are the power-cost rows.

Full lake build passed (9081 jobs); standard axioms.

## 2026-10-15T06:03:13-04:00

Lines 2375-2394 and 2454-2456 (third strong factors on the main columns). File: TrilinearHT/Auto/Sec14_5bExportedSideEstimate.lean.

Discrepancy found and corrected:
- The superseded `third_budgetM` (with `frzE`, `strTh_sqM`) bounded the third strong factor of each group by its own square and summed over the groups at a cell.
- This counts the `U` restoration energies and the shared (cumulative) frozen histories once for every group at the cell.
- Blueprint line 2263 says "a shared history will not be counted once for every group", and line 2375 says "a third factor is shared or bounded by its group square sum".
- The number of main groups at a cell is only bounded by a power of `D_base`, not by `P^C`. So the old accounting could not give the `P^C |R|` budget.
- These three declarations are removed. Nothing else used them.

New route (Sec14_5b):
- `two_two_leafM` and `leaf_two_two_boundM` now take a cell value `C₃` that bounds the third factor of every group at the cell, instead of a per-group square cap.
- `strTh_le_SG`, `third_le_SG`: the third factor is at most a shared part (`thS`: `U` restorations, identity outputs, pads of cumulative steps, other complements with cumulative histories) plus a group-indexed part (`thG`: pads of ball steps, other complements with a ball).
- `Xo_indep`, `pYe_indep`, `dFe_indep`, `thS_indep`: the shared parts do not depend on the group. The merge order gives this: `mergeDescM_after` says later descriptors of a slot are cumulative.
- `band_split`: the complement bands of an offset are bounded by four times the pad and identity freeze energies.
- `unfl_of_noflag`, `unfl_ind_le`: flags split into block flags of the three energies.
- `flag_prop`: block-flag propagation costs `K / c`.
- `frz_varcap`: block-freeze differences cost `K` times a variation capacity.
- `C3v` is the shared part plus the root of the group square sum of the group part.
- `third_le_C3v`, `C3v_budget`, `C3v_budget_cap`: the integrated bound. The `U` energy is counted once per cell. The freeze budgets come from the shared variation capacities and the joint group variation capacities of the outputs.
- `leaf_two_two_capM`: the leaf two-side estimate with this budget.

Full lake build passed (9082 jobs); standard axioms.

## 2026-10-15T11:17:23-04:00

Row eq:side-windows (lines 2549-2560). File: TrilinearHT/Auto/Sec15_2bTorusSizeFourierTests.lean.

Statements:
- `three_core_averaged_of`: the generic three-core bound with the fresh side offset averaged (factor 2 of `offset_average_form`). The side cutoff and the gauge multiplier are truncated afresh at each offset, the core cutoffs once.
- `SideInput.three_core_test`: on a leaf cell of the side states, a three-core tuple with side role `l` passing the three-core test, and any side column `X` in slot `l`. The cell form is at most twice the sum of: the torus-form and gauge errors; the shells above `2^{I_w}`; the coset errors; and `Σ_{Λ = 2^i ≤ 2^{I_w}} C_{J,A} μ ν^{-J} Λ^{-(A+1)} W Π_{j≠l} (a'_j + τ_c Σ_{F_j}|α|) b_Λ` with `b_Λ² = E_ρ Σ_{k ∈ threeWin(Λ)} |Ŝ'_ρ(k)|²`.

Departures (constants and formulation only):
- Window box `|n|_∞ ≤ 16 B'_h` instead of `B'_h`. The coset references are expansion frequencies (multiplier, cutoff and shift indices summed), which reach `9 B'_h`. The counting section only uses `|n|_∞ ≤ C B'_h`.
- Decay `Λ^{-(A+1)}` for any fixed `A ≥ 1`, with constant `2^{A+4} C_{J,A}`, instead of `Λ^{-J}` (the Schur bound "with `A` increased").
- Sign convention: the normalized coefficients are `∫_I S'(y) e(k y/r) dy`, so the windows read `|k - r(Q + n·ξ)| ≤ 2Λ` (the blueprint's `|k + r(Q + n·ξ)|` is for `e(-k y/r)`).
- `S'_ρ = e(-c_l p_ρ) S_phys` without the factor `ζ^{ρ_l}`. The cutoff is carried by the truncated core product (its truncation has sup at most `1 + τ_c`); the expectation normalization is the factor 2. Since `|ζ| ≤ 1`, Parseval for each offset is unchanged (`window_energy_integrable`: `Σ_k |Ŝ'_ρ(k)|² ≤ r ∫_I |S_phys|²`).
- The core sizes enter as `a'_j + τ_c Σ_{F_j}|α|` and the multiplier as `W = (1 + τ_m)(1 + τ_c)` (no `|box|` or `√|N|` factor). The truncation parts are left for eq:core-numerical.
- `I_w` is free; the shells above `2^{I_w}` are bounded by the ordinary `L²` pairing (cell Bessel, `three_core_main_l2`): `2^{A+5} C_{J,A} μ ν^{-J} 2^{-(I_w+1)(A+1)} W Π (a'_j + τ_c Σ|α|) (r ∫_I |S_phys|²)^{1/2}`. The blueprint's cut at `U_0` is the choice `2^{I_w} ≈ U_0`.
- Far cosets: `H = T/L_{h-Δ} - U_0 ≥ 4` from `L_{h'}(U_0 + 4) ≤ T` (`Tt_ge_U0_four`).
- The tiny/huge gap may come from a good component of any role `j₀` in the common chart (`three_cosets` generalized from role 0). With side role `l = 0` the gap is that of a successful core component, as in the blueprint ("a successful component contains a nonexceptional primary").

Other changes: the duplicate `card_windowSet_le` in Sec15_4 (identical statement) is removed. Six Lean files had been rewritten with CRLF line endings by a scripted edit; they are restored to LF (no content change).

Full lake build passed; standard axioms.

## 2026-10-15T12:42:49-04:00

Row eq:core-numerical (lines 2562-2567). File: TrilinearHT/Auto/Sec15_2bTorusSizeFourierTests.lean (gaugeErr in Sec15_1).

Statements:
- `SideInput.four_core_tuple_bound`: a four-core tuple on a leaf cell of the side states. The cell form is at most `|Ŵ_s(r q', r t')| Π_j a'_j` if the tuple passes the four-core test (`0` if it is discarded), plus `fourErrC κ J · D_*^{-100} Π_j Σ_{F_j} |α|`.
- `SideInput.three_core_tuple_bound`: a three-core tuple with side role `l`. The cell form is at most `threePrin` (the principal window sum with the true torus sizes) if the tuple passes, `0` if it is discarded, plus `threeErrC κ J A · D_*^{-100} Π_{j ≠ l} Σ_{F_j} |α| · σ` with the local side size `σ = (r⁻¹ ∫_I |S_phys|²)^{1/2}`.
- `SideInput.pattern_error_first_success`: the first-success weighted sum of tuple errors over trial counts, assignments, words and final heights equals the plain sum over the component tuples (weight one), which is at most `C Π_{core l} Σ_K Σ_{m ∈ K} |α_m| Π_{other l} s_l`.
- `core_numerical_integrated`: the integrated bound `m C e^{-k} |R|`.

Formulation and departures:
- The gauge multiplier is taken with the enlarged cutoff `δ/2`, where the gauge identity is exact (`gauge_factors_eq_mult_exact`, entry 2026-10-14T16:53:10). `gauge_torus_approx_of` and the three/four-core chain now carry `gaugeErr d δ δ''`, which is `0` at `δ'' = δ/2`; the earlier thin-layer error `8 d δ'' R_δ` is not small at that choice.
- The budgets of line 1944 (truncation tails at most `D_*^{-300}`, full Fourier norms of the multiplier and the cutoffs at most `D_*`) are hypotheses of the tuple bounds, as in the earlier rows.
- Discarded four-core tuples without reference: every expansion frequency `(P₁, P₂)` lies in the full box `B'_{h-Δ} = D_*^5 E_{h-Δ}` (shifts at most `D_* E`, cutoff and multiplier indices at most `E`; `(10 + 6 D_*) E ≤ D_*^5 E` for `D_* ≥ 2`, `expP_fullBox`). Hence `ν ≥ U₀` for all of them and `|Ŵ_s| ≤ C₁ U₀⁻¹`.
- Discarded three-core tuples without reference: every anchored frequency `T_l + (P₂ - l P₁)·ξ` has `|r ·| > U₀`, again by the full box. In positive chart dimension the averaged bound is applied with no near coset. In dimension zero there is a single constant coset; the reference value is chosen so that `|r β₀| ≥ U₀` in both cases (`three_core_noref_of`). In this case the core torus sizes are bounded crudely by `(1 + τ_c) Σ|α|` on the full torus, which is enough for an error term.
- Constants: `fourErrC κ J = 104 ‖w‖ + 31 C₀ + 2 C₁ + C_near + C_J`, `threeErrC κ J A = 208 ‖w‖ + 2^{A+12} C_{J,A} + 2 C_near' + 96 C_J`. Here `J ≥ 1` (four cores) and `J ≥ 3` (three cores; the far tails `(4/H)^{J-2}` need `J - 2 ≥ 1`). The window range of the three-core principal quantity satisfies `2^{I_w+1} ≥ U₀` ("shells above `U₀` are negligible").
- The integrated sum: "the path multiplicities, coefficient sums, and retained size caps make their integrated sum `O(e^{-k}|R|)`" is formalized with these quantities as fixed powers of `D_*` (coefficient sums `≤ D_*^a`, side sizes `≤ D_*^b`, length-weighted group multiplicity `≤ D_*^c |R|`, `4a + b + c ≤ 99`) and `D_* ≥ e^k`. The blueprint leaves this exponent accounting implicit (line 1934: `D_*` covers coefficient sums on normalized cells and the counts along paths; retained sizes are `P^C` with `P ≤ e^k ≤ D_*`).
- Generalizations: `four_core_test` and `three_core_test` now need only a reference (the threshold part of the test is used only to decide principal versus discarded).

Full lake build passed; standard axioms.

## 2026-10-15T12:58:11-04:00

Row lines 2569-2577 (moments of the core torus sizes over the failure histories). File: TrilinearHT/Auto/Sec15_2bTorusSizeFourierTests.lean.

Statements:
- `SideInput.role_size_moments`: fix a final upper height `h`, a good mode `m` of a core role `j` (final class `F = F_h(m)`) and an assignment `asg` of the `n` failed trials. Take torus forms of the selected modes `maskSel` for all words `w ∈ H^n`. Then `a'_j(w) ≤ 6 σ_F` and `E_w a'_j(w)² ≤ 36 (2δ_*)^{n_j} σ_F²`, where `σ_F² = compSizeSq` (`eq:component-size`).
- `SideInput.masked_sizes_moment` (Hölder): `E_w Π_{core j} a'_j ≤ 36⁴ ((2δ_*)^n)^{1/4} Π_{core j} σ_{F_j}`.
- `SideInput.masked_sizes_moment_exists`: the same with the torus forms provided by `maskSel_torus_form`.
- `assignment_moments_hasSum`: the sum over the `4^n` assignments and all `n` converges when `4 (2δ_*)^{1/4} < 1`.
- `SideInput.masked_tuples_empty`: a failure assigned to a non-core role leaves no masked tuples.

Formulation and departures:
- Constants: `C = 6` in the deterministic bound and `C = 36` in the second moment (from the factor `6` of `eq:torus-size`).
- The probability bound is applied to each minimal CURRENT component `U ⊆ F` (the summands of `eq:torus-size`). `U` counts as good at a height when all core components of the cell inside `U` are good there. On the upper heights these share their good predicates, so `U` is bad at a proportion at most `2δ_*` (`unitGood_bad_card`). A summand of a word needs its unit to fail at the `n_j` heights assigned to `j`; the other success requirements are dropped (`selComps_sum_le_filter`, `mask_second_moment`).
- Hölder is taken over the four slots with `m₀ = 4` factors also for three-core patterns; the side slot contributes the factor `1`. The exponent is therefore `n/4` rather than `n/m₀ = n/3` in the three-core case. This is a weaker bound that is still summable; it is used with the smallness condition `4 (2δ_*)^{1/4} < 1` on the "chosen small absolute δ_*" (line 1946). Assignments `Fin n → Fin 4` range over all four slots; those assigning a failure to a non-core slot have empty masks (`masked_tuples_empty`).
- The shifts of the torus forms are arbitrary functions of the word satisfying `eq:core-torus-form` (`TorusFormAt`). Their existence for every word is `maskSel_torus_form`, from `core_torus_form`.

Full lake build passed; standard axioms.

## 2026-10-15T13:36:31-04:00

Row eq:principal-core (lines 2577-2582). File: TrilinearHT/Auto/Sec15_2bTorusSizeFourierTests.lean.

Statements:
- `SideInput.four_core_principal_bins` (four cores, `Λ = 1`): `‖Λ_I(pattern)‖ ≤ 2⁴/(1 - 4(2δ_*)^{1/4}) Σ_{h∈H} |H|⁻¹ Σ_{bins} C_J 2μ ν^{-J} Π_j 6(2σ_j) N_{h,bin}` plus `Σ_r C_J D_*^{-100} Π_l Σ_{m ∈ r_l} |α_m|`.
- `SideInput.three_core_principal_bins` (side role `l`): the same with the bins `(μ, ν, Λ = 2^i, b_Λ, σ_j)`, the values `2 C_{J,A} 2^{A+4} (2μ) ν^{-J} Λ^{-(A+1)} (2b_Λ) Π_{j≠l} 6(2σ_j)` and the side size as an extra error factor.
- Intermediate results: `four_core_principal` and `three_core_principal` (before binning), `four_core_binned` and `three_core_binned`, `anchor_injective`.

Formulation and departures:
- Anchors. The representatives `a_j` of the final classes are a parameter `anc h j F` with the property `AnchorOK`: every mode of a core component good at `h` lies in `E_{h-Δ}` of the anchor of its class. The hereditary representatives of lines 2172-2183 satisfy it (`selected_in_pred_of_rep`). The tests and frequencies use these anchors; `anchor_injective` shows each tuple of anchors is counted at most once.
- `N_{h,bin}` counts tuples `p` of final classes of good core components at the final height `h`: those that pass the test, have nonzero sizes (and, for three cores, nonzero window size at the shell), and lie in the bin. The bins are the dyadic bands of `eq:four-tests` and of the sizes. Zero factors contribute nothing (they are excluded from the count).
- The power of `Λ` in the three-core values is `Λ^{-(A+1)}` with the Schur exponent `A ≥ 1` of `eq:side-windows`. The blueprint's `Λ^{-J}` is the case `A = J - 1`.
- Constants: `2⁴/(1 - 4(2δ_*)^{1/4})` comes from Hölder over four roles and the assignment series. It requires `4(2δ_*)^{1/4} < 1` (the chosen small absolute `δ_*`). The factors `6` in `6σ_j` come from `eq:torus-size`. The factors `2` come from the dyadic bands.
- Assignments of a failed trial to the side slot leave no masked tuples, so they contribute nothing (proof of `three_core_principal`).

Full lake build passed; standard axioms.

## 2026-10-15T14:18:57-04:00

Row lines 2709-2717 (counting setup and pair determination on the side states). File: TrilinearHT/Auto/Sec15_4VerificationCountingHypotheses.lean.

Formulation and departures:
- "Representatives": the mode nodes are the successful final classes of the cells (one chosen good mode per class and pre-cell). Their hereditary representatives come from `typed_representatives_sched` for each type class; the counting uses these representatives as the anchors of eq:principal-core (`repAnc`, `AnchorOKAt`).
- "Identify a representative with its fixed real value": the label of a class is the slope `ω_a(x*)` of its representative. Distinct classes of one type at one cell have distinct labels (`repAnchor_slope_inj`). Across cells, distinct labels of one type are separated by `(Ξ/2) max(R_s, R_t)` against shifts `N·ζ`, `|N| ≤ Q` (`path_label_sep'`).
- Separation vector and reserves: `ζ = 6^{Δ-2} ϑ/L_h` with `36 ζ = ξ = ϑ/L_{h-Δ}` (`torusξ_eq_zeta`; good classes have `h ≥ Δ = 10`). The shift reserve is `Q = E_h/6^8 ≥ 288 D_*^5 E_{h-Δ}` (`Valid.shift_reserve`, from `A₀ ≥ 6^{30} D_*`) and the band reserve is `8 · 2ν ≤ 16 U₀ ≤ Ξ/2`. These replace the blueprint's "the shift reserves include those fixed denominators" and "ν ≤ C U₀ ≪ Ξ" by explicit inequalities.
- Pair determination is stated for tested tuples with reference data in common bands `μ, 2ν` (the dyadic bins of eq:principal-core), at two cells containing the path point.
- `M_l^G ≥ 1`: a nonzero side use in the side bin `σ_l = band(b_Λ) ≤ b_Λ` has `σ_l² ≤ r⁻¹ ∫_I |S|²` (`side_bin_le`, Bessel via `window_root_le`).

Full lake build passed; standard axioms.

## 2026-10-15T14:26:56-04:00

Row eq:triple-test (lines 2718-2724). File: TrilinearHT/Auto/Sec15_4VerificationCountingHypotheses.lean.

Formulation and departures:
- The constants of eq:triple-test are explicit: `c = 1`, `C = 8` (four cores: `|t' - l'q'| ≤ 4 · 2ν R_s` with the band `2ν ≥ ν`) and the witness box `|n| ≤ 4 B'_{h-Δ}`; for three cores the test is the `T_l` test with `2ν` and `B'_{h-Δ}`.
- "`L₀ ≤ P^C (1 + log(ν/μ))^C` ... absorbed in `P^C` for the chosen `P`" is formalized as `L₀ ≤ K (1 + log(8ν/μ))` with the explicit factor `K = 32 (d_max + 5)^4 (log(288 D_*^5 H) + log 2 + 1)`, polynomial in the dimension and the logarithmic heights `log D_*`, `log H` (`mult_le_sched`). The parameter `P` is fixed only in the attempt (line 1668). Bounding `K ≤ P^C` uses `log D_* ≤ P^C` (line 1934) and `log H ≤ M Λ^{12}` (`chooseSchedule`, line 1976); this step is carried out at eq:core-final, where `P` is available.

Full lake build passed; standard axioms.

## 2026-10-15T14:46:52-04:00

Row eq:total-count (lines 2726-2729), side states. File: TrilinearHT/Auto/Sec15_4VerificationCountingHypotheses.lean.

Formulation and departures:
- The counts are stated along a path (scales `S`, cells `cellOf s` with `(cellOf s).1 = s`, path point `x*`) for one group, height, role types and bin. The anchors along the path are hypothesised to be the hereditary representatives (`FourPathAnc`, `ThreePathAnc`); these are the anchors `repAnc` built in row 2709-2717. `M_i^G = |A_i^G|` is the number of distinct labels of role `i` along the path.
- `L₀` is the explicit multiplicity bound `fourMult` / `threeMult` of `lem:height` at the bands of the bin; row eq:triple-test bounds it by the schedule (`mult_le_sched`).
- Side incidence: the blueprint says "the windows defining `b_Λ` for different incident triples are disjoint" and "`ν, Λ ≤ C U₀ ≪ Ξ`". The windows use the box `16 B'_{h-Δ}`, so the shift reserve used is `1152 · 16 · 6^8 D_*^5 E_{h-Δ} ≤ E_h` (`Valid.window_reserve`, from `A₀ ≥ 6^{30} D_*`). The shells are required to satisfy `2^{I_w} ≤ 2 U₀` (hypothesis `hIw`), which is the blueprint's `Λ ≤ C U₀`; the band reserve is `16 U₀ + 96 U₀ ≤ 128 U₀ ≤ Ξ/2`. The downstream choice of `I_w` (least with `2^{I_w} ≥ U₀/2`) satisfies `hIw`.
- `w_s = σ_l^{-2} ‖S_{l,G,s}‖²_{2,I_s}` with `‖S‖²_{2,I} = r⁻¹ ∫_I |S_phys|²` (`sideWeight`); Bessel is applied for each offset (`window_energy_integrable`) and averaged (`side_incidence_le`). The bound holds on every subset of scales because it is per scale.
- `N_s` is the number of label tuples in `E_s`; `fourPathE_card` / `threePathE_card` show it equals the number of tested tuples (and shells) in the bin, by injectivity of representative labels (`repAnchor_slope_inj`).
- The representative-anchor hypothesis `hrep` is required for all four roles; in three-core statements the side role's representatives are not used.

Full lake build passed; standard axioms.

## 2026-10-15T14:59:05-04:00

Row eq:applied-sparse (lines 2731-2742), side states. Files: TrilinearHT/Auto/Sec15_3FiniteSparseCountLemma.lean (refactor), TrilinearHT/Auto/Sec15_4VerificationCountingHypotheses.lean.

Formulation and departures:
- `sparse_count` had existential constants. Its proof already used `C = 3 · 10^{11}` and `C_res = 7200000`; these are now exposed as `sparse_count_explicit`, and `sparse_count` is derived from it with an unchanged statement. The reserve `Q ≥ C_res (d+1)² C B'_h` can only be checked against an explicit `C_res`. The older `sparseC4/sparseCres4` (Classical.choose) are not used by the side-state application.
- Reserves: `Q = E_h/6^8` (the blueprint's `⌊E_h/6^{Δ-2}⌋`; the floor is not needed because the lemma only uses `|n| ≤ Q`), `B = D_*^5 E_{h-Δ}` with the factor 4 of the four-core annuli, `Σ = Ξ/2`. `Valid.sparse_reserve` uses `A₀ ≥ C_* 6^{R_*} B_* D_*` and `d_max ≤ C_*`.
- New budget condition `d_max ≤ D_*` (hypothesis `hdD`) for the `Σ` reserve `7200000 (d+1)² · 8U₀ ≤ Ξ/2`. The blueprint asserts that `Ξ = D_*^{1000}` and `ν ≤ C D_*^{250}` give the reserve `Σ ≥ C_res (d+1)² ν`, which needs `(d+1)² ≲ D_*^{750}`. It takes `d_max ≤ k^{O(1)}`, `D_* ≥ e^k`, and "the finite number of dimensions is already in those budgets" (line 2567). The condition must be discharged where `D_*` is chosen (enlarging `D_*` to `max(D_*, d_max)` keeps `log D_* ≤ P^C`).
- Pure-shift gap: "any successful component contains a nonexceptional primary": a nonempty `E_s` has a tested tuple whose core class contains a mode good at `h` on the cell (`mem_goodCls`). Its `frequency_dichotomy` (`eq:gap` at height `H`, thresholds `T⁻¹/r_{v_b}`, `T/r_{t_b}`) applies to integer `|n|_∞ ≤ E_h/6^8 < H` (`Valid.box_lt_H`) and excludes `[μR/1000, 1000νR]` for `μ > U₀⁻¹/2` and `ν ≤ 8U₀`, using `T ≥ L_h(U₀+4)` (`Tt_ge_U0_four`).
- "Absorb the absolute constants in eq:triple-test into μ, ν": the four-core application uses the bands `μ` and `4 · 2ν` (`four_core_ann`), so `ℓ = 1 + log₂(2 + (d+1)² · 8ν/μ)`; the three-core one uses `μ, 2ν`.
- `M` is any common upper bound of the counts `M_i^G = |A_i|` (and of `M_l^G = Σ_s w_s` for three cores). `M = M'` is the blueprint case, and `M ≥ 1` follows from a nonempty `E_s`. For empty paths the bound is trivial, given a genuine bin (`0 < μ`, `0 ≤ ν`; hypothesis `hc`).
- The three-core application keeps the shell condition `2^{I_w} ≤ 2U₀` from `eq:total-count`; `L = L₀ = fourMult / threeMult`.

Full lake build passed; standard axioms.

## 2026-10-15T15:16:30-04:00

Row lines 2772-2774 (negligible amplitudes), side states. File: TrilinearHT/Auto/Sec15_5OneDistributionCalculationFinalSums.lean.

Formulation and departures:
- "Retained amplitudes satisfy `σ_j ≤ P^{C₀}`" is a hypothesis `σ_j ≤ U` on the class sizes, and for three cores also on the side sizes `(r⁻¹ ∫_I |S|²)^{1/2}`. It is discharged later from the retained sizes (`compSize_le`, `winB_le_sideSize`, and the core and side caps of `core_reduction_leaf`).
- The length-weighted incidence count is left as `D_*^4 · Σ_I |I| |G_I|` (or `D_*^3 (I_w+1) Σ_I |I| |G_I|` for three cores, counting shells as frequency choices). The heights enter through the average `|H|⁻¹ Σ_h` of `eq:principal-core`, so no height count is needed.
- `μ ν^{-J} Λ^{-(A+1)} ≤ 1` is used through `μ ≤ 1 ≤ ν` (`fourBands_spec`, `threeBands_spec`) and `Λ = 2^i ≥ 1`.
- "Choose the fixed integer `B > C₁ + 3C₀ + 2`; this is `O(e^{-k}|R|)`" is `negligible_exp_small` with `B ≥ C₁ + 3C₀ + 1` and `D_* ≥ e^k`. "Leaves the minimum by eq:min-subadd" is applied in eq:core-final.
- Amplitude quadruples: four cores use `(σ_j)_j`; three cores use `threeAmp = (b_Λ in the side role, σ_j in the core roles)`. All are dyadic (`2^k`), and those in `[ε, U]` number at most `(log₂(U/ε)+1)^4`.

Full lake build passed; standard axioms.

## 2026-10-15T15:34:37-04:00

Row lines 2783-2800 (powered group sums), side states. File: TrilinearHT/Auto/Sec15_5OneDistributionCalculationFinalSums.lean.

Formulation and departures:
- The group sum is stated at one path point, height, type tuple and bin. `M'` is replaced by `Σ_k M_k^G` (allowed by `path_count_four`, which "expands `M'` into its four possible maximizing roles"). Groups with empty paths contribute zero and are omitted ("omit zero-count groups").
- `L₀` and `ℓ` depend on the chart dimension of the group. They are bounded uniformly at `d_max` (monotonicity), so one constant serves all groups.
- Path caps: eq:top-count enters as the hypothesis `Σ_G |A_j^G| ≤ K σ_j^{-2}` for the distinct used representatives `A_j^G` (`fourUsedReps`, `threeUsedReps`), and the side cap as `Σ_G Σ_s ‖S_{l,G,s}‖²_{2,I_s} ≤ K` (`sideWeight_cap`).
- These sets are contained in the count sets of `first_top_count_main` (prop:tops): `A_j^G ⊆ {R.rep(node) : (I, node) ∈ useInst, x* ∈ I, σ_j² ≤ nodeSize}`. This holds once the representatives of type `κ_j` are those of `R`, the class nodes of that type lie in `R.Nd`, the path cells are actual-use cells, and the coefficients of the side states are those of the tops statement. These identifications belong to the construction of one attempt (sec:completion, line 2839).
- "The finite amplitude-bin count absorbs all their sums, including the 24 orderings": the ordering is internal to `path_count_four_sorted`; the sum over amplitude bins is carried out in eq:core-final with the count of `four_retained_amps_card` / `three_retained_amps_card`.

Full lake build passed; standard axioms.

## 2026-10-15T16:14:34-04:00

Row eq:core-final (lines 2808-2817), side states. File: TrilinearHT/Auto/Sec15_5OneDistributionCalculationFinalSums.lean.

Formulation and departures:
- Stated separately for the four-core pattern and for each three-core pattern with side role `l`. `core_final_patterns` (subadditivity of `min(η,·)`) adds them, which covers the core quantity of the patterns with at least three cores.
- Inputs that are conclusions of earlier rows enter as hypotheses:
  - the principal bounds of eq:principal-core (`hP`, in the form of `four_core_principal_bins` / `three_core_principal_bins`, with the anchors equal to the representatives);
  - the path caps of eq:top-count and the side cap along every retained path (`hcap`);
  - the retained amplitude bound `σ ≤ U` and `≤ D_*` alive modes.
- eq:top-count is required at every point `y` for the cells of the path of `y` that lie in `T`. This is the blueprint's "for every retained path". Note: `first_top_count_main` states its bound only at points outside its cuts, for all depths. The retained-path form (cells above the first crossing) follows from the first-crossing construction but is not literally its conclusion. This must be reconciled in the assembly; possibly first_top_count_main needs a retained-path version.
- `M_p` is an explicit product of polynomial factors (`multPoly`, `ellPoly`, `|H|`, the role-type count `(log₂ D_*+1)^8`, `(log₂(U/ε)+1)^4`, the shell count `I_w+1`, `K`, constants). Its conversion to `C_q P^{C₄}`, and of the separated errors to `O(e^{-k}|R|)` (`negligible_exp_small`, the `D_*^{-100}` numerical errors), is part of the exported core estimate (lines 2820-2822).
- Three-core shells are counted, giving the factor `I_w+1`, instead of summed with the factor `Λ^{-Jp}`. This is a weaker, still polynomial, bound. The heights enter through `|H| ≥ |H|^{1-p}`.
- The group-sum lemmas `four_group_sum_side` / `three_group_sum_side` now take per-group scale sets `S G` (the depths at which the group is used along the path).

Full lake build passed; standard axioms.

## 2026-10-15T17:42:28-04:00

Row line 2836 (depth bookkeeping). Files: TrilinearHT/Auto/Sec14_2bShortBlockSummation.lean, Sec14_4FixedStacksTwoVaryingSides.lean, Sec14_5CommonCutsHullMaximaSummation.lean, Sec14_5bExportedSideEstimate.lean, Sec15_1ExactCommonHeightSelection.lean.

Correction to lem:shortblock (statement fidelity):
- Before this change, short_block_comparison obtained C_N from the hypothesis K ≤ N. The blueprint's hypothesis is instead that the internal summation cells lie in at most K consecutive depths of the original N-depth range. Under that hypothesis K may exceed N, so the old form was a strengthened hypothesis.
- The lemma now takes a depth window: the summation cells lie in [d₀, d₀ + N). This is the only input `main_bound` uses.
- short_block_comparison_nz requires the window only for cells of nonzero kernel, since zero-kernel cells contribute nothing.
- piece_random_bound, piece_select_bound, piece_band_bound and sparse_piece_bound take the window (d₀ and nonzero-kernel cells in [d₀, d₀ + N)) in place of K ≤ N.
- near_band_bound takes a window for each sparse piece.

Line 2836 itself:
- The side-state chain now takes `A.DepthWin N` in place of K ≤ N. It runs from leaf_near_bandM and the near-band cut, stack, position, actual and critical lemmas, through the T-level side lemmas, side_estimate_leaf and core_reduction_leaf.
- `A.DepthWin N` says that the cells of the setup with nonzero weight lie in N consecutive depths. This is exactly the depth hypothesis of RetainedMin, `∀ I ∈ B.cells, B.w I ≠ 0 → d₀ ≤ I.1 ∧ I.1 < d₀ + N`.
- Consequently every C_N(q) in the side-state estimates is the constant of the original N depths, as in the blueprint.

Legacy AttemptParams system:
- leaf_near_band and Sec16_1 still assume K ≤ N, now justified per piece by the piece root's depth.
- They keep their C_K conclusions. They are not on the fp side-state route.

Full lake build passed; standard axioms (short_block_comparison, short_block_comparison_nz, near_band_bound, leaf_near_bandM, near_band_criticalM, near_band_critical_UM).

## 2026-10-15T18:37:37-04:00

Rows of line 2839 (one attempt on the fp system): basic input sizes, catalogs on test cells, certified groups. Files: Sec11_2cFiniteBaseDataAssembly.lean, Sec12_3bCatalogsMainColumns.lean, Sec12_4BinaryLocalizationVariation.lean, Sec13_4SideStatesFixedOffsets.lean, Sec14_1TransferPairedDefects.lean, Sec14_5bExportedSideEstimate.lean, Sec16_1OneAttemptRestarts.lean, Sec16_3SummingUpdateLevels.lean.

prop:base statement fidelity (basic projection inputs normalized on every cell):
- `HasColumnRep CF` and `ColumnRepBelow R' CF` now also assert that the inputs of the two basic projections have energy at most `CF |I|` on every cell `I` of the setup (`BasicProjection.CellEnergyOn`). Previously only the root energy was recorded.
- This is the blueprint's "their normalized L² sizes are bounded": the original inputs are normalized on every cell of the tree.
- The data was already available (`IsBasicOn` carries energies on all kernel-hull cells; the setup cells lie in the hull, `hTH`). `IsBasicOn.basicProjection` now exports it, and both base constructions pass it on.
- `BasicFamilies` has a new field `energy`. `BasicFamilies.normF` is the `hnormF` input of `core_reduction_leaf` with `C_F = 1`.

Catalogs on the active cells (lem:closure: "these main tests terminate on every active cell"):
- `main_closure`, `helper_closure`, `attempt_localization`, `helper_instantiation_main` and `helper_sides` now take a test-cell set `Tc ⊆ A.cells`. Previously the tests were imposed on all of `A.cells`.
- With `Tc` the active cells, the path-multiplicity hypothesis of the label counts holds at every cell.
- `A.cells` itself stays ancestor-closed, as the hulls of the side estimate need.
- Equivalent organization; no change of mathematical content.

Pattern inputs:
- `uslot p` is the marked slot of a side pattern.
- `patIn` gives the U column in that slot and the basic inputs elsewhere.
- `Λc_patIn`: the cell form of the pattern inputs is `A.Hf I (A.z p I)`.
- `norm_patIn_le`: normalized size at most `max 2 S`.

Certified groups:
- `groupsAt_cert_use` (port of the ap `groupsAt_cert`): at a cell where every present vertex succeeds, each current group has `Cert` and `ActualUse`.
- `FamParams.failure_cut` gives success below no failure root.

Full lake build passed; standard axioms.

## 2026-10-15T18:50:45-04:00

Discrepancy found while assembling line 2839 (fixed in the combination layer, in progress): the clearing integer Q₀ of sec:core.

Blueprint:
- Line 1890: "For group center z, choose an integer Q₀ in the main budget clearing C_z, and put ϑ = θ_z/Q₀".
- Q₀ is per group center.
- Lines 1934 and 1958 only need D_* ≥ Q₀ and Q₀ inside the bound H > (d_max C_* E_{J_*} B_* L_{J_*} Q₀ Ξ)^{10} of eq:mode-parameters.

Lean before the fix:
- The sec:core development reads the clearing integer from the leaf schedule `D.S.Q0`: torus frequencies `torusξ D.S`, `xiH`, the tests `fourRefSet`/`fourPasses`, and the hypotheses `hQC : Q₀·C_z integral`.
- One schedule serves all groups of a leaf. Its Q₀ would have to clear the curvature matrices of all group centers.
- A common multiple of the clearing integers of all centers has logarithm of the order of the number of distinct centers. That number is not bounded independently of the tree. So it is outside the main budget, and K ≤ C P^{C₅} (eq:mode-parameters through log Q₀) would fail.

Fix:
- Per-group schedules: `SideInput.withQ0 q` replaces only the clearing integer of the schedule.
- `ModeSchedule.Valid` persists for 1 ≤ q ≤ S.Q₀, since Q₀ enters only as a factor of the H bound.
- Every other component of the side input (blocks, side states, cores, errors, modes) is unchanged, definitionally.
- The per-group sec:core results (torus forms, tests, principal bins, counts) are applied to `D.withQ0 (q G)` with `q G` the clearing integer of the center of G.
- The cross-group combination lemmas of Sec15_5 (path totals, eq:core-final) are generalized to a per-group clearing integer.
- The leaf schedule keeps Q₀ := a common upper bound (≤ D_*), as in eq:mode-parameters.
- The per-group statements of sec:core are unchanged; they were already stated for one group.

## 2026-10-15T20:14:15-04:00

Resolution of the Q₀ discrepancy of 2026-10-15T18:50:45-04:00 (per-group clearing integer, blueprint line 1890). Fixed.

- Placement: `ModeSchedule.withQ0`, `ModeSchedule.Valid.withQ0` and their simp lemmas are in Sec13_3. `SideInput.withQ0` and its simp lemmas are in Sec14_5b.
- Generic cross-group lemmas take `(q : ι → ℕ) (hq : ∀ G, 1 ≤ q G ∧ q G ≤ S.Q0)` and use `S.withQ0 (q G)` per group:
  - `linear_side_of_events`, `side_errors_negligible` and `linear_energy` (Sec13_3);
  - `sideState_budget` (Sec13_4);
  - `tops_energy`, `first_top_count`, `first_top_count_main` and `usedReps_le_Dstar` (Sec13_5).
- Side-input lemmas take `(qG : bf.Grp → ℕ)`.
  - They work on the family leaf `D.toLeafQ qG`, whose group-`G` side values, sides and blocks are those of `D.withQ0 (qG G)`.
  - Lemmas: `V_sum_le`, `basic_side_energy`, `block_energy`, `U_side_energy`, `toLeaf_cap`, `side_estimate`, `Tside` and `side_estimate_leaf` (Sec14_5b); `cell_reduction`, `core_reduction` and `core_reduction_leaf` (Sec15_1), through the wrappers `form_expandQ`, `restored_eqQ` and `sizes_atQ`.
- The Sec15_5 path totals and eq:core-final take `(qG) (hqG)`.
- No statement gained an assumption beyond the family `qG` and its bounds `1 ≤ qG G ≤ Q₀`. Lemmas that do not need those bounds hold for every `qG`.

Full lake build passed (9083 jobs). Standard axioms: a global audit of all 13915 `Auto` declarations found only propext, Classical.choice and Quot.sound.

## 2026-10-15T21:11:13-04:00

Gap found while assembling line 2839 (linear sides and first top counts), fixed: the enlarged budget `D_*` did not cover the heights used by the representatives.

Blueprint:
- Line 1934: `D_*` covers "all mode counts, rational heights in eq:mode-differences, inverse private weights, Q₀, ...".

Lean before the fix:
- `typed_representatives_sched`, `first_top_count_main` and their callers take `hBσ : 2 (Q₀ (3 B_σ²)²)² ≤ ⌊D_*⌋`. This bounds the heights of the rescaled differences of key differences.
- `modeStarG` (the enlarged `D_*`) covered `B_σ` itself, but not this polynomial in `B_σ` and `Q₀`. So `hBσ` could not be discharged at `D_* = modeStarG`.

Fix (Sec13_1):
- `keyHgt` is the largest key height `max(1, B_m (1 + 4(2d_B+1) max(1, 4B_m/δ_c)))`, with `B_m = exp(D X_max^D)`.
- `hgtStar = 2((H_ed^(d_B²)+1)(3 keyHgt⁴))² + 1`.
- `modeStarG` now adds `hgtStar`, before `K_*` is chosen. The tails stay `≤ D_*^(-300)` for the final `D_*`.
- `le_modeStarG` exports `hgtStar ≤ D_*`.
- The degree bound `log_modeStarG_poly` keeps its form, via `hgtStar ≤ 19 (modeStar+1)^10` (`keyHgt_le_modeStar`); only its constant changes.
- `exists_mainModeSystem` exports `B_σ` and the reindexing of the primaries. `FamParams.ModeExports.hBσ_le` derives `hBσ` for every clearing integer `Q ≤ H_ed^(d_B²)+1`.

This is the blueprint's choice of `D_*` covering the heights: a polynomial enlargement, so `log D_* ≤ P^C` is unchanged.

Full lake build passed (9083 jobs). Global audit: standard axioms only.

## 2026-10-15T21:31:13-04:00

Gap found while assembling line 2839 (first top counts for the core), fixed: `eq:top-count` along retained paths.

Blueprint:
- Lines 2226-2229: first crossings of the partial top counts give `Σ_tops 1_I(y) ≤ P^C σ^-2` "outside a small root fraction".
- Line 2808 (`eq:core-final`): the path caps are used along every retained path.

Lean before the fix:
- `tops_cut_many` and `first_top_count(_main)` bounded the count only at points `y` outside the cut cells.
- `four/three_core_final_side` take the caps `hcap` for every `y`, summed over the retained cells `T` containing `y`.
- A retained cell above a cut contains points of the cut. Its count at such points was not controlled; and a retained cell can be covered entirely by cut cells.

Fix (Sec13_5, Sec15_5):
- `tops_cut_many` now states, for every point, the count of the tops on cells not inside any cut cell. These cells are retained cells of every choice (`dyadicRetainedCells_iff`).
- `card_reps_le_firstTops_of` is `card_reps_le_firstTops` restricted to an upward closed family of cells (`[DecidablePred P]`, so the filter instances agree).
- `first_top_count` and `first_top_count_main` now bound, for every `y`, the representatives used at instances on cells not inside any cut cell. This implies the old form.
- `four/three_usedReps_subset_tops` now record that the instance cell lies in the path family `Cs`. With `Cs` the retained cells, the core caps follow for every `y`.

Full lake build passed (9083 jobs). Global audit: standard axioms only.

## 2026-10-15T22:05:06-04:00

Proof-route changes for the helper catalogs of line 2839 (blueprint lines 2167-2169: "helper ranks exceed every main rank, so their insertion leaves all previously fixed main projections, offsets and side states unchanged").

1. Invariance only on active cells (Sec16_1).
- The global main outputs `basicOut` live on the relevant labels of the catalog (`RLab s`). Their global invariance under appended templates would need a transport of the depth families between label types.
- What is proved instead is the restricted form:
  - `basicOut_restrict_append`: on an active cell of its depth (`basicOut_restrict` with the unchanged ball and cumulative filters).
  - `frozenZ_restrict_append`: through the active ancestor at the frozen depth.
  - `sideState_restrict_append`.
- The side input of the leaf uses the extended catalogs: `SideInput.appendCat`, with a main budget of the extension.
- Every object that enters the leaf estimates through the main catalog is a restriction to an active cell. The transfer lemmas are `toLeafQ_sv_appendCat`, `toLeafQ_out_appendCat`, `repAt_appendCat` and `errAt_appendCat`.

2. Helper bases indexed by the groups of the leaf.
- `far_bound`, `side_estimate_leaf` and `core_reduction_leaf` took helper tests with base index `Fin 4 × bf.Grp`, an infinite type. The closure (lem:closure) needs finitely many tests.
- Only the side of the tested slot is used as a base, at an actual-use group of the cell.
- The base index is now `gset` (the groups of the leaf), with base `G ↦ T.sv a G I` for the test slot `a`. `far_bound` takes `gset` and `hgs : gs I ⊆ gset`.

3. `helper_sides` now requires only what it uses of its bases: their restrictions to the active cells avoid the fresh labels of the slot catalog.
- Side states are physical (`sideState_restrict_base`).
- The whole output of a basic `U` slot is a ball filter output of its own catalog (`ballFilt_fresh`, `restrict_ballFilt_self`).
- `helper_instantiation_main` and `helper_sides` also export the births, rank `L + 5`, mask tags and template form of the inserted templates.
- Tags are available occurrences (`maskOf_mem_X`, `occAvail_of_mem_X`), which gives `BallData` for the extended leaf (`ballDataAppend`, with `mainLabelsM_append_highRank`).

Full lake build passed (9083 jobs). Global audit (13999 Auto declarations): standard axioms only.

## 2026-10-15T22:42:24-04:00

Interface defect found while assembling the core estimate of line 2844 (eq:core-final on a leaf); fix in progress.

The defect:
- `four_core_final_side`, `four_path_total`, `four_path_bin_bound` (and the three-core analogs) take the anchors of the final classes as total functions `anc : ∀ (I : ℤ × ℤ) (G : bf.Grp), ℕ → ∀ j, Finset (Ms j G).Md → (Ms j G).alive U_I`.
- The path layer (`four_group_sum_side`, `fourPathE`, `fourUsedReps`, `FourPathAnc` and the three-core analogs) takes `ancOf : ∀ s, … → alive U_(cellOf s)`.
- Here `U_I` is the decision cell of `I`. It lies above the root for every cell of the first blocks (`b - 4K < R.1`), where no mode is alive, and the alive set can also be empty below the root.
- When it is empty, the function type is empty, since the domain `Finset Md` is nonempty. So these statements cannot be instantiated as stated.
- The anchors are only ever evaluated at cells and groups with successful classes, where the alive sets are nonempty. So the content is unaffected.

Fix (this session, in progress):
- The path and global layers take anchors depending on a proof `AncNe G I`: the alive sets of the core roles at the decision cell are nonempty.
- Quantities at cells without that proof are set by case split. They are empty there: no alive modes, no classes, no core subtotal.
- The per-cell layer (tests, bins, principal bounds) is unchanged.

## 2026-10-15T23:02:41-04:00

Anchor defect of 2026-10-15T22:42:24-04:00: fix completed. Full build passes; the axiom audit is standard.
- Path layer (Sec15_4, Sec15_5): `ancOf : ∀ s, AncNe G (cellOf s) → …` (`AncNe3 G (cellOf s) l` for three cores).
- `fourPathE`, `threePathE`, `fourUsedReps` and `threeUsedReps` are empty at scales without that proof (case split by `dite`).
- `FourPathAnc` and `ThreePathAnc` quantify over the proof; `fourPathE_card` and `threePathE_card` take it as a hypothesis.
- Global layer (Sec15_5): `anc : ∀ I G, AncNe G I → …`.
- The per-cell quantities of the global layer are `fourRetBinsA`, `fourCntA` and `fourBinSumA` (three cores: `threeRetBinsA`, `threeCntA`, `threeBinSumA`). Each is the per-cell quantity at the anchors when `AncNe` holds, and empty or zero otherwise.
- `four_principal_splitA` and `three_principal_splitA`: the per-cell split in this form.
- The principal-bound hypothesis `hP` of `four/three_core_final_side` is stated with `fourBinSumA`/`threeBinSumA`.
- Consequence for the leaf assembly: where `AncNe` fails, some core role has no alive mode at the decision cell, so its core vanishes and so does the pattern form. That vanishing is to be proved there.
- Unchanged: the per-cell layer (tests, bins, `four/three_core_principal_bins`). The standalone lemmas `four/three_negligible_side` and `four/three_retained_amps_card` are also unchanged; they hold for arbitrary anchors.

## 2026-10-15T23:50:38-04:00

Quantitative defect in the stack energies (eq:stack-energy, lines 2393-2399) of the side estimate on the side states. Fix in progress.

The defect:
- `block_energy` (Sec14_5b) bounds the energies of the block inputs `W_{G,b} = Z_b - Z_{u_b} + V_{G,b}` at the block starts by `sideB = 2 K (20 G₀ + 32) |R| + 2 K V_l |R|`.
- The bound comes from `sideState_budget`, which is the side budget of eq:side-cap at all depths of a block, hence the factor `K`.
- These energies are the `E_W` of the stacks. The hypotheses `hΓa`, `hΓb` of `side_estimate`, `side_estimate_leaf`, `core_reduction_leaf` and `leaf_bound` use `sideB`.
- As a result, `Γ_a`, `Γ_b` and the near-band term carry a factor of about `K`.
- The blueprint's eq:stack-energy is `Σ_{G,b} ‖stack‖² ≤ G₀ |R|`, free of `K`. Its block inputs use eq:variation on the intervals `[u_b, b]`, whose overlap over blocks is bounded, and each `V_{G,b}` once.
- `K ≤ C P^{C₅}` with `log D_* ≈ P^{C}`. So the extra factor would cancel the `P^{-1/2}` gain of eq:near-band in the final absorption (line 2876).

Fix:
- `rolling_budget_blocks`: for depths that are multiples of `K` (block starts), the rolling energy is at most `(20 G₀ + 32) |R|`. Color `t / K` modulo `5`: five colors instead of `5K`, and at most four early block starts.
- `sideState_budget_blocks`: at block starts, `2 (20 G₀ + 32) |R| + 2 Σ_b ‖V_{G,b}‖²`, each `V` counted once.
- `sideB0 = 2 (20 G₀ + 32) |R| + 2 V_l |R|` replaces `sideB` in `block_energy` and in the stack-energy hypotheses `hΓa`, `hΓb`.
- `sideB` (with `K`) remains the side budget `sideBs` of the side caps (eq:side-cap), where the blueprint also has `K`.

## 2026-10-16T00:05:56-04:00

Stack-energy defect of 2026-10-15T23:50:38-04:00: fixed.
- Sec13_4: `rolling_budget_blocks` and `sideState_budget_blocks`.
- Sec14_5b: `sideB0`. `block_energy` is now bounded by `sideB0`, and `side_estimate` passes `sideB0` as the block energy.
- The hypotheses `hΓa`, `hΓb` of `side_estimate`, `side_estimate_leaf`, `core_reduction_leaf` (Sec15_1) and `leaf_bound` (Sec16_2) use `sideB0`.
- The side caps keep `sideBs` with `sideB`, where the factor `K` is the blueprint's.
- The near-band term is now `(1 + C_N) P^{-1/2}` times `K`-free stack energies, logarithms of `K`, and `(K + 2)^{2(q-2)/(q-1)}`, as in eq:near-band.

## 2026-10-16T00:05:56-04:00

Interface correction (main tests of the far bound, lines 2252-2258).
- Previously, `leaf_farM`, `leaf_far_search`, `far_bound`, `side_estimate_leaf`, `core_reduction_leaf` and `leaf_bound` required the main tests with the basic input `basicIn` to pass in every slot, including the basic `U` slot.
- The attempt's catalogs (`exists_attempt`, `attempt_localization`) close the tests of the pattern inputs. In the `U` slot that input is `U`, not `basicIn`.
- The far bound only uses the two transfer slots `c, d`, which are basic: `¬ Ucase c d`.
- The hypothesis is now restricted. In `leaf_farM` and `leaf_far_search` it is required for `l = c ∨ l = d`; from `far_bound` up through `leaf_bound`, for the slots with `D.u ≠ some l`.
- In those slots the pattern input equals `basicIn` (`patIn_of_ne`).
- This is not a change of mathematics: the blueprint's tests are those of the actual pattern inputs.

## 2026-10-16T00:28:09-04:00

Interface additions for the leaf assembly. Full build passes.
- `exists_vchart` (Sec12_3b) has an unconditional complexity component. For unavailable vertices the chart is the zero chart of dimension one, which has that complexity.
- New `vchart_complexity`: every vertex tag has dimension at most `log(max H padW)` and rational heights at most `max H padW`.
- This gives the hypotheses `∀ w, (bf.vtag w).dim ≤ d_B` and the center height bounds used by `exists_leaf_modes` and `first_top_count_main`, which quantify over all vertices.
- `attempt_localization` (Sec12_4) and `exists_attempt` (Sec16_1) export `occAvail` of the tags of the main catalog columns. This is derived from the masks in `main_closure` and is used by `BallData` and `first_top_count_main`.
- New `helper_sides_closure` (Sec16_1): the helper catalogs on the closure counts of the attempt's main catalogs. Blueprint line 1828 has one sequence `n_r` for all `L + 5` ranks.
- Previously `helper_sides` recomputed its own counts with `closure_poly`. Its helper thresholds `catThreshold … n (L+5)` were then not tied to the main counts `n(L+4)` of the far bound (`hτH'` of `leaf_bound`).

## 2026-10-16T00:54:09-04:00

Interface corrections found while assembling one leaf (blueprint lines 1777-1789, 1828, 2167-2169).
- Helper base names (lines 1828, 2167-2169: "for one active cell there are only the already bounded main groups"). `far_bound`, `side_estimate_leaf`, `core_reduction_leaf`, `leaf_bound` and `hhpass_appendCat` used helper names `HelperName I gset`. That indexes the bases by all groups of the leaf, whose number is not bounded per cell. The closure counts `n_r`, `T` and the helper name bound `K_t` would then depend on the number of cells.
- Fix: these lemmas take a base-name type `Bh` and an enumeration `gE I : Bh → Grp` of the groups of each cell (`hgE`). The attempt uses `Bh = Fin famVtxBound`. The far bound uses only the base of the group at hand.
- Ball-label overlap counts (lem:whole-ranges: "usable endpoint cells whose masks contain their tags"; "group and label counts on paths"). In `main_wr1`, `main_wr2` and every statement above them, through `BallData` and `first_top_count_main` (31 statements), the count of group-label pairs at a point ranged over all cells containing the point.
- Fix: the count now ranges over cells with a downstream use certificate of the group (`∃ k', fp.Cert k' G I`), which are the only cells used.
- Separation (lem:masks) applies only to certified endpoints, and without certificates the count is not bounded. With them, `card_ballPairs_le` bounds it by the main labels on the path (`card_pathLabels_le`: `8 colBudget` plus the template path count).

## 2026-10-16T01:03:20-04:00

Two further interface corrections for the leaf assembly.
- Main test ranks (lines 1815, 1828: main ranks `1, …, L + 4`, helper rank `L + 5` reserved). The test names `TestName` (Sec12_3b) allow target and history ranks up to `L + 5`, so the main catalogs of `exists_attempt` close tests of the helper rank too. After the helper templates are appended, only main tests of rank at most `L + 4` keep passing (`helper_instantiation_main`).
- The far bound needs only target ranks `brank j ≤ L + 4` and `crank m ≤ L + 1`, with cumulative histories.
- Fix: new predicate `MainRk` (Sec14_1). The hypothesis `hpass` of `chain_passM`, `chain_passR`, `leaf_farM`, `leaf_far_search`, `far_bound`, `side_estimate_leaf`, `core_reduction_leaf` and `leaf_bound` is restricted to names of main rank (`mainRk_layerName`). This weakens the hypotheses only; the attempt's closure is unchanged.
- Type-class nodes (`hNdR` of `leafRep_repOK`, `leafNd_mem`, `leaf_core_estimate`, `leaf_bound`). Previously required at every height. `first_top_count_main` provides the type classes for heights `h ≤ J_*`, and the core estimate uses only the upper heights (`⊆ [0, J_*]`). The hypothesis is now `∀ h ≤ J_*`.

## 2026-10-16T05:06:25-04:00

Exports added for the explicit leaf bound (no change to the blueprint statements).
- `MainLiftExports.εM_le` (Sec13_1): the private mode weights are at most the main weights,
  as constructed (`εM = w(own) (Σ‖coef‖² + 1)⁻¹`). Needed for the class sizes (`clsSize_le`).
- `exists_leaf_modes` (Sec16_1): also returns the trivial mode systems off the used groups
  (`Bσ = 1`, no alive modes). Stabilization (`stab_of_valid`) quantifies over all groups.
- `leaf_bound` (Sec16_2): also returns the local side sizes `√T_c ≤ U` on the retained cells.
  These feed the three-core tuple errors (`threeErr_le`).
- The core-error accuracy is `ε = (U³ D_*⁵ e^k (1 + M_p V))⁻¹`, not `(U³ D_*⁴ e^k)⁻¹`.
  The core errors are summed over at most `M_p V` groups per point (`M_p` the active
  multiplicity, `V = famVtxBound`). The extra factor enters the main terms only through
  `log(U/ε)`.
- The enlarged budget `D_*` is built at an accuracy `k_D ≥ k` (`modeStarG … k_D …`).
  Its `e^{k_D}` summand then dominates the active multiplicity in the `D_*^{-90}` errors.
  All degree bounds (`log_modeStarG_poly`) hold at `k_D`, as in the blueprint ("increase the
  starting logarithm").
