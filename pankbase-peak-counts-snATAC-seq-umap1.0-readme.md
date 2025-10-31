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
If you use this dataset in your research, please cite:

```
; RRID:SCR_016202; PMID: 31127054; PMID: 36206763). HPAP is part of a Human Islet Research Network (RRID:SCR_014393) consortium (UC4-DK112217, U01-DK123594, UC4-DK112232, and U01-DK123716). If scRNA-seq data is used, please also cite PMID: 35228745 and PMID: 37188822.

nPOD

The Network for Pancreatic Organ donors with Diabetes (nPOD; RRID:SCR_014641) is a collaborative type 1 diabetes research project supported by grants from Breakthrough T1D/ The Leona M. & Harry B. Helmsley Charitable Trust (3-SRA-2023-1417-S-B) and the Helmsley Charitable Trust (2018PG-T1D053, G-2108-04793). Results and interpretation of analyses that include nPOD data are the responsibility of the authors and do not necessarily reflect the official view of nPOD. Organ Procurement Organizations (OPO) partnering with nPOD to provide research resources are listed at https://npod.org/for-partners/npod-partners/.

Additional information about how to identify nPOD samples in your work and other relevant guidelines can be found at the nPOD website (https://npod.org/publications/policies/).

ADI

Human islets for research were provided by the Alberta Diabetes Institute IsletCore at the University of Alberta in Edmonton (http://www.bcell.org/adi-isletcore.html) with the assistance of the Human Organ Procurement and Exchange (HOPE) program, Trillium Gift of Life Network (TGLN), and other Canadian organ procurement organizations. Islet isolation was approved by the Human Research Ethics Board at the University of Alberta (Pro00013094). All donors' families gave informed consent for the use of pancreatic tissue in research.

This work includes data and/or analyses from HumanIslets.com funded by the Canadian Institutes of Health Research, JDRF Canada, and Diabetes Canada (5-SRA-2021-1149-S-B/TG 179092) with data from islets isolated by the Alberta Diabetes Institute IsletCore with the support of the Human Organ Procurement and Exchange program, Trillium Gift of Life Network, BC Transplant, Quebec Transplant, and other Canadian organ procurement organizations with written informed donor consent as approved by the Human Research Ethics Board at the University of Alberta (Pro00013094).

ADI HumanIslets.com web tool

    Ewald et al. (2024) HumanIslets.com: Improving accessibility, integration, and usability of human research islet data. Cell Metab. 2025 Jan 7;37(1):7-11. doi: 10.1016/j.cmet.2024.09.001. Epub 2024 Oct 1. PMID: 39357523.

ADI Proteomic data and RNAseq

    Kolic et al. (2024) Proteomic predictors of individualized nutrient-specific insulin secretion in health and disease. Cell Metabolism, Volume 36, Issue 7, 1619-1633.e5

ADI Patch-seq

    Dai et al. (2022) Heterogenous impairment of α cell function in type 2 diabetes is linked to cell maturation state. Cell Metabolism, 34(2):256-268.e5. doi: 10.1016/j.cmet.2021.12.021.
        Camunas-Soler et al. (2020) Patch-seq links single-cell transcriptomes to human islet dysfunction in diabetes. Cell Metabolism, 31(5):1017-1031.e4. doi: 10.1016/j.cmet.2020.04.005.

ADI Omics analysis results

    Robinson et al. (2009) edgeR: a Bioconductor package for differential expression analysis of digital gene expression data. Bioinformatics, 26(1):139-140. doi: doi.org/10.1093/bioinformatics/btp616

ADI Missing value imputation (processed proteomics data)

    Stekhoven et al. (2012) MissForest—non-parametric missing value imputation for mixed-type data, Bioinformatics, 28(1):112-118. doi: 10.1093/bioinformatics/btr597

ADI Batch correction (processed bulk RNAseq and Nanostring)

    Leek et al. (2012) The sva package for removing batch effects and other unwanted variation in high-throughput experiments, Bioinformatics, 28(6):882-883. doi: 10.1093/bioinformatics/bts034

ADI Pathway analysis libraries

    Gillespie et al. (2022) The reactome pathway knowledgebase 2022, Nucleic Acids Research, 50(D1): D687–D692, doi.org/10.1093/nar/gkab1028
        Kanehisa et al. (2023) KEGG for taxonomy-based analysis of pathways and genomes. Nucleic Acids Research, 51(D1): D587-D592, doi.org/10.1093/nar/gkac963
	    The Gene Ontology Consortium. (2023) The Gene Ontology knowledgebase in 2023 Genetics, 224(1):iyad031. doi: 10.1093/genetics/iyad031

IIDP

Acknowledgement and citation of IIDP as the source of resources and information, including any islets, tissue, slides, data, or images from the IIDP or any of their network webpages. Some experimental results were derived from human pancreatic islets and/or other resources provided by the NIDDK-funded Integrated Islet Distribution Program (IIDP) (RRID:SCR_014387) at City of Hope, NIH Grant # 2UC4DK098085.

An RRID for each isolation is obtained by the Islet Isolation Center when a pancreas becomes available for broadcast. The RRID replaces the UNOS ID and must be reported instead of the UNOS ID so that the donor’s identity remains confidential. The ancillary tissues, such as duodenum, blood, spleen, histology slides also will have an RRID. The RRIDs associated with each donor are linked to each other within the IIDP Research Data Repository.

Pancreatlas

Please include the URL (https://www.pancreatlas.org) and RRID (RRID:SCR_018567) or reference our manuscript: Saunders, D. C. et al. Pancreatlas: Applying an Adaptable Framework to Map the Human Pancreas in Health and Disease. Patterns 1(8), 100120 (2020). DOI: 10.1016/j.patter.2020.100120.
```
