# snATAC-seq Dataset Files

## Overview

This dataset contains peak counts and chromatin accessibility data from single-nucleus ATAC-seq (snATAC-seq) analysis of pancreatic cell types. The data includes both cell type-specific peak counts and unified peak calls across all cell types.

## File Structure

### Data Files

Each cell type has two associated count files:

- **`*_sample_counts.txt`**: Raw peak counts per sample
- **`*_sample_CPM.txt`**: Counts per million (CPM) normalized peak counts

### Peak Definition File

- **`HPAPUnionPeaks.mod.bed`**: Unified peak calls across all pancreatic cell types (BED format)

### Cell Types and Files

| Cell Type | Files |
|-----------|-------|
| **Acinar** | `Acinar_sample_counts.txt`<br>`Acinar_sample_CPM.txt` |
| **Alpha** | `Alpha_sample_counts.txt`<br>`Alpha_sample_CPM.txt` |
| **Beta** | `Beta_sample_counts.txt`<br>`Beta_sample_CPM.txt` |
| **Delta** | `Delta_sample_counts.txt`<br>`Delta_sample_CPM.txt` |
| **Gamma** | `Gamma_sample_counts.txt`<br>`Gamma_sample_CPM.txt` |
| **Ductal** | `Ductal_sample_counts.txt`<br>`Ductal_sample_CPM.txt` |
| **MUC5B+ Ductal** | `MUC5B_Ductal_sample_counts.txt`<br>`MUC5B_Ductal_sample_CPM.txt` |
| **Activated Stellate** | `A_Stellate_sample_counts.txt`<br>`A_Stellate_sample_CPM.txt` |
| **Quiescent Stellate** | `Q_Stellate_sample_counts.txt`<br>`Q_Stellate_sample_CPM.txt` |
| **Endothelial** | `Endothelial_sample_counts.txt`<br>`Endothelial_sample_CPM.txt` |
| **Immune** | `Immune_sample_counts.txt`<br>`Immune_sample_CPM.txt` |
| **Schwann** | `Schwann_sample_counts.txt`<br>`Schwann_sample_CPM.txt` |

## Metadata

The `metadata.tsv` file contains detailed information about each dataset:

| Column | Description |
|--------|-------------|
| **ID** | Unique dataset identifier (PKBDS format) |
| **Award** | Grant award number |
| **Description** | Detailed description of the dataset and cell type |
| **Lab** | Contributing laboratory |
| **Files** | Associated data files for the dataset |

### Metadata Contents

| ID | Award | Description | Lab | Files |
|----|-------|-------------|-----|-------|
| PKBDS9687AMNO | R01-DK114650-01A1 | Unified peaks of islet cell type-specific chromatin accessibility from 97,659 cells derived from single cell ATAC-seq assays of 41 non-diabetic;T1D autoantibody positive (Aab+);T1D;and T2D donors from the Human Pancreas Analysis Program | kyle-gaulton | HPAPUnionPeaks.mod.bed |
| PKBDS4758SLXG | U24DK138512-DK138515 | Peak counts for pancreatic acinar cells from snATAC-seq | pankbase-consortium | Acinar_sample_counts.txt, Acinar_sample_CPM.txt |
| PKBDS5528RBHE | U24DK138512-DK138515 | Peak counts for pancreatic delta cells from snATAC-seq | pankbase-consortium | Delta_sample_counts.txt, Delta_sample_CPM.txt |
| PKBDS0206SBJF | U24DK138512-DK138515 | Peak counts for pancreatic ductal cells from snATAC-seq | pankbase-consortium | Ductal_sample_counts.txt, Ductal_sample_CPM.txt |
| PKBDS3521REWK | U24DK138512-DK138515 | Peak counts for pancreatic beta cells from snATAC-seq | pankbase-consortium | Beta_sample_counts.txt, Beta_sample_CPM.txt |
| PKBDS4115VWFM | U24DK138512-DK138515 | Peak counts for pancreatic schwann cells from snATAC-seq | pankbase-consortium | Schwann_sample_counts.txt, Schwann_sample_CPM.txt |
| PKBDS5249JJKD | U24DK138512-DK138515 | Peak counts for pancreatic alpha cells from snATAC-seq | pankbase-consortium | Alpha_sample_counts.txt, Alpha_sample_CPM.txt |
| PKBDS8469RQOO | U24DK138512-DK138515 | Peak counts for pancreatic endothelial cells from snATAC-seq | pankbase-consortium | Endothelial_sample_counts.txt, Endothelial_sample_CPM.txt |
| PKBDS1840SOPT | U24DK138512-DK138515 | Peak counts for pancreatic activated stellate cells from snATAC-seq | pankbase-consortium | A_Stellate_sample_counts.txt, A_Stellate_sample_CPM.txt |
| PKBDS7254MJJN | U24DK138512-DK138515 | Peak counts for pancreatic quiescent stellate cells from snATAC-seq | pankbase-consortium | Q_Stellate_sample_counts.txt, Q_Stellate_sample_CPM.txt |
| PKBDS3504VMPS | U24DK138512-DK138515 | Peak counts for pancreatic gamma cells from snATAC-seq | pankbase-consortium | Gamma_sample_counts.txt, Gamma_sample_CPM.txt |
| PKBDS8988YQBZ | U24DK138512-DK138515 | Peak calls unified across all pancreatic cell types from snATAC-seq | pankbase-consortium | HPAPUnionPeaks.mod.bed |
| PKBDS3568VOEM | U24DK138512-DK138515 | Peak counts for pancreatic MUC5b+ ductal cells from snATAC-seq | pankbase-consortium | MUC5B_Ductal_sample_counts.txt, MUC5B_Ductal_sample_CPM.txt |
| PKBDS7691LOBY | U24DK138512-DK138515 | Peak counts for pancreatic immune cells from snATAC-seq | pankbase-consortium | Immune_sample_counts.txt, Immune_sample_CPM.txt |

## Usage

To access a specific cell type's chromatin accessibility data:

1. Identify the cell type of interest from the table above
2. Use the corresponding files:
   - `*_sample_counts.txt` for raw peak counts
   - `*_sample_CPM.txt` for normalized peak counts
3. Reference `HPAPUnionPeaks.mod.bed` for the unified peak definitions across all cell types

## Data Source

This snATAC-seq dataset includes:
- Cell type-specific chromatin accessibility profiles
- Data from the Human Pancreas Analysis Program (HPAP)
- Analysis of 97,659 cells from 41 donors including non-diabetic, T1D autoantibody positive, T1D, and T2D samples

## Citation
