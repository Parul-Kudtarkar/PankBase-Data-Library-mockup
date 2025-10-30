# PankBase Single-Cell RNA-seq UMAP v3.3

## Overview

This dataset contains **single-cell RNA-sequencing data** from human pancreatic tissue, processed and visualized using UMAP (Uniform Manifold Approximation and Projection) dimensionality reduction. The dataset includes comprehensive cell-level metadata, log-normalized gene expression counts, and UMAP coordinates for interactive exploration of pancreatic cell heterogeneity across multiple donors and conditions.

This resource enables researchers to explore gene expression patterns at single-cell resolution, identify cell type-specific markers, and investigate diabetes-related changes in pancreatic cells.

## Dataset Information

- **Dataset**: PankBase Single Cell RNA-seq Browser v3.3
- **Release Date**: June 4, 2025 (060425)
- **Award**: U24DK138512-DK138515
- **Lab**: pankbase-consortium
- **Data Sources**: HPAP, nPOD, ADI, IIDP, and other contributing centers
- **Chemistry**: 10X Genomics (V2, V3)
- **Total Cells**: Variable (check metadata.tsv for exact count)

### Files Included

| File Name | Description | Format |
|-----------|-------------|--------|
| `060425_scRNA_v3.3.rds` | Complete Seurat object with processed data | RDS (R) |
| `metadata.tsv` | Cell-level metadata with donor and biosample information | TSV |
| `coordinates.tsv` | UMAP coordinates for each cell | TSV |
| `lognorm_counts.tsv.gz.tsv` | Log-normalized gene expression matrix | TSV (compressed) |

## Data Processing
https://data.pankbase.org/workflows/PKBWF9623SLYX
https://data.pankbase.org/workflows/PKBWF7216YNOL

## Cell Types Included
*Note: Exact cell types present can be determined from the "Cell Type" column in metadata.tsv*

## Metadata Description

The `metadata.tsv` file contains extensive information for each cell, organized into the following categories:

### Cell-Level QC Metrics
- `NAME`: Unique cell identifier (SRA Run ID + Barcode)
- `Cell Type`: Annotated cell type
- `nCount RNA`: Total UMI counts per cell
- `nFeature RNA`: Number of genes detected per cell
- `rna pct mitochondrial`: Percentage of mitochondrial reads

### Sequencing Information
- `samples`: SRA Run ID
- `barcodes`: Cell barcode
- `treatments`: Experimental treatment (e.g., infected_with_SARS-CoV-2)
- `chemistry`: 10X Genomics chemistry version (V2, V3)
- `source`: Data source (HPAP, nPOD, ADI, IIDP)

### Donor Demographics
- `Center Donor IRRID`: Research Resource Identifier for donor
- `Donor Accession`: PankBase donor accession (PKBDO...)
- `Sex`: Donor biological sex
- `Age (years)`: Donor age
- `BMI`: Body Mass Index
- `Reported Ethnicities`: Self-reported ethnicity

### Diabetes-Related Information
- `Diabetes Status`: NA (non-diabetic), T1D, T2D, etc.
- `Diabetes Duration (years)`: Years since diagnosis
- `HbA1C (percentage)`: Hemoglobin A1C levels
- `C Peptide (ng/ml)`: C-peptide levels
- `Family History of Diabetes`: TRUE/FALSE
- `Glucose Lowering Theraphy`: Treatment information

### Autoantibody Data
- `AAB GADA POSITIVE`: Glutamic acid decarboxylase antibody
- `AAB IA2 POSITIVE`: Insulinoma-associated antigen 2 antibody
- `AAB ZNT8 POSITIVE`: Zinc transporter 8 antibody
- `AAB IAA POSITIVE`: Insulin autoantibody
- *Corresponding values (unit/ml) for each antibody*

