# PankBase Biosample Metadata

## Overview

This dataset contains comprehensive metadata for **pancreatic biosamples** from the PankBase consortium, including three major biosample types:

1. **Primary Islets**: Pancreatic islet cells directly harvested from human donors
2. **Human Beta Cell Lines**: Immortalized beta cell lines (EndoC-βH1, EndoC-βH2, EndoC-βH3, EndoC-βH5)
3. **Primary Cells**: Other primary pancreatic cell types isolated from donors

This resource enables researchers to identify appropriate biosamples for experiments, understand sample characteristics and processing conditions, link samples to donors and experimental data, and ensure reproducibility through comprehensive metadata.

## Dataset Information

- **Data Sources**: HPAP, nPOD, ADI, IIDP, Prodo Laboratories, Cell Line Vendors
- **Award**: U24DK138512-DK138515
- **Lab**: pankbase-consortium
- **Format**: Tab-separated values (TSV)
- **Primary Islet Schema**: https://data.pankbase.org/profiles/primary_islet/
- **Cell Line Documentation**: Based on EndoC-β cell line series

## Biosample Types

### 1. Primary Islets

**Pancreatic islets** directly isolated from human donors through enzymatic digestion and purification. These samples represent the most physiologically relevant in vitro model of human islet biology.

**Key Characteristics:**
- Freshly isolated from human pancreata
- Contain mixed cell populations (alpha, beta, delta, PP cells, etc.)
- Variable purity and viability depending on isolation
- Available from multiple isolation centers (IIDP, HPAP, ADI, Prodo)

**Typical Uses:**
- Glucose-stimulated insulin secretion (GSIS) assays
- Bulk RNA-seq, scRNA-seq
- Proteomics and metabolomics
- Electrophysiology
- Transplantation studies

### 2. Human Beta Cell Lines

**Immortalized human beta cell lines** derived from a 9-week-old female fetal pancreas. Four distinct lines are available, each with unique properties:

#### EndoC-βH1 (CVCL_IS71)
- **Immortalization**: Constitutive (SV40 large T antigen + hTERT)
- **Properties**: Continuously proliferating, robust, well-characterized
- **Source**: Ravassard et al., *JCI* 2011
- **Applications**: High-throughput screening, CRISPR line generation, electrophysiology
- **Availability**: Commercial and via MTA

#### EndoC-βH2 (CVCL_L909)
- **Immortalization**: Conditional (Cre-lox excision)
- **Properties**: Can return to non-proliferative, mature state
- **Source**: Scharfmann et al., *JCI* 2014
- **Applications**: Studying mature beta cell biology

#### EndoC-βH3 (CVCL_IS72)
- **Immortalization**: Drug-inducible excision (tamoxifen-responsive)
- **Properties**: Rapid generation of non-proliferative, high-insulin cells
- **Source**: Benazra et al., *Mol Metab* 2015
- **Applications**: Studies requiring mature beta cell phenotype

#### EndoC-βH5
- **Immortalization**: Pre-excised before distribution
- **Properties**: High-purity, primary-like beta cells, cannot be expanded
- **Source**: Blanchi et al., *Mol Metab* 2023
- **Applications**: Experiments requiring consistent, primary-like phenotype

### 3. Primary Cells

**Other primary pancreatic cell types** isolated from human donors, including sorted populations, cultured cells, and specialized preparations.

## Field Categories

### Core Identifiers (Required for All)

- `Accession`: Unique PankBase identifier (PKBSM...)
- `Sample Terms`: Ontology term identifying the biosample (UBERON, EFO, CL terms)
- `Sample Name`: Text-based identifier (e.g., "EndoC-bH1", "HP-21337-01")
- `Classification`: Biosample type (primary islet, cell line, primary cell)
- `Description`: Detailed description of the biosample

### Donor Information (Required)

