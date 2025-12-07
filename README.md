# LUMINA — Spatio-Cellular Architecture of Early Macular Degeneration

A research/analysis repo that combines **retinal single-cell transcriptomics metadata** with **curated AMD gene evidence (eQTL + literature)** to (1) build a **multi-layer gene→cell-type→tissue network** and (2) benchmark **machine learning + a RoPE-Transformer (TensorFlow)** for phenotype/cell-type related classification tasks.

## What’s inside
- **Single-cell metadata pipeline (Scanpy/AnnData)**: load `.h5ad` and export metadata tables.
- **Knowledge graph construction (NetworkX)**:
  - curated AMD genes + evidence types
  - exported as **nodes/edges CSVs** for visualization (Gephi/Cytoscape).
- **Modeling & benchmarking (scikit-learn + TensorFlow)**:
  - TF-IDF + classic ML baselines (LR/SVM/NB/Tree ensembles)
  - a **RoPE-Transformer** text-style model over engineered “metadata tokens”.

## Data
This repo uses a metadata table (example: `Macular.csv`) containing ~100k observations and columns like:
- `cell_type`, `author_cell_type`, `tissue`, `sex`, `development_stage`, `donor_id`, etc.

> Recommended: don’t commit large datasets directly to GitHub. Use **Git LFS**, Releases, or provide a download script.

## Quick start

### 1) Create environment
```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
source .venv/bin/activate

pip install -U pip
pip install scanpy anndata pandas numpy matplotlib networkx scikit-learn tensorflow
