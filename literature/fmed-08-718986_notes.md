# Notes on: Expression of LOX Suggests Poor Prognosis in Gastric Cancer

**Citation:** Zhu et al. (2021). Frontiers in Medicine, Vol. 8, Article 718986.
**PMC:** https://pmc.ncbi.nlm.nih.gov/articles/PMC8476844/

---

## Key Facts

- Uses **GSE84437** (same dataset as our analysis, 433 patients)
- Also uses TCGA gastric cancer data (375 samples) for cross-validation
- Focuses on **LOX** (Lysyl Oxidase), not LOXL4 — hypothesis-driven, not genome-wide

---

## Their Methods vs. Ours

| | Zhu et al. 2021 | Our analysis |
|---|---|---|
| Gene selection | Hypothesis-driven (LOX only) | Genome-wide unbiased screen |
| Survival method | KM + univariate/multivariate Cox | Stratified Cox with FDR correction |
| PH assumption | Not reported | Tested — stratified for violation |
| Log2 transform | Not reported | Applied (raw intensities confirmed) |
| Outlier analysis | Not reported | Deviance residuals + sensitivity analysis |

---

## Their Key Findings

- LOX mRNA significantly elevated in gastric cancer vs. normal tissue (p = 3.5e-11)
- High LOX expression associates with worse survival in both TCGA (p = 0.007) and GSE84437 (p = 0.031)
- Multivariate Cox: LOX is an independent prognostic factor (p = 0.015)
- High LOX correlates with advanced T stage and clinical staging
- GSEA: ECM-receptor interaction, TGF-beta, Wnt, mTOR pathways enriched
- Immune microenvironment: increased M2 macrophages in high-LOX tumours

---

## Relevance to Our LOXL4 Finding

- LOX and LOXL4 are members of the **same gene family** — both are copper-dependent amine oxidases involved in collagen and elastin crosslinking
- This paper provides independent biological support for our LOXL4 result — two members of the same family are both prognostic in gastric cancer, consistent with a broader role of LOX family enzymes in ECM remodelling and tumour aggressiveness
- LOXL4 is mentioned in the paper as a related family member but not analysed — our finding fills this gap
- The paper did not find LOXL4 because they did not look for it (hypothesis-driven approach)

---

## What Our Analysis Adds

- Unbiased genome-wide screen on the same dataset identified LOXL4 independently
- More rigorous statistical methodology (PH testing, stratification, FDR correction)
- LOXL4 finding is complementary and novel relative to this paper
- Convergence of LOX and LOXL4 as prognostic markers strengthens the biological story around the LOX family in gastric cancer

---

## To Do

- Cite this paper in the biological interpretation section of the notebook
- Consider mentioning that LOX (the family parent) was previously identified as prognostic in the same dataset, and that our unbiased screen independently identified LOXL4 as a related family member