- `Donors`: Link to donor record (PKBDO...)
- `Sex`: Biological sex (auto-populated from donor)
- `Age`: Age at collection time
- `Age Units`: Units for age measurement
- `Lower Bound Age`: Minimum age for range
- `Lower Bound Age In Hours`: Age in hours
- `Embryonic`: Whether sample is from embryonic tissue

### Sample Origin and Relationships

**Derivation:**
- `Originated From`: Link to parent biosample (for differentiation, modification)
- `Part of Biosample`: Link to larger biosample this is part of
- `Pooled From`: Biosamples pooled to create this sample
- `Sorted From`: Larger sample from which this was sorted
- `Sorted From Detail`: Details on sorting fractions
- `demultiplexed_from`: Parent multiplexed sample

**Products:**
- `Biosample Parts`: Parts into which this sample was divided
- `Sorted Fraction Samples`: Fractions this sample was sorted into
- `Demultiplexed To`: Samples demultiplexed from this one
- `Multiplexed In`: Multiplexed samples containing this sample
- `Pooled In`: Pooled samples containing this sample
- `Origin Sample Of`: Samples that originated from this one

### Primary Islet-Specific Fields

#### Tier 0 (Required for Primary Islets)

- `Cold Ischaemia Time (hours)`: Duration pancreas kept cold after removal
- `Isolation Center`: Facility where islets were isolated
- `Lab`: Lab associated with submission

#### Tier 1 (Highly Recommended)

- `RRID`: Research Resource Identifier for biosample
- `Organ Source`: Type of organ donor (deceased, living)
- `Resource`: Processing facility (HPAP, IIDP, nPOD, ADI)
- `Prep Viability (percentage)`: Pre-shipment islet viability
- `Warm Ischaemia Duration / Down Time (hours)`: Time without blood supply
- `Purity (Percentage)`: Pre-shipment islet purity
- `Hand Picked`: Whether manually selected
- `Pre-Shipment Culture Time (hours)`: Culture time before shipping
- `Islet Function Available`: Whether functional data available

#### Tier 2 (Additional Context)

**Islet Characteristics:**
- `Islet Yield (IEQ)`: Total islet equivalents obtained
- `IEQ/Pancreas Weight (grams)`: IEQ per gram of pancreas
- `Post-Shipment islet viability (%)`: Viability after shipping
- `Digest Time (hours)`: Pancreas digestion time
- `Percentage Trapped (percentage)`: Trapped/non-functional islets
- `Islet Morphology`: Whether morphology assessed
- `Islet Histology`: Whether histology assessed

**Sample Processing:**
- `FACS Purification`: FACS protocols used
- `Preservation Method`: Tissue preservation method
- `Date Harvested`: Sample harvest date
- `Post-mortem Interval (hours)`: Time elapsed since death
- `pmi_units`: Units for post-mortem interval

### Cell Line-Specific Fields

#### Required Cell Line Fields

- `Sources`: Originating vendor (e.g., "human-cell-design")
- `Year Obtained`: Year obtained from vendor
- `Lot ID`: Vendor lot identifier
- `Product ID`: Vendor product identifier
- `Vendor Passage`: Passage number from vendor

#### Cell Line Culture Conditions

- `Coating Condition`: Coating buffer and incubation time
- `Excision Status`: Immortalization cassette status (excised, non-excised)
- `Growth Medium`: Medium used for culture
- `Cell Density`: Culture density
- `Passage Number`: Passages from source
- `Date Obtained`: Date obtained from source
- `Date Harvested`: Date harvested for assay
- `Authentication`: Authentication method used

### Experimental Modifications

**Treatments:**
- `Treatments`: Treatments applied (cytokines, drugs, etc.)
- `cell_fate_change_treatments`: Treatments for cell fate changes
- `time_post_change`: Time after treatment
- `time_post_change_units`: Units for time post-treatment

