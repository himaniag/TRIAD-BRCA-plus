# Figures

All figures from the TRIAD-BRCA+ manuscript, numbered as in the paper (PNG, 300 dpi).

| File | Caption |
|---|---|
| [Figure_1.png](Figure_1.png) | **Figure 1.** Architecture of TRIAD-BRCA+. Stages 1–4 are fitted strictly inside each outer training fold; Stage 5 transfers the framework to TCGA-BRCA. |
| [Figure_2.png](Figure_2.png) | **Figure 2.** (a) PAM50 label distribution in METABRIC; the four reproducible subtypes form the analytical cohort. (b) Distribution of four knowledge-guided module scores by subtype. |
| [Figure_3.png](Figure_3.png) | **Figure 3.** Leakage audit (10 paired folds). (a) Change in balanced accuracy when each excluded channel is re-inserted, for three probes (mean ± SD). (b) Optimism from reporting accuracy instead of balanced accuracy, and from fitting preprocessing on the full cohort (v1 SVM expert). |
| [Figure_4.png](Figure_4.png) | **Figure 4.** Model comparison (mean ± SD over 10 paired folds; small dots = individual folds). Dashed line: TRIAD-BRCA v1 equal-weight ensemble. |
| [Figure_5.png](Figure_5.png) | **Figure 5.** Critical-difference diagram of mean balanced-accuracy ranks over the 10 paired folds (lower rank = better). Thick bars join models that are not significantly different (Nemenyi). |
| [Figure_6.png](Figure_6.png) | **Figure 6.** Incremental ablation waterfall from TRIAD-BRCA v1 (A0) to TRIAD-BRCA+ (A5); labels give the mean change contributed by each component. |
| [Figure_7.png](Figure_7.png) | **Figure 7.** Balanced accuracy for every combination of fusion and decision rule on the same TRIAD-BRCA+ expert fits. Gains come from the decision layer, not from learned or adaptive fusion. |
| [Figure_8.png](Figure_8.png) | **Figure 8.** Confusion matrices of pooled out-of-fold predictions (repeat 1, n = 1,559); cell text: count and row-normalised recall. |
| [Figure_9.png](Figure_9.png) | **Figure 9.** Per-subtype receiver operating characteristic (ROC) and precision–recall curves of the TRIAD-BRCA+ fused posterior (pooled out-of-fold, repeat 1). |
| [Figure_10.png](Figure_10.png) | **Figure 10.** Per-subtype F1 with bootstrap 95% CIs (pooled out-of-fold predictions). |
| [Figure_11.png](Figure_11.png) | **Figure 11.** Top-label reliability diagrams (10 bins, pooled out-of-fold posteriors). |
| [Figure_12.png](Figure_12.png) | **Figure 12.** Permutation importance of TRIAD-BRCA+ on outer test folds (repeat 1). |
| [Figure_13.png](Figure_13.png) | **Figure 13.** Pairwise error correlation between experts (pooled out-of-fold predictions). |
| [Figure_14.png](Figure_14.png) | **Figure 14.** Robustness to degraded molecular input at inference (mean ± SD, 5 folds). |
| [Figure_15.png](Figure_15.png) | **Figure 15.** Learning curves (mean ± SD over 5 folds of repeat 1). |
| [Figure_16.png](Figure_16.png) | **Figure 16.** Kaplan–Meier curves by reference PAM50 label and by TRIAD-BRCA+ out-of-fold prediction. |
| [Figure_17.png](Figure_17.png) | **Figure 17.** External transfer to TCGA-BRCA (n = 506). (a) Balanced accuracy with bootstrap 95% CIs under the v1 protocol (E1) and the proposed harmonisation protocols (E2, E3). (b–c) Confusion matrices. |
