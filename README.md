Andrographolide vs Head and Neck Cancer
### A Network Pharmacology & Molecular Docking Pipeline

![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Field](https://img.shields.io/badge/Field-Bioinformatics-blue)
![Tools](https://img.shields.io/badge/Tools-STRING%20%7C%20Cytoscape%20%7C%20CB--Dock2-orange)

**Author:** Vaibhav Bhujbal  
**Field:** Computational Biology / Zoology  
**Location:** Maharashtra, India  
**Contact:** bhujbalv9553@gmail.com

---

## 📌 About This Project

Andrographolide is a natural compound from *Andrographis paniculata*,
a medicinal plant used in Ayurvedic medicine. This project uses free 
online bioinformatics tools to systematically identify which cancer 
proteins it may target in head and neck cancer (HNC) — and validates 
those predictions against real Indian patient data.

---

## 🔬 Pipeline Overview
Andrographolide → ADMET → Target Prediction → Disease Genes
→ Common Targets (87) → PPI Network → Pathway Analysis
→ Patient Validation (GEO) → Molecular Docking

---

## 📋 Step-by-Step Pipeline

### Step 1 — Drug Profiling
| Item | Detail |
|------|--------|
| Tools | SwissADME, pkCSM |
| Goal | Check oral drug-likeness |
| Result | ✅ Passed all Lipinski criteria, 0 violations |

### Step 2 — Target Prediction
| Item | Detail |
|------|--------|
| Tools | SwissTargetPrediction, SuperPred |
| Goal | Predict human protein targets |
| Result | 207 putative targets identified |

### Step 3 — Disease Gene Collection
| Item | Detail |
|------|--------|
| Tools | GeneCards, OMIM, Open Targets Platform |
| Goal | Collect HNC-associated genes |
| Result | 17,020 disease genes collected |

### Step 4 — Common Target Identification
| Item | Detail |
|------|--------|
| Tool | Microsoft Excel (COUNTIF) |
| Goal | Find drug-disease gene overlap |
| Result | **87 shared targets identified** |

### Step 5 — PPI Network Construction
| Item | Detail |
|------|--------|
| Tools | STRING v12.0, Cytoscape v3.10.2 |
| Goal | Build protein interaction network, find hub genes |
| Settings | Confidence score > 0.700 |
| Result | 10 hub genes: EGFR, CDK1, CHEK1, PPARG, PTGS2, MAPK1, MAPK3, JAK2, MAPK14, CYP11B2 |

### Step 6 — Pathway Enrichment Analysis
| Item | Detail |
|------|--------|
| Tool | Metascape |
| Goal | GO and KEGG pathway analysis |
| Result | Top: Pathways in cancer (p = 1×10⁻¹⁶) |

### Step 7 — Patient Data Validation
| Item | Detail |
|------|--------|
| Tool | GEO2R — NCBI |
| Datasets | GSE23558 (Indian OSCC), GSE30784 (US OSCC) |
| Goal | Confirm hub genes are dysregulated in real patients |
| Result | 8/10 hub genes significant in GSE30784 |

> 💡 GSE23558 was chosen specifically because it contains
> Indian OSCC patient data — directly relevant to India's 
> high oral cancer burden.

### Step 8 — Molecular Docking
| Item | Detail |
|------|--------|
| Tool | CB-Dock2 (AutoDock Vina) |
| Mode | Blind docking |
| Goal | Test andrographolide binding to hub proteins |
| Result | All targets scored below −7.5 kcal/mol |

---

## 📊 Key Results

| Target | Role in HNC | Expression in OSCC | Docking (kcal/mol) |
|--------|------------|-------------------|-------------------|
| EGFR | Primary oncogenic driver | ⬆ Upregulated | −7.9 |
| CDK1 | Cell cycle (G2/M) | ⬆ Upregulated | −8.4 |
| CHEK1 | DNA damage checkpoint | ⬆ Upregulated | −8.2 |
| PPARG | Tumour suppressor | ⬇ Downregulated | −9.16 |
| PTGS2 | COX-2 / Inflammation | ⬆ Upregulated | −8.9 |

---

## 🗂️ Repository Structure