**Genetic Modifications:**
- `Modifications`: Modifications applied (CRISPR, shRNA, etc.)
- `Construct Library Sets`: Vectors introduced
- `Nucleic Acid Delivery`: Delivery method (lentiviral, transfection)
- `Multiplicity Of Infection`: MOI for vector introduction
- `Time Post Library Delivery`: Time after delivery
- `Time Post Library Delivery Units`: Units for time post-delivery
- `Cellular Sub Pool`: Cellular sub-pool fraction

**Biological Markers:**
- `Biomarkers`: Markers associated with biosample
- `targeted_sample_term`: Target cell type for differentiation

### Processing and Protocols

- `Protocols`: Links to preparation protocols
- `cell_fate_change_protocol`: Protocol for cell fate changes
- `Starting Amount`: Initial quantity obtained
- `Starting Amount Units`: Units for starting amount

### Disease and Phenotype

- `Disease Terms`: Associated disease ontology terms

### Associated Data

- `File Sets`: Linked experimental file sets
- `Documents`: Additional documentation
- `Publication Identifiers`: Related publications (PMIDs)
- `Institutional Certificates`: Institutional approvals

### External References

- `URL`: External resource links
- `External Resources`: External database identifiers
- `Award`: Grant associated with submission

### Administrative Fields

- `Notes`: Internal notes
- `Summary`: Auto-generated summary

## Data Interpretation Notes

### Missing Data Conventions

- `NA`, empty field: Data not available or not applicable
- `-999`: Explicitly unknown or not measured
- `unknown`: Status unknown

### Sample Relationship Fields

Sample relationships use PankBase accession identifiers:
- **Originated From**: Parent sample (e.g., after CRISPR modification, differentiation)
- **Part of Biosample**: Larger sample this is a fraction of (e.g., aliquot)
- **Pooled From**: Comma-separated list of samples pooled together
- **Sorted From**: Sample from which this was FACS/cell sorted

### Islet Quality Metrics

**Viability:**
- Pre-Shipment: Measured at isolation center before shipping
- Post-Shipment: Measured after receiving at destination lab
- Values typically 70-95% for high-quality preparations

**Purity:**
- Percentage of islet tissue vs. exocrine contamination
- Measured by Dithizone (DTZ) staining or other assays
- Values >80% considered high purity

**IEQ (Islet Equivalent):**
- Standardized measure: 1 IEQ = islet with 150 μm diameter
- Typical yields: 100,000-500,000 IEQ per pancreas
- Yield depends on donor factors, ischemia time, digestion quality

### Cold and Warm Ischemia

**Cold Ischemia Time:**
- Time pancreas kept on ice after removal from donor
- Affects islet viability and function
- Typical range: 6-20 hours
- Shorter times generally better

**Warm Ischemia (Down Time):**
- Time without blood supply at body temperature
- Critical for islet quality
- <30 minutes preferred for optimal function

### Cell Line Passage Numbers

- **Vendor Passage**: Passage number when received from vendor
- **Passage Number**: Current passage number (passages from source)
- Lower passages generally preferred for consistency
- EndoC-βH1 can be passaged extensively; EndoC-βH5 cannot be expanded

### Excision Status (Cell Lines)

- **Non-excised**: Immortalizing transgenes still present, cells proliferate
- **Excised**: Immortalizing cassette removed, cells more mature, non-proliferative
- Relevant for EndoC-βH2, EndoC-βH3, EndoC-βH5

## Quality Control Recommendations

When using this dataset:

1. **Check completeness**: Not all fields populated for all samples
2. **Verify sample type**: Ensure biosample matches your experimental needs
3. **Review processing conditions**: Cold ischemia, culture time affect sample quality
4. **Check viability and purity**: For primary islets, use quality metrics
5. **Validate cell line identity**: Check passage number, excision status
6. **Link to donors**: Use donor data for additional context
7. **Review modifications**: Check for genetic modifications or treatments
8. **Verify RRID availability**: For reproducibility and cross-referencing


## Citation

If you use this dataset in your research, please cite:

### For Primary Islets from HPAP

