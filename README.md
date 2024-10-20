# 🧬 MPXV-2022 BioMarker Identifier

**🔍 A Comprehensive Transcriptomic Network Analysis and Machine Learning Approach to Identify Potential Biomarkers for 2022 Monkeypox Virus Infection**

---

## 📝 Introduction

The **MPXV-2022 BioMarker Identifier** project leverages cutting-edge **bioinformatics** and **machine learning** to explore **microarray** and **RNA-Seq** data. The aim is to identify differentially expressed genes (DEGs) that can serve as potential biomarkers for the **2022 Monkeypox virus (MPXV)** infection.

---

## 🔄 Workflow Overview

### 📊 1. Data Extraction & Normalization

- **Source**: Data was collected from **NCBI's Gene Expression Omnibus (GEO)** using keywords like **Monkeypox**, **MPXV**, and **Mpox**.
- **Selection Criteria**: 
  - Samples with high relevance to the study were prioritized.
  - Rigorous quality checks were applied to ensure robustness.
  
- **Tools Used**: 
  - `limma` v3.54.2 for microarray normalization.
  - `DESeq2` v1.38.3 for RNA-Seq normalization.
  - Processed using **R v4.3.3**.

---

### 🔬 2. Differential Gene Expression (DEG) Analysis

- **Tools for Microarray & RNA-Seq Analysis**: 
  - `limma` for microarray.
  - `DESeq2` and `lfcShrink` for RNA-Seq.
  - **VennDiagram** v1.7.3 to identify intersecting DEGs across conditions.

---

### 🧬 3. Functional Enrichment Analysis

- **Functional Annotation**:
  - **DAVID v6.8** for comprehensive gene annotation.
  - **GOplot** v1.0.2 for visualizing **Gene Ontology (GO)** terms.
  - **Cytoscape** v3.10.1 with **ClueGO** v2.5.10 and **CluePedia** v1.5.10 for pathway analysis.

---

### 🧩 4. Protein-Protein Interaction (PPI) Network

- **PPI Network Construction**:
  - **STRING** v12.0 for visualizing interactions between proteins.
  - **MCODE** v2.0.2 for detecting highly connected gene clusters.
  - **cytoHubba** v0.1 for identifying hub genes critical to the network.

---

### 📈 5. Gene Set Enrichment Analysis (GSEA)

- **Pathway Identification**:
  - **GSEA v4.3.2** with **Hallmark Gene Sets** to identify significant pathways activated during MPXV infection.

---

### 💊 6. Drug Target Prediction

- **Drug Target Identification**:
  - Using **DSigDB** in **Enrichr** to identify candidate drugs targeting hub genes.
  - Visualized using **ggplot2** v3.5.1.

---

## 🚀 Machine Learning Model Selection, Dimensionality Reduction, and Evaluation

### 🔑 Key Steps:

- **Feature Selection**:
  - DEGs were cross-referenced with hub genes and cluster genes for machine learning analysis.
  
- **Model Training**:
  - **PyCaret** v3.3.2 was used to streamline the end-to-end process of model building.
  - Dependencies: `Pandas`, `SciPy`, `Joblib`, `Scikit-Learn`, `Sktime`, `Pmdarima`.

- **Process**:
  - Data was split into **80% training** (19 samples) and **20% testing** (5 samples).
  - A **10-fold cross-validation** was applied during model training.
  - PyCaret’s **compare_models()** function was used to evaluate various classifiers like:
    - **Random Forest (RF)**
    - **Logistic Regression (LR)**
    - **Extra Trees (ET)**
    - **SVM**, **Ada Boost (ADA)**
    - **Quadratic Discriminant Analysis (QDA)**
    - **K Neighbors Classifier (KN)**
    - **Extreme Gradient Boosting (XGBoost)**
    - **Light Gradient Boosting Machine (LightGBM)**

- **Best Model**:
  - The **Random Forest (RF)** classifier emerged as the best-performing model, with metrics including **accuracy**, **AUC**, **recall**, **precision**, and **F1 score**.

- **Dimensionality Reduction**:
  - **t-SNE** (using **Rtsne** v0.17) and **PCA** were applied to visualize clustering of the DEGs.

- **Evaluation**:
  - **ROC analysis** was performed using **pROC** v1.18.5 and **randomForest** v4.7.1.1.

---

## ⚙️ Running the Analysis

### 🔍 **ML_model Folder**

1. **Run Python and R Scripts for Machine Learning**:
   - **Python script** (`1_pycrate.py`):
     ```bash
     python 1_pycrate.py
     ```
   - **Jupyter Notebook** (`1_Pycrate.ipynb`):
     - Open and run cells in a Jupyter environment.
   - **R Scripts** for **PCA**, **t-SNE**, and **ROC**:
     ```bash
     Rscript 2_tSNE.R
     Rscript 3_PCA.R
     Rscript 4_pROC.R
     ```

---

### 🧪 **Microarray Folder**

1. **Run R Scripts for Microarray Data Analysis**:
   - **Required Packages**: `affy`, `limma`, `GEOquery`, `ggplot2`
   - **Run**:
     ```bash
     Rscript 1_Expression_MicroArray.R
     Rscript 2_UmapPlot_MicroArray.R
     Rscript 3_TopTable_MicroArray.R
     Rscript 5_DEGs_Identification_MicroArray.R
     ```

---

### 🧬 **RNA_Seq Folder**

1. **Run R Scripts for RNA-Seq Data Analysis**:
   - **Required Packages**: `DESeq2`, `ggplot2`, `data.table`, `tidyverse`
   - **Run**:
     ```bash
     Rscript 1_install_packages.R
     Rscript 2_load_data.R
     Rscript 3_PCA.R
     Rscript 4_DGE_Normalization.R
     Rscript 5_DGE_LFC.R
     Rscript 6_volcano.R
     ```

---

## 📦 Dependencies

### **R Packages**:
- `limma` v3.54.2
- `DESeq2` v1.38.3
- `lfcShrink`
- `VennDiagram` v1.7.3
- `GOplot` v1.0.2
- `corrplot` v0.92
- `TBtools-II` v2.097
- `Rtsne` v0.17
- `pROC` v1.18.5
- `randomForest` v4.7.1.1
- `GEOquery`
- `ggplot2` v3.5.1

### **Python Libraries**:
- `PyCaret` v3.3.2
- `Pandas` v2.1.4
- `SciPy` v1.11.4
- `Joblib` v1.3.2
- `Scikit-Learn` v1.4.2
- `Sktime` v0.26.0
- `Pmdarima` v2.0.4
- `XGBoost`
- `LightGBM`

---

## 📞 Contact

For inquiries or potential collaborations, reach out to the **MPXV-2022 BioMarker Identifier Team**.

---

## 🔗 Citation

If this tool is used in your research, please cite:
**MPXV-2022 BioMarker Identifier Team**. *Identification of Potential Biomarkers for 2022 Mpox Virus Infection: A Transcriptomic Network Analysis and Machine Learning Approach*. (2024).
