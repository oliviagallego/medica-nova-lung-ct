# Medica Nova — Lung CT Malignancy Classification (Applied AI in Biomedicine)

Course project (Politecnico di Milano, AY 2024/2025): develop ML/DL models to classify lung CT scans by malignancy score and benign vs malignant.

## Overview
We work with ~2300 patients, each with two CT images:
- **Full-slice** image
- **Nodule zoom** image (ROI)
Labels are malignancy scores **1–5**, and we also evaluate **binary** classification (benign 1–3 vs malignant 4–5). :contentReference[oaicite:0]{index=0}

## Methods
- Data cleaning + stratified split (train/val/test)
- Preprocessing: resize + normalization
- Feature engineering:
  - First-order statistics
  - Texture (GLCM)
  - Wavelet features
  - Morphological features (nodule segmentation-based) :contentReference[oaicite:1]{index=1}
- Models:
  - Classical ML: Logistic Regression, Decision Tree, Random Forest (+ Optuna tuning)
  - Probability calibration (Platt scaling)
  - Deep learning: CNN, EfficientNet, ResNet50, VGG16 :contentReference[oaicite:2]{index=2}

## Key Results (from report)
- **Binary (nodule-based) Random Forest + Optuna + calibration** achieved **F1 = 0.8401** and **ROC AUC = 0.8410**. :contentReference[oaicite:3]{index=3}  
- Full-slice binary RF reached **F1 = 0.7098**. :contentReference[oaicite:4]{index=4}  
- Deep learning models struggled due to class imbalance and dataset size. :contentReference[oaicite:5]{index=5}

## Repository Structure
- `notebooks/` — main notebook with the pipeline
- `reports/` — final PDF report
- `data/` — (optional) small sample files / or instructions to obtain data

## How to run
1. Create environment
   - `pip install -r requirements.txt` *(add if you create it)*
2. Open `notebooks/notebook_medica_nova.ipynb` and run top to bottom.

## Authors
Aurore Bechet de la Peschardière · Malvin Noël · Olivia Gallego Toscano :contentReference[oaicite:6]{index=6}

## Disclaimer
Educational project. Not for clinical use.
