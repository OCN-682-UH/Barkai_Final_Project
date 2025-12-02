# 🧬 Population Genetic Structure of the Sea Urchin *Tripneustes gratilla*

**Final Project for OCN 682**

---

## Project Overview

This project investigates the global population genetics of the collector urchin, ***Tripneustes gratilla***, across its Indo-Pacific range. The analysis utilizes **222 curated mitochondrial Cytochrome Oxidase I (COI) sequence** submissions obtained from GenBank.

The primary goal was to answer the research question: **Is there genetic population structure in *Tripneustes gratilla* across its sampled Indo-Pacific range?**

The analysis confirms the presence of significant genetic structure. 

---

## Repository Structure

The core project files and data are organized as follows:
├── Data/
│ ├── Cleaned_Tripneustes_CO1_Data.csv # Final curated dataset (222 sequences)
│ ├── Final_Project_Data_Dictionary.csv # Data Dictionary
│ ├── sequence (1).gb # Raw data
│ ├── sequence (2).gb # Raw data
│ ├── sequence (3).gb # Raw data
│ ├── sequence (4).gb # Raw data
│ ├── sequence (5).gb # Raw data
│ └── sequence (6).gb # Raw data
├── Output/
│ ├── structure_plot_simplified_mean_loc.png # Main Structure Plot (Figure 1)
│ └── urchin_map_k3_final.png # Geographic Map of Clusters (Figure 2)
├── Scripts/
│ ├── Final_Project.qmd # Final Quarto document
│ └── Final_Project.html # Final knitted HTML report


---

## Methodology: Discriminant Analysis of Principal Components (DAPC)

The analysis was performed using **R** and packages specialized for genetic data:

* **Data Curation & Alignment:** Raw GenBank data was cleaned, standardized, and sequences were aligned using **ClustalW** (`msa` package).
* **Optimal Clustering ($K$):** The optimal number of genetic clusters was determined to be **$K=3$** based on the Elbow Method (Within Sum of Squares analysis) on the Principal Components Analysis (PCA) scores.
* **DAPC:** **Discriminant Analysis of Principal Components (DAPC)** (from the `adegenet` package) was applied to assign individuals to these three likely genetic clusters.

---

## Key Findings

The DAPC analysis revealed three distinct genetic clusters, strongly supporting the hypothesis of significant population structure.

* **Result:** **Three distinct genetic clusters ($K=3$)** were identified.
* **Interpretation:** The observed structure is mainly due to **major oceanographic barriers** and **isolation by distance** that restrict larval dispersal across the vast species range.

---

### R Libraries Used:

* **Core:** `tidyverse`, `knitr`, `here`, `readr`, `dplyr`
* **Genetic Analysis:** `Biostrings`, `msa`, `ape`, `adegenet`, `ade4`
* **Visualization & Mapping:** `ggplot2`, `ggtext`, `DT`, `htmltools`, `stringr`, `sf`, `rnaturalearth`, `rnaturalearthdata`, `ggrepel`

### How to Reproduce:

1.  Clone this repository: `git clone [Your Repository URL]`
2.  Open the `Final_Project.Rmd` file in **RStudio**.
3.  Ensure all required packages are installed.
4.  Run the chunks sequentially or use the **Knit** button to generate the final report (`Final_Project.html`) and all output figures in the `Output/` folder.

---

**Author:** Leah Barkai
**Date:** December 2, 2025
