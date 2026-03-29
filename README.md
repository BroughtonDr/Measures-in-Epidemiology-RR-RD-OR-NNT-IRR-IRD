# 📊 Measures of Association in Epidemiology
### RR · RD · OR · NNT · IRR · IRD
**Tutorial Series: Epidemiology with Python**
*Desy Nuryunarsih — Researcher, University of St Andrews*

---

## 📖 Overview

This tutorial introduces **six fundamental measures of association** used in epidemiology. It is designed for **complete beginners** — no prior statistics background is required.

We use a **simulated dataset** of 600 individuals to explore the relationship between **smoking** (exposure) and **lung cancer** (outcome), followed over up to 52 weeks.

---

## 🎯 Learning Objectives

By the end of this tutorial, you will be able to:

- Explain the difference between **relative** and **absolute** measures of association
- Calculate and interpret **RR, RD, OR, NNT, IRR, and IRD** using Python
- Understand **when to use** each measure in real research contexts
- Read and interpret **confidence intervals** for each measure
- Recognise the difference between **risk-based** and **rate-based** measures

---

## 📁 File

| File | Description |
|------|-------------|
| `Measures_in_Epidemiology_Smoking.ipynb` | Main Jupyter notebook — all code, explanations, and outputs |

---

## 🗃️ Dataset

The dataset is **fully simulated** inside the notebook using `numpy`. No external files needed.

| Variable | Description | Values |
|----------|-------------|--------|
| `smoking` | Exposure: smoking status | 1 = smoker, 0 = non-smoker |
| `lung_cancer` | Outcome: lung cancer diagnosis | 1 = diagnosed, 0 = not diagnosed |
| `follow_up_weeks` | Person-time contributed | 20–52 weeks |

- **N = 600** (300 smokers, 300 non-smokers)
- **~20 missing values** in `lung_cancer` (realistic simulation)
- **Seed:** `np.random.seed(42)` — fully reproducible

---

## 📐 Measures Covered

| # | Measure | Formula | Plain English |
|---|---------|---------|---------------|
| 1 | **Risk Ratio (RR)** | Pr(Y=1\|A=1) / Pr(Y=1\|A=0) | How many times more likely? https://www.cancer.gov/publications/dictionaries/cancer-terms/def/risk-ratio|
| 2 | **Risk Difference (RD)** | Pr(Y=1\|A=1) − Pr(Y=1\|A=0) | What is the extra absolute risk? https://pmc.ncbi.nlm.nih.gov/articles/PMC5300861/|
| 3 | **Odds Ratio (OR)** | Odds(A=1) / Odds(A=0) | Ratio of odds — used in case-control & logistic regression https://www.cancer.gov/publications/dictionaries/cancer-terms/def/odds-ratio |
| 4 | **Number Needed to Harm (NNH)** | 1 / \|RD\| | How many smokers produce 1 extra cancer case? https://www.sciencedirect.com/topics/pharmacology-toxicology-and-pharmaceutical-science/number-needed-to-harm|
| 5 | **Incidence Rate Ratio (IRR)** | (a/T₁) / (b/T₀) | Rate ratio accounting for person-time https://academic.oup.com/aje/article-abstract/167/5/517/212297?redirectedFrom=PDF|
| 6 | **Incidence Rate Difference (IRD)** | (a/T₁) − (b/T₀) | Absolute rate difference per person-week https://pubmed.ncbi.nlm.nih.gov/20606039/|

---

## 🔑 Key Results (from simulated data)

| Measure | Estimate | 95% CI |
|---------|----------|--------|
| RR | 2.72 | (1.88, 3.94) |
| RD | 0.19 | (0.13, 0.25) |
| OR | 3.46 | (2.21, 5.39) |
| NNH | 5.27 | (NNT 7.95 to NNH 3.94) |
| IRR | 2.69 | (1.79, 4.03) |
| IRD | 0.005 per person-week | (0.003, 0.007) |

> ✅ All estimates indicate a **positive association** between smoking and lung cancer in this simulated cohort.

---

## ⚙️ Requirements

```
Python >= 3.7
zepid
numpy
pandas
```

Install with:
```bash
pip install zepid numpy pandas
```

---

## 🚀 How to Run

### Option 1: Google Colab (recommended for beginners)
1. Upload `Measures_in_Epidemiology_Smoking.ipynb` to [Google Colab](https://colab.research.google.com)
2. Run all cells from top to bottom (`Runtime → Run all`)
3. The `!pip install zepid` cell at the top will handle installation automatically

### Option 2: Local Jupyter
```bash
pip install zepid numpy pandas jupyter
jupyter notebook Measures_in_Epidemiology_Smoking.ipynb
```

---

## 📚 References

- Zivich PN et al. *zEpid: An epidemiology toolbox in Python.* JOSS, 2022.
- Rothman KJ, Greenland S, Lash TL. *Modern Epidemiology*, 3rd edition.
- Altman DG. *Confidence intervals for the number needed to treat.* BMJ, 1998.

---

## 👩‍🔬 Author

**Desy Nuryunarsih**
Research Fellow, University of St Andrews
*Tutorial Series: Epidemiology with Python*

---

> ⚠️ **Note:** These measures describe *associations*, not causal effects. Observational data alone cannot establish causation. See causal inference methods (e.g., inverse probability weighting) for effect estimation.
