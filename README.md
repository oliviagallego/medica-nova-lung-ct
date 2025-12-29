# Medica Nova — Lung CT Malignancy Classification (Applied AI in Biomedicine)

Course project (Politecnico di Milano, AY 2024/2025): ML/DL models to classify lung CT scans by malignancy score and **benign vs malignant**.

## Overview
Dataset: ~2300 patients, each with two CT views:
- **Full-slice** image
- **Nodule zoom (ROI)** image

Labels:
- Malignancy score **1–5**
- Binary task: **benign (1–3)** vs **malignant (4–5)**

## Methods
**Pipeline**
- Data cleaning + stratified split (train/val/test)
- Preprocessing: resizing + normalization

**Feature engineering**
- First-order statistics
- Texture (GLCM)
- Wavelet features
- Morphological features (segmentation-based)

**Models**
- Classical ML: Logistic Regression, Decision Tree, Random Forest (+ Optuna tuning)
- Probability calibration (Platt scaling)
- Deep learning: CNN, EfficientNet, ResNet50, VGG16

## Key results (from report)
| Task / Input | Best approach | F1 | ROC AUC |
|---|---|---:|---:|
| Binary (nodule ROI) | Random Forest + Optuna + calibration | **0.8401** | **0.8410** |
| Binary (full-slice) | Random Forest | 0.7098 | — |

Deep learning models underperformed, likely due to class imbalance and limited dataset size.

## Repository structure
- `notebooks/` — main notebook (end-to-end pipeline)
- `reports/` — final PDF report
- `data/` — `.xlsx` files used for testing / labels *(no CT images included)*

## How to run
1. Clone the repo
   ```bash
   git clone https://github.com/oliviagallego/medica-nova-lung-ct.git
   cd medica-nova-lung-ct
