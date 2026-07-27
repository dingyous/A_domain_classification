# A Domain Classification (A vs KAL)

## Overview

Canonical adenylation (A) domains and 2-keto acid AMP ligase (KAL) domains are evolutionarily related enzyme modules involved in substrate activation but differ in substrate preferences and catalytic functions.

This tool distinguishes A domains from KAL domains directly from amino acid sequences using protein language model embeddings and machine learning models.

**Key features**
- Sequence-based domain classification
- ESM-2 protein language model embeddings
- Multiple classifiers (Logistic Regression, SVM, Random Forest, XGBoost)
- Binary classification (KAL/A)


## Installation

### 1. Clone the repository

```bash
git clone https://github.com/dingyous/A_domain_classification.git
cd A_domain_classification
```

### 2. Create and activate a Python environment

Using conda:

```bash
conda create -n a_domain_esm python=3.9
conda activate a_domain_esm
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

If PyTorch is not installed automatically, install it explicitly:

```bash
python -m pip install torch
python -m pip install fair-esm
```

---

## Repository Structure

- **data/**  
  Contains input FASTA files (domain sequences).

- **saved_models_A_vs_KAL/**  
  Stores trained machine learning classifiers (`.pkl` files) for reuse without retraining.

- **A_domain_prediction_KAL.ipynb**  

- **requirements.txt**  
  Python dependencies required to run the project.

---

## Usage

Run the binary classification pipeline:

```bash
jupyter notebook A_domain_prediction_KAL.ipynb
```

The notebook performs:
- ESM-2 embedding
- UMAP visualization  
- Cross-validation evaluation  
- Model saving (`.pkl`)  

---

## Output

The pipeline generates:
- Cross-validation performance results  
- Per-class evaluation metrics  
- Fold-level predictions  
- Trained models (`.pkl`)  

---

## Training Models

**1. ESM-based classification using protein language model embeddings**
- Generate embeddings using ESM-2  
- Apply mean pooling to obtain fixed-length vectors  
- Train classifiers (LR, SVM, RF, XGBoost)  

**2. Visualization and analysis**
- UMAP projection of embedding space  
- Assessment of domain separability  

---

## Applications

- Classification of adenylation-related domains in NRPS gene clusters  
- Functional annotation of biosynthetic gene clusters  
- Supporting NRPS engineering and module design  
- Identifying domain-level functional diversity beyond sequence identity  

---

## Citation

If you use this code in your research, please cite our paper:
