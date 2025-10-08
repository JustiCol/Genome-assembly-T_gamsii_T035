# Genome-assembly-T_gamsii_T035

Pipeline to assemble and annotate the genome of *Trichoderma gamsii* strain T035 from Oxford Nanopore Technologies (ONT) reads.

---

## Overview

This repository contains all data, scripts, and results used in the assembly, annotation, and validation of the T035 genome. It also includes data and scripts used to evaluate the biocontrol capacity of *T. gamsii* T035 and perform comparative genomics.

---

## Repository Structure

### data/ 
Contains strain information, transcriptomic data, and supplementary tables.

- "List_of_transcriptomic_data.xlsx": Origin of transcriptomic data used to confirm the quality of the genome structural annotation.
- "Strains_for_MashTree.xlsx": Names and origins of all strains used to generate the MashTree presented in Figure 2.
- "Table pathogens.xlsx": Names and origins of plant pathogens used to evaluate the biocontrol capacity of *T. gamsii* T035.
- "Supplementary_tables.xlsx": All supplementary tables relevant to the study.

---

### results/
Contains supplementary figures and genome annotations.

- "Supplementary_Figure_S1.png": Scale used to evaluate *T. gamsii* overgrowth on several plant pathogens (Figure 4A).
- "T_gamsii_T035.gff": Structural genome annotation obtained with Helixer.
- "T_gamsii_T035_anno.gff": Structural annotation supplemented with functional annotation from Eggnog.
- "S2_linear_plot.png": Linear k-mer frequency plot generated with GenomeScope, showing the number of k-mers (y-axis) versus k-mer coverage (x-axis).
- "S3_log_plot.png": Logarithmic version of the k-mer frequency plot.
- "S4_transformed_linear_plot.png": Linear plot of transformed k-mer frequencies to highlight repetitive content.
- "S5_transformed_log_plot.png": Logarithmic version of the transformed k-mer plot.

---

### scripts/  
All scripts used in the study, organized by analysis type.

#### Annotation/
- "EDTA": SLURM script to detect transposable elements. Outputs summarized in Supplementary Table S4 ("Supplementary_tables.xlsx").
- "GFFread.txt": SLURM script to extract CDS, transcript, and protein files from the genome and its GFF annotation.

#### Genome_assembly/
- "Genome_assembly_contigs.txt": SLURM script to assemble T035 genome de novo using sequencing reads from BioProject PRJNA1327094.
- "Contigs_to_scaffolds_Ragtag": SLURM script to scaffold contigs using the *T. atroviride* reference genome (GCF_020647795.1). The resulting assembly has been submitted to the same BioProject (PRJNA1327094) but is not yet publicly available (as of 07/10/2025).

#### In_vitro_tests/
- "Antibiosis_script": Script to generate Figure 4B’s boxplot from "test.xlsx".
- "Parasitism_script.txt": Script to generate Figure 4A’s radar plot from "df.xlsx".
- "df.xlsx": Data for the radar plot (Figure 4A). Column A: tested pathogens; Column B: antagonist strain (I1237 or T035); Columns C & D: technical and biological replicates; Column E: parasitic graduation (see "Supplementary_Figure_S1.png").
- "test.xlsx": Data for the boxplot (Figure 4B). Column A: bacterial pathogens; Column B: antagonist strain (I1237, T035, or control); Columns C & D: technical and biological replicates; Column E: area under the curve (AUC) of bacterial growth, measured by spectrophotometry.

#### Mash_comparison/
- "MashTree": SLURM script to generate the Newick tree for Figure 2. Genomes used are listed in "Strains_for_MashTree.xlsx".

#### Quality/
- "k-mer_analysis": SLURM script to generate the k-mer histogram. This histogram was later used to obtain the spectra plots to evaluate the genome quality with GenoScope (see "S2_linear_plot.png", "S3_log_plot.png", "S4_transformed_linear_plot.png", "S5_transformed_log_plot.png"). All results can be observed at the following link: http://genomescope.org/genomescope2.0/analysis.php?code=S5DhLvgnW5NZNsCLj1KN

#### Validation_with_STAR/
- "STAR": SLURM script to validate the structural genome annotation ("T_gamsii_T035.gff") using public transcriptomic data ("List_of_transcriptomic_data.xlsx").

---

## Usage

Scripts are designed for SLURM-based clusters with Conda environments.

---

## Genome Data Availability

- **BioProject:** PRJNA1327094 (*Trichoderma gamsii* strain T035 genome sequencing)  
- **BioSample:** SAMN51264459  
- **SRA:** SRR35336635  
- **TaxID:** 398673  

---

## Citation

If you use this dataset or pipeline, please cite: Draft genome of *Trichoderma gamsii* strain T035 a promising beneficial fungus in agriculture (https://doi.org/10.1101/2025.09.22.677720).

---

## GitHub Repository

The scripts and pipeline are also available on GitHub: https://github.com/JustiCol/Genome-assembly-T_gamsii_T035/tree/main.




