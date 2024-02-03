Welcome to the GitHub repository for the following publication: Genome-scale quantification and prediction of drug-induced readthrough of pathogenic premature termination codons (Toledano I, Supek F & Lehner B, 2023)

Here you'll find source code for computational analyses and to reproduce the figures in the paper.

# Table Of Contents

* **1. [Required Software](#required-software)**
* **2. [Required Data](#required-data)**
* **3. [Installation Instructions](#installation-instructions)**
* **4. [Usage](#usage)**

# Required Software

To run the Stop_codon_readthrough pipeline you will need the following software and associated packages:

* **[_R_](https://www.r-project.org/)** (dplyr, stringr, stringi, GGally, ggpubr, ggplot2, viridis, tidyverse, seqinr, matrixStats, data.table, rtracklayer, openxlsx, reshape2, caret, hexbin, png, grid, gridExtra, MuMIn, tidyr, rstatix, ggridges, hrbrthemes, glmnet, spgs, ggtext, devtools, ggdendroplot, UpSetR)

# Required Data

Read counts (DiMSum output), readthrough efficiencies, and required miscellaneous files should be downloaded from **[Main dataset and other files](https://figshare.com/articles/dataset/Other_objects/25138712)**, **[Fig.1](https://figshare.com/articles/dataset/Fig_1_Files/25138625)**, **[Fig.2](https://figshare.com/articles/dataset/Fig_2_files/25138685)**, **[Fig.3](https://figshare.com/articles/dataset/Fig_3_Files/25138688)**, **[Fig.4](https://figshare.com/articles/dataset/Fig_4_Files/25138691)**, **[Fig.5](https://figshare.com/articles/dataset/Fig_5_Files/25138697)** and **[Fig.6](https://figshare.com/articles/dataset/Fig_6_Files/25139210)** to your project directory (named 'base_dir') i.e. where output files should be written.

# Installation Instructions

Make sure you have git and conda installed and then run (expected install time <10min):

```
# Install dependencies (preferably in a fresh conda environment)
conda install -c conda-forge r-dplyr, r-stringr, r-stringi, r-ggally r-ggpubr r-ggplot2 r-viridis r-tidyverse r-seqinr r-matrixstats r-data.table r-openxlsx r-reshape2 r-caret r-hexbin r-png r-gridextra r-mumin r-tidyr r-rstatix r-ggridges r-hrbrthemes r-glmnet r-spgs r-ggtext r-devtools r-UpSetR r-biocmanager
conda install -c bioconda bioconductor-biomart
conda install -c bioconda bioconductor-rtracklayer
conda install conda-forge::r-gridgraphics
```
Alternatively load the 'RT_diseasePTCs.yml' which contains the conda environment already generated.

# Usage

The 7 R Markdown files contain the code to reproduce the figures and results from the computational analyses described in the following publication: Genome-scale quantification and prediction of drug-induced readthrough of pathogenic premature termination codons (Toledano I, Supek F & Lehner B, 2023). See [Required Data](#required-data) for instructions on how to obtain all required data and miscellaneous files before running the pipeline. If using/downloading the files from [Required Data](#required-data) and only plotting the figures, the expected run time is <10min. However, if generating all the files (i.e. the in silico PTC saturation dataset of the human genome) and models needed for all main and supplementary figures, the expected run time is ~2days (without data parallelisation). All steps in which the user can decide whether to generate the file/model or to download it from [Required Data](#required-data) are indicated.
R Markdown files are meant to be run in the following order:

* **1. Generate_treated_samples.Rmd**
* **2. Fig1_extdataFig1.Rmd**
* **3. Fig2_extdataFig2.Rmd**
* **4. Fig3_extdataFig3.Rmd**
* **5. Fig4_extdataFig4.Rmd**
* **6. Fig5.Rmd**
* **7. Fig6_extdatafig5.Rmd**

# Additional scripts and software

The following software package is required for pre-processing of raw FASTQ files:

* **[DiMSum](https://github.com/lehner-lab/DiMSum) v1.2.9** (pipeline for pre-processing deep mutational scanning data i.e. FASTQ to fitness). Download the FastQ files from Sequence Read Archive (SRA) with accession number PRJNA996618: http://www.ncbi.nlm.nih.gov/bioproject/996618 to your base directory (base_dir). Store the Clitocine, DAP and SRI FastQ files in a separate folder (named 'round_A_fastq') than CC90009, FUr, Gentamicin, G418, SJ6986 and untreated conditions (folder named 'round_B_fastq'). That is because they were assayed in two different rounds (named 'A' and 'B') and we did a separate Dimsum run for each. Shell scripts to run both Dimsum rounds can be found in [Required Data](#required-data).
  
Configuration files and additional scripts for running DiMSum are available in the "DiMSum" folder **[here](https://crgcnag-my.sharepoint.com/:f:/g/personal/itoledano_crg_es/Eszq0KwHEq5Lt-NNghiRmzIBtL_MdXLKtIitmotN8VWoaQ?e=CLSl2m)**.
