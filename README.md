# Genomic analysis of immunoglobulin loci in the Vertebrate Genome Project

This repository contains data and scripts for the analysis of immunoglobulin (IG) loci across 531 species assembled by the Vertebrate Genome Project.

---

## Data Overview

### 1. `all_species_stats_pruned_12052025.csv`

This file provides a **summary of IG locus annotations across all 531 species**.

Each row corresponds to one species and includes locus-level statistics for:
- IGH (heavy chain)
- IGK (kappa light chain)
- IGL (lambda light chain)
- IGI (other light chain, if present)

#### Column description (repeated per locus: IGH, IGK, IGL, IGI)

- **`<LOCUS>_AnnotationLevel`**  
  Describes how the locus is represented in the genome assembly:
  - `0` → One proximal locus
  - `1` → One distal locus
  - `2` → Multiple loci detected
  - `3` → Locus not detected

- **`<LOCUS>_TotalLength`**  
  Total genomic length spanned by the locus.

- **`<LOCUS>_TotalGenes`**  
  Total number of annotated genes within the locus.

- **`<LOCUS>_MinDir`**  
  Fraction of genes located on the same strand within this locus

- **`<LOCUS>_NumContigs`**  
  Number of contigs the locus is distributed across.  

- **`<LOCUS>_LocusFraction`**  
  Fraction of the total genome assembly occupied by the locus.

#### Additional columns

- **`SpeciesID`** – Unique identifier for each species  
- **`TableIdx`** – Internal index used in downstream analyses  
- **`VertClass`** – Vertebrate class (e.g., mammals, birds, fish, ...)  
- **`TreeID`** – Identifier linking species to the phylogenetic tree  
- **`LatinName`** – Scientific species name  

---

### 2. `annotation_stats.zip`

This archive contains **per-species annotation statistics**, organized into individual CSV files (see `annotation_stats/` after unzipping).

Each file corresponds to one species and contains locus-specific annotation details.

#### Common columns (same structure across all files)

- **`SpeciesID`** – Unique species identifier  
- **`Path`** – File path or source of the annotation  
- **`Locus`** – IG locus (e.g., IGH, IGK, IGL, IGI)  

- **`AnnotationLevel`**  
  Same interpretation as above:
  - `0` → One proximal locus  
  - `1` → One distal locus  
  - `2` → Multiple loci  
  - `3` → Undetected  

- **`NumGenes`**  
  Number of genes annotated for this locus.

- **`ContigInfo`**  
  Genomic coordinates of the locus in the format: [(contig_name, start, end)]

  - **`NumContigs`**  
Number of contigs containing locus sequences.

- **`LocusFraction`**  
Fraction of the genome assembly occupied by this locus.

---

### 3. `gene_fasta_files_032726.zip`

This archive contains **FASTA files of annotated IG genes**, organized by locus and class.

- Each file includes nucleotide sequences of annotated genes.
- Headers typically encode gene identity and annotation details (depending on preprocessing pipeline).

---
  
