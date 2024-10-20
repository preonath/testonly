# MPXV-2022 BioMarker Identifier

**A comprehensive Transcriptomic Network Analysis and Machine Learning Approach to Identify Potential Biomarkers for 2022 Monkeypox Virus Infection.**

## Introduction
The **MPXV-2022 BioMarker Identifier** project utilizes sophisticated approaches to analyze microarray and RNA-Seq data. This tool is engineered to discover differentially expressed genes (DEGs) and validate these as potential biomarkers for the 2022 Monkeypox virus infection using advanced machine learning techniques.

## Workflow

### Data Extraction
- **Sources**: NCBI Gene Expression Omnibus (GEO).
- **Selection Criteria**: Samples and conditions are selected based on stringent predefined criteria to ensure relevance and quality.

### Data Preprocessing
- **Normalization**: Standard normalization procedures are applied to ensure comparability across samples.
- **Outlier Detection**: Identification and removal of outliers to ensure the quality of the data analysis.

### Differential Expression Analysis
- **Microarray Data**:
  - **Tool**: `limma` (R package).
  - **Scripts**: `1_Expression_MicroArray.R`, `5_DEGs_Identification_MicroArray.R`.
- **RNA-Seq Data**:
  - **Tool**: `DESeq2` (R package).
  - **Scripts**: `1_install_packages.R`, `5_DGE_LFC.R`.
- **Visualization**:
  - **Volcano Plots**: `6_VolcanoPlot_MicroArray.R`, `6_volcano.R`.

### Machine Learning Validation
- **Feature Selection**:
  - **Tool**: PyCaret (Python package).
  - **Script**: `1_pycrate.py`, `1_Pycrate.ipynb`.
  - **Feature Visualization**: PCA and t-SNE plots from `3_PCA.R`, `2_tSNE.R`.
- **Model Evaluation**:
  - **Tool**: ROC curve analysis.
  - **Script**: `4_pROC.R`.
- **Biomarker Discovery**:
  - **Outcome**: Six key biomarkers linked to MPXV infection identified.
  - **Validation**: Validation through robust machine learning models.

## Running the Analysis

### ML_model Folder
1. **Running Python and R Scripts for Machine Learning Analysis**
   - Python script (`1_pycrate.py`):
     - Required Packages: `pandas`, `numpy`, `matplotlib`, `seaborn`, `pycaret`
     ```bash
     python 1_pycrate.py
     ```
   - Jupyter Notebook (`1_Pycrate.ipynb`):
     - Open and run cells in a Jupyter environment.
   - R scripts for PCA, t-SNE, and ROC:
     ```bash
     Rscript 2_tSNE.R
     Rscript 3_PCA.R
     Rscript 4_pROC.R
     ```

### Microarray Folder
1. **Running R Scripts for Microarray Data Analysis**
   - **Expression Analysis and Preprocessing**:
     - Required Packages: `affy`, `limma`, `GEOquery`, `ggplot2`
     ```bash
     Rscript 1_Expression_MicroArray.R
     ```
   - **Dimension Reduction and Visualization**:
     - Required Package: `umap`, `ggplot2`
     ```bash
     Rscript 2_UmapPlot_MicroArray.R
     ```
   - **Statistical Analysis and Reporting**:
     ```bash
     Rscript 3_TopTable_MicroArray.R
     Rscript 5_DEGs_Identification_MicroArray.R
     ```
   - **Data Visualization**:
     ```bash
     Rscript 4_Boxplot_Histogram_MicroArray.R
     Rscript 4_Histogram_MicroArray.R
     Rscript 6_VolcanoPlot_MicroArray.R
     ```

### RNA_Seq Folder
1. **Running R Scripts for RNA-Seq Data Analysis**
   - **Package Installation**:
     - Required Packages: `DESeq2`, `ggplot2`, `data.table`, `tidyverse`
     ```bash
     Rscript 1_install_packages.R
     ```
   - **Data Loading and Preprocessing**:
     ```bash
     Rscript 2_load_data.R
     ```
   - **Exploratory Data Analysis**:
     ```bash
     Rscript 3_PCA.R
     ```
   - **Normalization and Differential Expression Analysis**:
     ```bash
     Rscript 4_DGE_Normalization.R
     Rscript 5_DGE_LFC.R
     ```
   - **Result Visualization**:
     ```bash
     Rscript 6_volcano.R
     ```

## Legacy Support

### Python 2.7 Version
The MPXV-2022 BioMarker Identifier is no longer maintained on Python 2.7. If you have no other option than working with Python 2.7, please download the original codes (release: Original MPXV-2022 codes, v1_beta), and replace the genotype and mutation definition files with the current ones. The script should still work. In case of failure, please let us know.

### R Version 3.5 Compatibility
Support for R version 3.5 has been phased out. If required, users should attempt to run earlier versions of the scripts compatible with R 3.5, but full functionality cannot be guaranteed. Updates and support are provided only for the latest versions of R.

## Dependencies
Ensure all dependencies are installed:
- R packages: `limma`, `DESeq2`, `ggplot2`, `affy`, `umap`, `data.table`, `tidyverse`
- Python packages: `PyCaret`, `numpy`, `pandas`, `matplotlib`, `seaborn`

## Setup
Follow the setup instructions provided in the separate setup documentation to prepare your analysis environment.

## Usage
For detailed usage instructions, refer to the headers in each script which outline command-line arguments, inputs, and outputs.

## Contact
For further inquiries or potential collaborations, please contact:


## Citation
Please cite this tool as follows if utilized in your research:
- MPXV-2022 BioMarker Identifier Team. "Identification of Potential Biomarkers for 2022 Mpox Virus Infection: A Transcriptomic Network Analysis and Machine Learning Approach." (2024).