RRID:SCR_016202; PMID: 31127054; PMID: 36206763. HPAP is part of a Human Islet Research Network (RRID:SCR_014393) consortium (UC4-DK112217, U01-DK123594, UC4-DK112232, and U01-DK123716).

### For Primary Islets from nPOD

The Network for Pancreatic Organ donors with Diabetes (nPOD; RRID:SCR_014641) is a collaborative type 1 diabetes research project supported by grants from Breakthrough T1D/The Leona M. & Harry B. Helmsley Charitable Trust (3-SRA-2023-1417-S-B) and the Helmsley Charitable Trust (2018PG-T1D053, G-2108-04793).

### For Primary Islets from ADI

Human islets for research were provided by the Alberta Diabetes Institute IsletCore at the University of Alberta in Edmonton (http://www.bcell.org/adi-isletcore.html). Islet isolation was approved by the Human Research Ethics Board at the University of Alberta (Pro00013094).

**ADI HumanIslets.com web tool:**
- Ewald et al. (2024) HumanIslets.com: Improving accessibility, integration, and usability of human research islet data. Cell Metab. 2025 Jan 7;37(1):7-11. doi: 10.1016/j.cmet.2024.09.001. PMID: 39357523.

### For Primary Islets from IIDP

Some experimental results were derived from human pancreatic islets provided by the NIDDK-funded Integrated Islet Distribution Program (IIDP) (RRID:SCR_014387) at City of Hope, NIH Grant # 2UC4DK098085.

### For EndoC Beta Cell Lines

**EndoC-βH1:**
- Ravassard P, et al. A genetically engineered human pancreatic β cell line exhibiting glucose-inducible insulin secretion. J Clin Invest. 2011;121(9):3589-97. PMID: 21865645

**EndoC-βH2:**
- Scharfmann R, et al. Development of a conditionally immortalized human pancreatic β cell line. J Clin Invest. 2014;124(5):2087-98. PMID: 24667639

**EndoC-βH3:**
- Benazra M, et al. A human beta cell line with drug inducible excision of immortalizing transgenes. Mol Metab. 2015;4(12):916-25. PMID: 26909311

**EndoC-βH5:**
- Blanchi B, et al. EndoC-βH5: A novel human beta cell line for in vitro research. Mol Metab. 2023. PMID: 36681354

### Metadata Standards

Based on standards developed by IIDP, HPAP, and University of Alberta IsletCore, consistent with:
- Hart N & Powers A. Diabetologia 2018
- Brissova M et al. Diabetes 2019
- Brissova M et al. Diabetologia 2019

## Contact & Support

For questions, issues, or additional information:
- **Website**: [PankBase Portal](https://pankbase.org)
- **Primary Islet Schema**: https://data.pankbase.org/profiles/primary_islet/
- **Award**: U24DK138512-DK138515
- **Email**: help@pankbase.org

## Data Use Guidelines

### Source-Specific Requirements

**Primary Islets:**
- Check source program (HPAP, nPOD, ADI, IIDP) for specific usage requirements
- Use RRIDs in publications for reproducibility
- Some programs require manuscript review before publication

**Cell Lines:**
- Commercial cell lines: Follow vendor terms of use
- MTA-distributed lines: Comply with material transfer agreement
- Cite original publications for each cell line used

### Recommended Practices

- Report `Accession` and `RRID` in methods for reproducibility
- Describe sample selection criteria clearly
- Report passage numbers for cell lines
- Document culture conditions and modifications
- Acknowledge tissue donors and their families

## License

Please refer to PankBase data use policies for licensing and terms of use. Individual data sources (HPAP, nPOD, ADI, IIDP) and commercial vendors may have specific requirements. Please review citation requirements and consult respective program websites for detailed policies.

---

**Dataset**: pankbase-biosamples.tsv  
**Last Updated**: October 2025  
**Format**: Tab-separated values (TSV)
**Schema Version**: 19
**Biosample Types**: Primary Islets, Human Beta Cell Lines, Primary Cells
