Welcome to the GitHub repository for the following publication: Genome-scale quantification and prediction of drug-induced readthrough of pathogenic premature termination codons (Toledano I, Supek F & Lehner B, 2023)

Here you'll find source code for computational analyses and to reproduce the figures in the paper.

# Table Of Contents

* **1. [Required Software](#required-software)**
* **2. [Required Data](#required-data)**
* **3. [Installation Instructions](#installation-instructions)**
* **4. [Usage](#usage)**

# Required Software

To run the Stop_codon_readthrough pipeline you will need the following software and associated packages:

* **[_R_](https://www.r-project.org/)** (dplyr, stringr, stringi, GGally, ggpubr, ggplot2, viridis, tidyverse, seqinr, matrixStats, data.table, rtracklayer, openxlsx, reshape2, caret, hexbin, png, grid, gridExtra, MuMIn, tidyr, rstatix, ggridges, hrbrthemes, glmnet, spgs)

# Required Data

Read counts (Dimsum output), readthrough efficiencies, and required miscellaneous files should be downloaded from **[here](https://crgcnag-my.sharepoint.com/:f:/g/personal/itoledano_crg_es/Eszq0KwHEq5Lt-NNghiRmzIBtL_MdXLKtIitmotN8VWoaQ?e=CLSl2m)** to your project directory (named 'base_dir') i.e. where output files should be written.

# Installation Instructions

Make sure you have git and conda installed and then run (expected install time <10min):

```
# Install dependencies (preferably in a fresh conda environment)
conda install -c conda-forge r-dplyr, r-stringr, r-stringi, r-GGally, r-ggpubr, r-ggplot2, r-viridis, r-tidyverse, r-seqinr, r-matrixStats, r-data.table, r-rtracklayer, r-openxlsx, r-reshape2, r-caret, r-hexbin, r-png, r-grid, r-gridExtra, r-MuMIn, r-tidyr, r-rstatix, r-ggridges, r-hrbrthemes, r-glmnet, r-spgs

# Open an R session

```

# Usage

The 8 Rmarkdown files contain the code to reproduce the figures and results from the computational analyses described in the following publication: [Genome-scale quantification and prediction of drug-induced readthrough of pathogenic premature termination codons (Toledano I, Supek F &amp; Lehner B, 2023)]. See [Required Data](#required-data) for instructions on how to obtain all required data and miscellaneous files before running the pipeline. If using/downloading the files from [Required Data](#required-data) and only plotting the figures, the Expected run time <10min. However, if generating all the files (i.e. the in silico PTC saturation dataset of the human genome) and models needed for all main and supplementary figures, the expected run time is ~2days. All steps in which the user can decide whether to generate the file/model or to download it from [Required Data](#required-data) are indicated.
Rmarkdown files are meant to be run in the following order:

* **1. Dimsum.Rmd**
* **2. Generate_treated_samples.Rmd**
* **3. Fig1_extdataFig1.Rmd**
* **4. Fig2_extdataFig2.Rmd**
* **5. Fig3_extdataFig3.Rmd**
* **6. Fig4_extdataFig4.Rmd**
* **7. Fig5.Rmd**
* **8. Fig6_extdatafig5.Rmd**


# Additional scripts and software

The following software package is required for pre-processing of raw FASTQ files:

* **[DiMSum](https://github.com/lehner-lab/DiMSum) v1.2.9** (pipeline for pre-processing deep mutational scanning data i.e. FASTQ to fitness)

Configuration files and additional scripts for running DiMSum and MoCHI are available in the "DiMSum" folder **[here](https://crgcnag-my.sharepoint.com/:f:/g/personal/cweng_crg_es/EliX349TTkpIoMomBwphyRMBYI17nEt4XZ45XcTvWtpuyw)**.