### Biosample Information
- `Biosample Accession`: PankBase biosample accession (PKBSM...)
- `Biosample Cold Ischaemia Time (hours)`: Time on ice before processing
- `Islet Yield IEQ`: Islet equivalent yield
- `IEQ Pancreas Weight (grams)`: Pancreas weight
- `Isolation Center`: Organization that performed islet isolation
- `Organ Source`: deceased or living
- `Donation Type`: DBD (Donation after Brain Death), DCD, etc.


## Citation

If you use this dataset in your research, please cite:

### HPAP (Human Pancreas Analysis Program)

RRID:SCR_016202; PMID: 31127054; PMID: 36206763. HPAP is part of a Human Islet Research Network (RRID:SCR_014393) consortium (UC4-DK112217, U01-DK123594, UC4-DK112232, and U01-DK123716). If scRNA-seq data is used, please also cite PMID: 35228745 and PMID: 37188822.

### nPOD (Network for Pancreatic Organ donors with Diabetes)

The Network for Pancreatic Organ donors with Diabetes (nPOD; RRID:SCR_014641) is a collaborative type 1 diabetes research project supported by grants from Breakthrough T1D/The Leona M. & Harry B. Helmsley Charitable Trust (3-SRA-2023-1417-S-B) and the Helmsley Charitable Trust (2018PG-T1D053, G-2108-04793). Results and interpretation of analyses that include nPOD data are the responsibility of the authors and do not necessarily reflect the official view of nPOD. Organ Procurement Organizations (OPO) partnering with nPOD to provide research resources are listed at https://npod.org/for-partners/npod-partners/.

