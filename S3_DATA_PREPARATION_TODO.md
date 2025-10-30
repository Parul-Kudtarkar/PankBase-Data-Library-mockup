# S3 Data Preparation Todo List

This document lists all items that need to be prepared and uploaded to S3 for the Data Download carousel functionality.

## Overview

The Data Download carousel includes 6 downloadable resources. Each needs to be packaged appropriately and uploaded to S3 with proper metadata and documentation.

---

## 1. PanKbase scRNA UMAP (`pankbase-scrna-umap`)

### Files to Prepare:
- [ ] **UMAP object** (e.g., RDS, H5AD, or other format)
- [ ] **Cell by gene matrix** (counts/normalized data)
- [ ] **Metadata file** (cell annotations, sample info, etc.)
- [ ] **UMAP coordinates** (embedding coordinates)
- [ ] **README/documentation** explaining file contents and usage

### Actions:
- [ ] Validate all files are complete and error-free
- [ ] Compress all files into `pankbase-scrna-umap.zip`
- [ ] Create manifest file listing contents and checksums
- [ ] Upload to S3 bucket at `/download/pankbase-scrna-umap/`
- [ ] Set appropriate S3 permissions (public read)
- [ ] Update "Updated: Oct 2025 | 3.2M cells" metadata

### Notes:
- Total cells: 3.2M
- Ensure file sizes are optimized for download
- Consider providing multiple format options (H5AD, RDS, etc.)

---

## 2. Pseudobulk RUV normalized counts (`pankbase-ruv-normalized-pseudo-bulk-counts-umap3.3`)

### Files to Prepare:
- [ ] **Pseudobulk RUV normalized counts** for 6 cell types
- [ ] **Metadata file** describing the comparison groups
- [ ] **README/documentation** explaining the analysis methodology

### Actions:
- [ ] Compile Pseudobulk RUV normalized counts for 6 cell types
- [ ] Validate completeness of comparisons
- [ ] Compress all files into `pankbase-ruv-normalized-pseudo-bulk-counts-umap3.3.zip`
- [ ] Create manifest file with file descriptions
- [ ] Upload to S3 bucket at `/download/`
- [ ] Set appropriate S3 permissions
- [ ] Update "Updated: Oct 2025" metadata

### Notes:
- Include information about statistical methods used
- Provide example scripts for loading and using the data

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
- [ ] **Donor metadata TSV file** with all 3.7K donors
- [ ] **Column descriptions/documentation** explaining each field
- [ ] **Data dictionary** with field definitions and allowed values
- [ ] **README** with sample queries and usage examples

### Actions:
- [ ] Validate TSV format and encoding (UTF-8)
- [ ] Check for missing or inconsistent data
- [ ] Compress file(s) into `pankbase-donors.zip`
- [ ] Create manifest file
- [ ] Upload to S3 bucket at `/download/pankbase-donors/`
- [ ] Set appropriate S3 permissions
- [ ] Update "Updated: Oct 2025 | 3.7K donors" metadata

### Notes:
- Total donors: 3.7K
- Ensure data privacy compliance (de-identification if necessary)
- Include version information

---

## 6. PanKbase Biosamples (`pankbase-biosamples`)

### Files to Prepare:
- [ ] **Biosample metadata TSV file** with all 3.6K samples
- [ ] **Column descriptions** and data dictionary
- [ ] **README** with usage examples and sample queries

### Actions:
- [ ] Validate TSV format and data consistency
- [ ] Cross-reference with donor metadata
- [ ] Compress file(s) into `pankbase-biosamples.zip`
- [ ] Create manifest file
- [ ] Upload to S3 bucket at `/download/pankbase-biosamples/`
- [ ] Set appropriate S3 permissions
- [ ] Update "Updated: Oct 2025 | 3.6K samples" metadata

### Notes:
- Total biosamples: 3.6K
- Ensure linking to donor IDs is accurate
- Include information about sample preparation protocols

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
pankbase-data/
├── download/
│   ├── pankbase-scrna-umap/
│   │   └── pankbase-scrna-umap.zip
│   ├── deg-analysis/
│   │   └── deg-analysis.zip
│   ├── snatac-marker-peaks/
│   │   └── snatac-marker-peaks.zip
│   ├── snatac-umap/
│   │   └── snatac-umap.zip
│   ├── pankbase-donors/
│   │   └── pankbase-donors.zip
│   └── pankbase-biosamples/
│       └── pankbase-biosamples.zip
```

  

---

## Notes

- Ensure all data follows FAIR principles (Findable, Accessible, Interoperable, Reusable)
- Consider providing data in multiple formats for broader accessibility
- Keep file sizes manageable (consider splitting very large files)
- Document any data transformations or preprocessing steps
- Include contact information for data-related questions

