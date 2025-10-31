# PankBase RUV-Normalized Pseudo-Bulk Counts (UMAP v3.3)

## Overview

This dataset contains **RUV-normalized pseudo-bulk gene expression counts** for six major pancreatic cell types, derived from the PankBase single-cell RNA-seq browser version 3.3. These processed counts are optimized for differential expression analysis and downstream statistical modeling.

## Dataset Information

- **Source**: PankBase Consortium Single Cell RNA-seq Browser v3.3
- **Award**: U24DK138512-DK138515
- **Lab**: pankbase-consortium
- **Input File Set**: PKBDS1349YHGQ
- **Processing Method**: Pseudobulk aggregation with RUV (Remove Unwanted Variation) normalization

## Pipeline : https://github.com/PanKbase/PanKbase-DEG-analysis/blob/main/1_pseudobulk_counts.R.ipynb
## Cell Types Included

This release includes normalized counts for the following pancreatic cell types:

### Metadata Contents

| ID | Award | Lab | Description | Files |
|----|-------|-----|-------------|-------|
| PKBDS3483TGEQ | U24DK138512-DK138515 | pankbase-consortium | RUV-normalized pseudo-bulk counts for differential expression analysis of pancreatic stellate cell derived from cells in the single cell RNA-seq browser v3.3 | ActiveStellate_k-chosen_fdr0.05_all.txt, ActiveStellate_ruvNormCounts.txt |
| PKBDS8497JAAX | U24DK138512-DK138515 | pankbase-consortium | RUV-normalized pseudo-bulk counts for differential expression analysis of pancreatic ductal cell derived from cells in the single cell RNA-seq browser v3.3 | Ductal_k-chosen_fdr0.05_all.txt, Ductal_ruvNormCounts.txt |
| PKBDS6610NSWK | U24DK138512-DK138515 | pankbase-consortium | RUV-normalized pseudo-bulk counts for differential expression analysis of pancreatic acinar cell derived from cells in the single cell RNA-seq browser v3.3 | Acinar_k-chosen_fdr0.05_all.txt, Acinar_ruvNormCounts.txt |
| PKBDS5505XMWS | U24DK138512-DK138515 | pankbase-consortium | RUV-normalized pseudo-bulk counts for differential expression analysis of pancreatic D cell derived from cells in the single cell RNA-seq browser v3.3 | Delta_k-chosen_fdr0.05_all.txt, Delta_ruvNormCounts.txt |
| PKBDS3519RAFX | U24DK138512-DK138515 | pankbase-consortium | RUV-normalized pseudo-bulk counts for differential expression analysis of type B pancreatic cell derived from cells in the single cell RNA-seq browser v3.3 | Beta_k-chosen_fdr0.05_all.txt, Beta_ruvNormCounts.txt |
| PKBDS9343POSP | U24DK138512-DK138515 | pankbase-consortium | RUV-normalized pseudo-bulk counts for differential expression analysis of pancreatic A cell derived from cells in the single cell RNA-seq browser v3.3 | Alpha_k-chosen_fdr0.05_all.txt, Alpha_ruvNormCounts.txt |



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

## Contact & Support

For questions, issues, or additional information:
- Visit: [PankBase Portal](https://pankbase.org)
- Award: U24DK138512-DK138515
- email: help@pankbase.org

## Version History

- **v3.3**: Current release
  - Six pancreatic cell types
  - RUV normalization applied

## License

Please refer to PankBase data use policies for licensing and terms of use.

---

**Last Updated**: October 2025  
**Dataset Version**: UMAP 3.3  
**File Set Type**: Principal Analysis