Additional information about how to identify nPOD samples in your work and other relevant guidelines can be found at the nPOD website (https://npod.org/publications/policies/).

### ADI (Alberta Diabetes Institute IsletCore)

Human islets for research were provided by the Alberta Diabetes Institute IsletCore at the University of Alberta in Edmonton (http://www.bcell.org/adi-isletcore.html) with the assistance of the Human Organ Procurement and Exchange (HOPE) program, Trillium Gift of Life Network (TGLN), and other Canadian organ procurement organizations. Islet isolation was approved by the Human Research Ethics Board at the University of Alberta (Pro00013094). All donors' families gave informed consent for the use of pancreatic tissue in research.

This work includes data and/or analyses from HumanIslets.com funded by the Canadian Institutes of Health Research, JDRF Canada, and Diabetes Canada (5-SRA-2021-1149-S-B/TG 179092) with data from islets isolated by the Alberta Diabetes Institute IsletCore with the support of the Human Organ Procurement and Exchange program, Trillium Gift of Life Network, BC Transplant, Quebec Transplant, and other Canadian organ procurement organizations with written informed donor consent as approved by the Human Research Ethics Board at the University of Alberta (Pro00013094).

**ADI HumanIslets.com web tool:**
- Ewald et al. (2024) HumanIslets.com: Improving accessibility, integration, and usability of human research islet data. Cell Metab. 2025 Jan 7;37(1):7-11. doi: 10.1016/j.cmet.2024.09.001. PMID: 39357523.

### IIDP (Integrated Islet Distribution Program)

Acknowledgement and citation of IIDP as the source of resources and information, including any islets, tissue, slides, data, or images from the IIDP or any of their network webpages. Some experimental results were derived from human pancreatic islets and/or other resources provided by the NIDDK-funded Integrated Islet Distribution Program (IIDP) (RRID:SCR_014387) at City of Hope, NIH Grant # 2UC4DK098085.

### Pancreatlas

Please include the URL (https://www.pancreatlas.org) and RRID (RRID:SCR_018567) or reference: Saunders, D. C. et al. Pancreatlas: Applying an Adaptable Framework to Map the Human Pancreas in Health and Disease. Patterns 1(8), 100120 (2020). DOI: 10.1016/j.patter.2020.100120.

## Contact & Support

For questions, issues, or additional information:
- **Website**: [PankBase Portal](https://pankbase.org)
- **Award**: U24DK138512-DK138515
- **Email**: help@pankbase.org

## Version History

- **v3.3** (June 4, 2025): Current release
  - Comprehensive single-cell RNA-seq dataset
  - Multiple pancreatic cell types annotated
  - Integrated data from HPAP, nPOD, ADI, IIDP
  - UMAP dimensionality reduction applied
  - Extensive donor and biosample metadata

## License

Please refer to PankBase data use policies for licensing and terms of use. Individual data sources (HPAP, nPOD, ADI, IIDP) may have specific requirements for data usage and publication. Please review the citation requirements above and consult the respective program websites for detailed policies.

---

**Dataset**: pankbase-scrna-umap-v3.3  
**Last Updated**: October 2025  
**Format**: Seurat RDS object + TSV files  
**Data Type**: Single-cell RNA-sequencing%                                                                                                                                                                                                                     parulkudtarkar@FVFDR31YQ6L7 pankbase-scrna-umap-v3.3 % ls
060425_scRNA_v3.3.rds		coordinates.tsv			lognorm_counts.tsv.gz.tsv	metadata.tsv			README.md
parulkudtarkar@FVFDR31YQ6L7 pankbase-scrna-umap-v3.3 % aws s3 cp ../pankbase-scrna-umap-v3.3.zip s3://pankbase-data-v1/download/ . --no-sign-request 

Unknown options: .
parulkudtarkar@FVFDR31YQ6L7 pankbase-scrna-umap-v3.3 % aws s3 cp ../pankbase-scrna-umap-v3.3.zip s3://pankbase-data-v1/download/ --no-sign-request 
upload failed: ../pankbase-scrna-umap-v3.3.zip to s3://pankbase-data-v1/download/pankbase-scrna-umap-v3.3.zip An error occurred (AccessDenied) when calling the CreateMultipartUpload operation: Anonymous users cannot initiate multipart uploads.  Please authenticate.
parulkudtarkar@FVFDR31YQ6L7 pankbase-scrna-umap-v3.3 % cd ..
parulkudtarkar@FVFDR31YQ6L7 Desktop % ls
ALL							lab_meeting.pptx					paper							Screenshot 2025-10-27 at 3.17.50 PM.png
aws_pem							pankbase-ruv-normalized-pseudo-bulk-counts-umap3.3	perseus							test
epigenomebrowser.pem					pankbase-ruv-normalized-pseudo-bulk-counts-umap3.3.zip	pk
files(4).txt						pankbase-scrna-umap-v3.3				react-langchain
images							pankbase-scrna-umap-v3.3.zip				Screenshot 2025-08-12 at 9.24.19 AM.png
parulkudtarkar@FVFDR31YQ6L7 Desktop % rm pankbase-ruv-normalized-pseudo-bulk-counts-umap3.3.zip 
parulkudtarkar@FVFDR31YQ6L7 Desktop % rm pankbase-scrna-umap-v3.3.zip 
parulkudtarkar@FVFDR31YQ6L7 Desktop % time tar -czf pankbase-scrna-umap-v3.3.tar.gz pankbase-scrna-umap-v3.3/
tar -czf pankbase-scrna-umap-v3.3.tar.gz pankbase-scrna-umap-v3.3/  464.10s user 21.82s system 97% cpu 8:18.33 total
parulkudtarkar@FVFDR31YQ6L7 Desktop % cd pankbase-scrna-umap-v3.3 
parulkudtarkar@FVFDR31YQ6L7 pankbase-scrna-umap-v3.3 % cat README.md 
# PankBase Single-Cell RNA-seq UMAP v3.3

## Overview

This dataset contains **single-cell RNA-sequencing data** from human pancreatic tissue, processed and visualized using UMAP (Uniform Manifold Approximation and Projection) dimensionality reduction. The dataset includes comprehensive cell-level metadata, log-normalized gene expression counts, and UMAP coordinates for interactive exploration of pancreatic cell heterogeneity across multiple donors and conditions.

This resource enables researchers to explore gene expression patterns at single-cell resolution, identify cell type-specific markers, and investigate diabetes-related changes in pancreatic cells.

## Dataset Information

- **Dataset**: PankBase Single Cell RNA-seq Browser v3.3
- **Release Date**: June 4, 2025 (060425)
- **Award**: U24DK138512-DK138515
- **Lab**: pankbase-consortium
- **Data Sources**: HPAP, nPOD, ADI, IIDP, and other contributing centers
- **Chemistry**: 10X Genomics (V2, V3)
- **Total Cells**: Variable (check metadata.tsv for exact count)

### Files Included

| File Name | Description | Format |
|-----------|-------------|--------|
| `060425_scRNA_v3.3.rds` | Complete Seurat object with processed data | RDS (R) |
| `metadata.tsv` | Cell-level metadata with donor and biosample information | TSV |
| `coordinates.tsv` | UMAP coordinates for each cell | TSV |
| `lognorm_counts.tsv.gz.tsv` | Log-normalized gene expression matrix | TSV (compressed) |

## Data Processing
https://data.pankbase.org/workflows/PKBWF9623SLYX
https://data.pankbase.org/workflows/PKBWF7216YNOL

## Cell Types Included
*Note: Exact cell types present can be determined from the "Cell Type" column in metadata.tsv*

## Metadata Description

The `metadata.tsv` file contains extensive information for each cell, organized into the following categories:

### Cell-Level QC Metrics
- `NAME`: Unique cell identifier (SRA Run ID + Barcode)
- `Cell Type`: Annotated cell type
- `nCount RNA`: Total UMI counts per cell
- `nFeature RNA`: Number of genes detected per cell
- `rna pct mitochondrial`: Percentage of mitochondrial reads

### Sequencing Information
- `samples`: SRA Run ID
- `barcodes`: Cell barcode
- `treatments`: Experimental treatment (e.g., infected_with_SARS-CoV-2)
- `chemistry`: 10X Genomics chemistry version (V2, V3)
- `source`: Data source (HPAP, nPOD, ADI, IIDP)

### Donor Demographics
- `Center Donor IRRID`: Research Resource Identifier for donor
- `Donor Accession`: PankBase donor accession (PKBDO...)
- `Sex`: Donor biological sex
- `Age (years)`: Donor age
- `BMI`: Body Mass Index
- `Reported Ethnicities`: Self-reported ethnicity

### Diabetes-Related Information
- `Diabetes Status`: NA (non-diabetic), T1D, T2D, etc.
- `Diabetes Duration (years)`: Years since diagnosis
- `HbA1C (percentage)`: Hemoglobin A1C levels
- `C Peptide (ng/ml)`: C-peptide levels
- `Family History of Diabetes`: TRUE/FALSE
- `Glucose Lowering Theraphy`: Treatment information

### Autoantibody Data
- `AAB GADA POSITIVE`: Glutamic acid decarboxylase antibody
- `AAB IA2 POSITIVE`: Insulinoma-associated antigen 2 antibody
- `AAB ZNT8 POSITIVE`: Zinc transporter 8 antibody
- `AAB IAA POSITIVE`: Insulin autoantibody
- *Corresponding values (unit/ml) for each antibody*

### Biosample Information
- `Biosample Accession`: PankBase biosample accession (PKBSM...)
- `Biosample Cold Ischaemia Time (hours)`: Time on ice before processing
- `Islet Yield IEQ`: Islet equivalent yield
- `IEQ Pancreas Weight (grams)`: Pancreas weight
- `Isolation Center`: Organization that performed islet isolation
- `Organ Source`: deceased or living
- `Donation Type`: DBD (Donation after Brain Death), DCD, etc.


## Citation

If you use this dataset in your research, please cite:

### HPAP (Human Pancreas Analysis Program)

RRID:SCR_016202; PMID: 31127054; PMID: 36206763. HPAP is part of a Human Islet Research Network (RRID:SCR_014393) consortium (UC4-DK112217, U01-DK123594, UC4-DK112232, and U01-DK123716). If scRNA-seq data is used, please also cite PMID: 35228745 and PMID: 37188822.

### nPOD (Network for Pancreatic Organ donors with Diabetes)

The Network for Pancreatic Organ donors with Diabetes (nPOD; RRID:SCR_014641) is a collaborative type 1 diabetes research project supported by grants from Breakthrough T1D/The Leona M. & Harry B. Helmsley Charitable Trust (3-SRA-2023-1417-S-B) and the Helmsley Charitable Trust (2018PG-T1D053, G-2108-04793). Results and interpretation of analyses that include nPOD data are the responsibility of the authors and do not necessarily reflect the official view of nPOD. Organ Procurement Organizations (OPO) partnering with nPOD to provide research resources are listed at https://npod.org/for-partners/npod-partners/.

Additional information about how to identify nPOD samples in your work and other relevant guidelines can be found at the nPOD website (https://npod.org/publications/policies/).

### ADI (Alberta Diabetes Institute IsletCore)

Human islets for research were provided by the Alberta Diabetes Institute IsletCore at the University of Alberta in Edmonton (http://www.bcell.org/adi-isletcore.html) with the assistance of the Human Organ Procurement and Exchange (HOPE) program, Trillium Gift of Life Network (TGLN), and other Canadian organ procurement organizations. Islet isolation was approved by the Human Research Ethics Board at the University of Alberta (Pro00013094). All donors' families gave informed consent for the use of pancreatic tissue in research.

This work includes data and/or analyses from HumanIslets.com funded by the Canadian Institutes of Health Research, JDRF Canada, and Diabetes Canada (5-SRA-2021-1149-S-B/TG 179092) with data from islets isolated by the Alberta Diabetes Institute IsletCore with the support of the Human Organ Procurement and Exchange program, Trillium Gift of Life Network, BC Transplant, Quebec Transplant, and other Canadian organ procurement organizations with written informed donor consent as approved by the Human Research Ethics Board at the University of Alberta (Pro00013094).

**ADI HumanIslets.com web tool:**
- Ewald et al. (2024) HumanIslets.com: Improving accessibility, integration, and usability of human research islet data. Cell Metab. 2025 Jan 7;37(1):7-11. doi: 10.1016/j.cmet.2024.09.001. PMID: 39357523.

### IIDP (Integrated Islet Distribution Program)

Acknowledgement and citation of IIDP as the source of resources and information, including any islets, tissue, slides, data, or images from the IIDP or any of their network webpages. Some experimental results were derived from human pancreatic islets and/or other resources provided by the NIDDK-funded Integrated Islet Distribution Program (IIDP) (RRID:SCR_014387) at City of Hope, NIH Grant # 2UC4DK098085.

### Pancreatlas

Please include the URL (https://www.pancreatlas.org) and RRID (RRID:SCR_018567) or reference: Saunders, D. C. et al. Pancreatlas: Applying an Adaptable Framework to Map the Human Pancreas in Health and Disease. Patterns 1(8), 100120 (2020). DOI: 10.1016/j.patter.2020.100120.

## Contact & Support

For questions, issues, or additional information:
- **Website**: [PankBase Portal](https://pankbase.org)
- **Award**: U24DK138512-DK138515
- **Email**: help@pankbase.org

## Version History

- **v3.3** (June 4, 2025): Current release
  - Comprehensive single-cell RNA-seq dataset
  - Multiple pancreatic cell types annotated
  - Integrated data from HPAP, nPOD, ADI, IIDP
  - UMAP dimensionality reduction applied
  - Extensive donor and biosample metadata

## License

Please refer to PankBase data use policies for licensing and terms of use. Individual data sources (HPAP, nPOD, ADI, IIDP) may have specific requirements for data usage and publication. Please review the citation requirements above and consult the respective program websites for detailed policies.

---

**Dataset**: pankbase-scrna-umap-v3.3  
**Last Updated**: October 2025  
**Format**: Seurat RDS object + TSV files  
**Data Type**: Single-cell RNA-sequencing
