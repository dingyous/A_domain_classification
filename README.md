# A Domain Classification (A vs Ak vs CAL)

## Overview

Adenylation-related domains in NRPS systems—including canonical A domains, specialized adenylation (Ak) domains, and coenzyme A ligase (CAL) domains—are evolutionarily related enzyme modules involved in substrate activation, but differ in substrate preference and catalytic architecture. 
This tool classifies these domain types directly from amino-acid sequences using protein language model embeddings and machine learning models.

**Key features**
- Sequence-based domain classification
- ESM-2 protein language model embeddings
- Multiple classifiers (Logistic Regression, SVM, Random Forest, XGBoost)
- Multiclass classification (A / Ak / CAL)


## Installation

### 1. Clone the repository

```bash
git clone https://github.com/Xinyingtsai/A_domain_classification.git
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

- **model/**  
  Stores trained machine learning classifiers (`.pkl` files) for reuse without retraining.

- **CAL_A_domain_prediction_binary.ipynb**  
  Notebook for binary classification tasks.

- **CAL_A_domain_prediction_multiclass.ipynb**  
  Main notebook for multiclass classification of A, Ak, and CAL domains.  
  Includes embedding processing, visualization, model training, and evaluation.

- **requirements.txt**  
  Python dependencies required to run the project.

---

## Usage

Run the multiclass classification pipeline:

```bash
jupyter notebook CAL_A_domain_prediction_multiclass.ipynb
```

The notebook performs:
- ESM-2 embedding
- UMAP visualization  
- Multiclass classification  
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
