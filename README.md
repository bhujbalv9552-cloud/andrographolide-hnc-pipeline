# andrographolide-hnc-pipeline
Network pharmacology and molecular docking pipeline for andrographolide in head and neck cancer
# Andrographolide in Head and Neck Cancer
## A Network Pharmacology Pipeline

**Author:** Vaibhav Bhujbal
**Field:** Computational Biology / Zoology
**Institution:** Maharashtra, India

---

## About This Project
This project maps the potential targets of andrographolide
(a compound from Andrographis paniculata plant) against 
head and neck cancer using free online bioinformatics tools.

---

## Pipeline Steps

### Step 1 — Drug Profiling
- Tool: SwissADME, pkCSM
- What I did: Checked if andrographolide is drug-like
- Result: Passed all Lipinski criteria, zero violations

### Step 2 — Target Prediction
- Tool: SwissTargetPrediction, SuperPred
- What I did: Predicted which human proteins it may bind
- Result: 207 putative targets

### Step 3 — Disease Gene Collection
- Tool: GeneCards, OMIM, Open Targets Platform
- What I did: Collected HNC-associated genes
- Result: 17,020 disease genes

### Step 4 — Finding Common Targets
- Tool: Microsoft Excel (COUNTIF)
- What I did: Found overlap between drug targets and disease genes
- Result: 87 common targets

### Step 5 — PPI Network
- Tool: STRING v12, Cytoscape v3.10
- What I did: Built protein interaction network, found hub genes
- Result: 10 hub genes including EGFR, CDK1, CHEK1, PPARG

### Step 6 — Pathway Analysis
- Tool: Metascape
- What I did: GO and KEGG enrichment of 87 targets
- Result: Top pathway — Pathways in cancer (p=1e-16)

### Step 7 — Patient Data Validation
- Tool: GEO2R (NCBI)
- Datasets: GSE23558 (Indian OSCC), GSE30784 (US OSCC)
- What I did: Checked if hub genes are actually dysregulated in patients
- Result: 8/10 hub genes significant in GSE30784

### Step 8 — Molecular Docking
- Tool: CB-Dock2
- What I did: Docked andrographolide against 10 hub proteins
- Result: Best binding to PPARG (-9.16 kcal/mol), CDK1 (-8.4 kcal/mol)

---

## Key Results Summary

| Target | Expression in OSCC | Docking Score |
|--------|-------------------|---------------|
| EGFR   | Upregulated       | -7.9 kcal/mol |
| CDK1   | Upregulated       | -8.4 kcal/mol |
| CHEK1  | Upregulated       | -8.2 kcal/mol |
| PPARG  | Downregulated     | -9.16 kcal/mol|
| PTGS2  | Upregulated       | -8.9 kcal/mol |

---

## Files in This Repository
- `data/` — target lists and gene sets
- `results/` — docking scores, expression data
- `figures/` — network, Venn diagram, docking images
- `methods.md` — detailed tool settings used
