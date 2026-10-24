# TRIAD-BRCA+

**Knowledge-Guided Heterogeneous Ensembling with Balanced-Risk Decision Calibration for Leakage-Controlled PAM50 Breast Cancer Subtyping and Harmonised Cross-Cohort Transfer**

Himani Agrawal and Megha Rathi, Department of CSE & IT, Jaypee Institute of Information Technology, Noida, India

<!-- After the first GitHub release is archived by Zenodo, replace XXXXXXX with the concept DOI suffix (the "all versions" DOI). -->
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)

This repository holds the code, figures and tables for the TRIAD-BRCA+ manuscript (submitted to the *Journal of Computer Science & Technology*). TRIAD-BRCA+ predicts the four reproducible PAM50 intrinsic subtypes (Basal-like, HER2-enriched, Luminal A, Luminal B) from METABRIC multi-view data under a leakage-controlled protocol, and transfers to TCGA-BRCA with label-free per-cohort harmonisation.

| | METABRIC (repeated 5-fold CV × 2) | TCGA-BRCA transfer |
|---|---|---|
| Balanced accuracy | 0.849 ± 0.019 | 0.695 |
| Macro-F1 | 0.844 ± 0.021 | 0.673 |
| MCC | 0.780 ± 0.031 | 0.510 |
| Macro-AUC | 0.972 ± 0.006 | — |

## Repository contents

```
TRIAD-BRCA-plus/
├── TRIAD-BRCA-plus_Colab.ipynb       complete pipeline: data loading, cross-validation, leakage audit,
│                                     learning curves, external transfer, and every table and figure
├── data/
│   └── README.md                     where to download the five input files (not redistributed)
├── Figures/                          Figure_1.png … Figure_17.png (300 dpi) + captions
├── Tables/                           Table_1.csv … Table_24.csv, All_Tables.xlsx + captions
├── requirements.txt
├── CITATION.cff
└── README.md
```

Figures and tables are numbered exactly as in the manuscript; see [Figures/README.md](Figures/README.md) and [Tables/README.md](Tables/README.md) for captions.

## Data

All inputs are public. Download the five files listed in [data/README.md](data/README.md) (manuscript references [86]–[90]) from their sources:

- METABRIC RNA/mutation/clinical: https://www.kaggle.com/datasets/raghadalharbi/breast-cancer-gene-expression-profiles-metabric
- METABRIC clinical with relapse-free survival: https://www.kaggle.com/datasets/gunesevitan/breast-cancer-metabric
- METABRIC cBioPortal clinical export: https://www.cbioportal.org/study/summary?id=brca_metabric
- TCGA-BRCA multi-omics: https://www.kaggle.com/datasets/samdemharter/brca-multiomics-tcga
- TCGA-BRCA GDC clinical: https://portal.gdc.cancer.gov/projects/TCGA-BRCA

## Reproducing the results

**Google Colab (as used for the paper)**

1. Open `TRIAD-BRCA-plus_Colab.ipynb` in Colab (a CPU runtime is enough).
2. Run all cells. When asked, upload the five CSV files. Alternatively, set `USE_GOOGLE_DRIVE = True` in the first cell and put the files in `MyDrive/TRIAD-BRCA-plus/data`.
3. Outputs are written to `results/`: `tables/`, `figures/`, `TRIAD-BRCA-plus_all_tables.xlsx` and `captions.csv`, and are zipped as `TRIAD-BRCA-plus_results.zip` at the end.

**Locally**

```bash
pip install -r requirements.txt
mkdir -p data && cp /path/to/the/five/*.csv data/
jupyter notebook TRIAD-BRCA-plus_Colab.ipynb   # reads data/ and writes results/ next to the notebook
```

Settings in the first cell:

| Setting | Default | Meaning |
|---|---|---|
| `QUICK` | `False` | `True` runs a reduced 3-fold × 1 protocol for a fast check (numbers will differ from the paper) |
| `N_JOBS` | `2` | outer folds processed in parallel |
| `FORCE_RERUN` | `False` | ignore cached fold results and recompute |

All randomness is controlled by a single seed (42), and BLAS/OpenMP thread pools are fixed to one thread. The saved run in the notebook took about 100 minutes on a 2-core Colab CPU runtime (cross-validation 76 min, leakage audit 10 min, learning curves 14 min, external transfer 1.5 min). Results are reproducible on a given platform; different library versions or hardware can change the last decimal places of a few values.

## Citation

If you use this code, figures or tables, please cite the article (GitHub's "Cite this repository" button uses [CITATION.cff](CITATION.cff)):

> H. Agrawal and M. Rathi. TRIAD-BRCA+: Knowledge-Guided Heterogeneous Ensembling with Balanced-Risk Decision Calibration for Leakage-Controlled PAM50 Breast Cancer Subtyping and Harmonised Cross-Cohort Transfer. *Journal of Computer Science & Technology* (submitted).

## License

<!-- Choose a license (e.g. MIT for the code, CC BY 4.0 for figures and tables), add the LICENSE file, and state it here. -->
To be added.

## Contact

Himani Agrawal (agrawal.himani1010@gmail.com), Megha Rathi (megha.rathi@mail.jiit.ac.in)
