# S3 Data Preparation Todo List

This document lists all items that need to be prepared and uploaded to S3 for the Data Download carousel functionality.

## Overview

The Data Download carousel includes 6 downloadable resources. Each needs to be packaged appropriately and uploaded to S3 with proper metadata and documentation.

---

## 1. PanKbase scRNA UMAP (`pankbase-scrna-umap`)

### Files to Prepare:
- [X] **UMAP object** (e.g., RDS, H5AD, or other format)
- [X] **Cell by gene matrix** (counts/normalized data)
- [X] **Metadata file** (cell annotations, sample info, etc.)
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

- [X] **UMAP coordinates** (embedding coordinates)
- [X] **README/documentation** explaining file contents and usage

### Actions:
- [X] Validate all files are complete and error-free
- [X] Compress all files into `pankbase-scrna-umap.zip`
- [X] Create manifest file listing contents
- [X] Upload to S3 bucket at `/download/`
- [X] Set appropriate S3 permissions (public read)
- [X] Update "Updated: Oct 2025 | 3.2M cells" metadata

### Notes:
- Ensure file sizes are optimized for download
- Consider providing multiple format options (H5AD, RDS, etc.)

---

## 2. Pseudobulk RUV normalized counts (`pankbase-ruv-normalized-pseudo-bulk-counts-umap3.3`)

### Files to Prepare:
- [X] **Pseudobulk RUV normalized counts** for 6 cell types
- [X] **Metadata file** describing the files
      
metadata-pankbase-ruv-normalized-pseudo-bulk-counts-umap3.3.tsv

| Accession | Award | Description | File Set Type | Files | Input File Sets | Lab | Summary |
|-----------|-------|-------------|---------------|-------|-----------------|-----|---------|
| PKBDS3483TGEQ | U24DK138512-DK138515 | RUV-normalized pseudo-bulk counts for differential expression analysis of pancreatic stellate cell derived from cells in the single cell RNA-seq browser v3.3 | principal analysis | PKBFI3988BVSI,PKBFI6741PPHZ | PKBDS1349YHGQ | pankbase-consortium | principal analysis of scRNA-seq data |
| PKBDS8497JAAX | U24DK138512-DK138515 | RUV-normalized pseudo-bulk counts for differential expression analysis of pancreatic ductal cell derived from cells in the single cell RNA-seq browser v3.3 | principal analysis | PKBFI6084ZAJV,PKBFI1941JRTI | PKBDS1349YHGQ | pankbase-consortium | principal analysis of scRNA-seq data |
| PKBDS6610NSWK | U24DK138512-DK138515 | RUV-normalized pseudo-bulk counts for differential expression analysis of pancreatic acinar cell derived from cells in the single cell RNA-seq browser v3.3 | principal analysis | PKBFI6084CGGA,PKBFI3898AAJA | PKBDS1349YHGQ | pankbase-consortium | principal analysis of scRNA-seq data |
| PKBDS5505XMWS | U24DK138512-DK138515 | RUV-normalized pseudo-bulk counts for differential expression analysis of pancreatic D cell derived from cells in the single cell RNA-seq browser v3.3 | principal analysis | PKBFI1553PGUM,PKBFI3428ENDH | PKBDS1349YHGQ | pankbase-consortium | principal analysis of scRNA-seq data |
| PKBDS3519RAFX | U24DK138512-DK138515 | RUV-normalized pseudo-bulk counts for differential expression analysis of type B pancreatic cell derived from cells in the single cell RNA-seq browser v3.3 | principal analysis | PKBFI1695DUZE,PKBFI5887OGWB | PKBDS1349YHGQ | pankbase-consortium | principal analysis of scRNA-seq data |
| PKBDS9343POSP | U24DK138512-DK138515 | RUV-normalized pseudo-bulk counts for differential expression analysis of pancreatic A cell derived from cells in the single cell RNA-seq browser v3.3 | principal analysis | PKBFI1082DWBN,PKBFI4455LTGH | PKBDS1349YHGQ | pankbase-consortium | principal analysis of scRNA-seq data |

- [X] **README/documentation** explaining the analysis methodology
1. Overview
2. Dataset Information
3. Cell Types Included
4. Citation
5. Contact & Support
6. Version History
7. License


### Actions:
- [X] Compile Pseudobulk RUV normalized counts for 6 cell types
- [X] Include information about pipeline used
- [X] Compress all files into `pankbase-ruv-normalized-pseudo-bulk-counts-umap3.3.zip`
- [X] Create manifest file with file descriptions
- [X] Upload to S3 bucket at `/download/`
- [X] Set appropriate S3 permissions
- [X] Update "Updated: Oct 2025" metadata

### Future:
- [ ] Provide example scripts for loading and using the data tbd

---

## 3. snATAC Marker Peaks (`snatac-marker-peaks`)

### Files to Prepare:
- [ ] **Marker peaks data** for each cell type
- [ ] **Peak annotations** (genomic coordinates, associated genes)
- [ ] **Metadata file** with cell type information
- [ ] **README/documentation** explaining peak calling methodology

