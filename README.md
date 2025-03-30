##  Project Overview
Short summary of what you're doing (e.g., comparing DNN vs XGBoost for cell type classification from scRNA-seq data)

## Workflow Summary
1. Data Selection  
2. Preprocessing 
3. Data Reduction 
4. Data Splitting  
5. Model Training (DNN, XGBoost)  
6. Evaluation & Metrics  
7. Result Comparison  
8. Visualization & Reporting


This project compares **deep learning (DNN)** and **XGBoost** models for classifying cell types using **single-cell RNA sequencing (scRNA-seq)** data. We evaluate model performance on datasets of varying sizes (50K, 60K cells), using three preprocessing strategies:  
- **Raw features**  
- **PCA-reduced features**  
- **Randomly undersampled (RUS) features**

---

## 📊 Project Workflow

### 1. 🔍 Data Selection & Collection
- Selected two large scRNA-seq datasets (50K+ cells each) from the [Cellxgene](https://cellxgene.cziscience.com/) database.
- Chose datasets with a **diverse range of cell types** and **class imbalance** to simulate realistic classification challenges.

### 2.  Data Preprocessing and Reduction
- **Normalization**: Applied log normalization and scaling.
- **Filtering**: Removed low-quality cells with:
  - High mitochondrial gene expression
  - Low gene expression 
- **Annotation**: Annotated cell types for supervised learning.
- **PCA (Principal Component Analysis)** was used to reduce the number of features from thousands of genes to a lower-dimensional representation, capturing the most variance.
- **Random Undersampling (RUS)** was applied to reduce the number of majority class samples, addressing class imbalance while preserving minority cell types.

Each preprocessing strategy (Raw, PCA, RUS) was used to create distinct input datasets for model evaluation.


### 3. Data Splitting
- Split ratio: **80% training** / **20% testing**.

### 4. Model Training
- Trained two types of models:
  - Deep Neural Networks (DNN)
  - XGBoost classifiers
- Each model was trained on all 3 dataset versions (raw, PCA, RUS).

### 5. Evaluation
- Evaluated using:
  - Accuracy
  - F1 Score
  - Confusion Matrix
- Benchmarked computational performance for each model-dataset combination.

### 6. 📈 Results & Visualization
- Performance metrics visualized using matplotlib.
- Appendix figures demonstrate model scalability and resource consumption.

---

## 📁 Repository Structure

```bash
.
├── notebooks/
│   ├── DNN_50K_Raw.ipynb
│   ├── DNN_50K_PCA.ipynb
│   ├── DNN_50K_RUS.ipynb
│   ├── DNN_60K_Raw.ipynb
│   ├── DNN_60K_PCA.ipynb
│   ├── DNN_60K_RUS.ipynb
│   └── XGBoost.ipynb
├── figures/
│   └── appendix_figure_A_1.png
├── README.md