### Actions:
- [ ] Organize peaks by cell type
- [ ] Validate peak coordinates and annotations
- [ ] Compress all files into `snatac-marker-peaks.zip`
- [ ] Create manifest file
- [ ] Upload to S3 bucket at `/download/snatac-marker-peaks/`
- [ ] Set appropriate S3 permissions
- [ ] Update "Updated: Sep 2025 | peaks" metadata

### Notes:
- Total peaks:
- Include reference genome version information
- Provide formats compatible with common peak analysis tools

---

## 4. snATAC UMAP (`snatac-umap`)

### Files to Prepare:
- [ ] **Cell by peak matrix** (accessibility scores)
- [ ] **Metadata** for 91K nuclei
- [ ] **UMAP coordinates** (2D/3D embedding)
- [ ] **README/documentation** with usage instructions

### Actions:
- [ ] Validate matrix dimensions match metadata
- [ ] Check UMAP coordinate files
- [ ] Compress all files into `snatac-umap.zip`
- [ ] Create manifest file with file specifications
- [ ] Upload to S3 bucket at `/download/snatac-umap/`
- [ ] Set appropriate S3 permissions
- [ ] Update "Updated: Sep 2025 | 91K cells" metadata

### Notes:
- Total nuclei: 91K
- Ensure memory-efficient file formats for large matrices
- Consider providing sparse matrix formats

---

## 5. PanKbase Donors (`pankbase-donors`)

### Files to Prepare:
- [X] **Donor metadata TSV file** with all 3.7K donors
- [X] **Column descriptions/documentation** explaining each field
- [X] **Data dictionary** with field definitions and allowed values
- [X] **README** with sample queries and usage examples

### Actions:
- [X] Validate TSV format and encoding (UTF-8)
- [X] Check for missing or inconsistent data
- [X] Compress file(s) into `pankbase-donors.zip`
- [X] Upload to S3 bucket at `/download/`
- [X] Set appropriate S3 permissions
- [X] Update "Updated: Oct 2025 | 3.7K donors" metadata

### Notes:
- Total donors: 3.7K
- Ensure data privacy compliance (de-identification if necessary)
- Include version information schema version 18

---

## 6. PanKbase Biosamples (`pankbase-biosamples`)

### Files to Prepare:
- [X] **Biosample metadata TSV file** with all 3.6K samples
- [X] **Column descriptions** and data dictionary
- [X] **README** with usage examples and sample queries

### Actions:
- [X] Validate TSV format and data consistency
- [X] Cross-reference with donor metadata
- [X] Compress file(s) into `pankbase-biosamples.zip`
- [X] Upload to S3 bucket at `/download/`
- [X] Set appropriate S3 permissions
- [X] Update "Updated: Oct 2025 | 3.6K samples" metadata

### Notes:
- Total biosamples: 3.6K
- Ensure linking to donor IDs is accurate

---

## General S3 Setup Tasks

### S3 Bucket Configuration:
- [X] **Create or verify S3 bucket** (e.g., `pankbase-data-v1`)
- [X] **Set up bucket policy** for public read access to downloads
- [X] **Configure CORS settings** if needed for web downloads
- [ ] **Set up versioning** for data files
- [ ] **Configure lifecycle policies** for cost optimization

### Download Infrastructure:
- [ ] **Implement download tracking**
- [ ] **Configure logging** for download monitoring
- [ ] **Test download links** from the website

### Documentation:
- [ ] **Create master README** explaining all download options
- [ ] **Document S3 bucket structure**
- [ ] **Create download instructions** for users
- [ ] **Write FAQ** about data formats and usage

### Quality Assurance:
- [ ] **Validate all zip files** can be extracted successfully
- [ ] **Test download speeds** for large files
- [ ] **Verify file integrity** (checksums/MD5)
- [ ] **Check all metadata is accurate** (counts, dates, etc.)
- [ ] **Perform end-to-end download test** from website

### Maintenance:
- [ ] **Set up automated backup** of data files
- [ ] **Create update schedule** for data refresh
- [ ] **Document data versioning** approach
- [ ] **Plan for future data additions**

---

## File Structure Example

```
pankbase-data-v1/
├── download/
│   ├── pankbase-scrna-umap-v3.3.tar.gz	
│   ├── pankbase-snatac-umap-v1.0.tar.gz
│   ├── pankbase-ruv-normalized-pseudo-bulk-counts-umap3.3.tar.gz
│   ├──  pankbase-peak-counts-snATAC-seq-umap1.0.tar.gz
│   ├── pankbase-biosamples.tar.gz
│   └── pankbase-donors.tar.gz
```

  

---

## Notes

- Ensure all data follows FAIR principles (Findable, Accessible, Interoperable, Reusable)
- Consider providing data in multiple formats for broader accessibility
- Keep file sizes manageable (consider splitting very large files)
- Document any data transformations or preprocessing steps
- Include contact information for data-related questions

