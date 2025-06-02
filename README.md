# Interactive-Analysis-with-Biological-Pathways
The Autopath project explores how to surface biological pathways for two diseases, as a way to make it easier for biologists to get insight from the raw data. Our two case studies are **Age-Related Macular Degeneration** - a degenerative process affecting the macula of the retina that occurs in older adults and results in impairment or loss of central vision - and **Systemic Lupus Erythematosus (SLE)** - a chronic autoimmune disease where the immune system mistakenly attacks healthy tissues and organs, leading to inflammation and damage. 

# Project overview 

## What's the problem?   
How can we leverage existing data to understand and treat disease? 

## Challenges 
- There's **too much data**, sometimes stored in different locations and on different cloud infrastructure, and it's **too hard to find and combine the right data** for analysis.
- Analysis **tools require too much comp bio wrangling** and are **not user-friendly (for biologists)**.    

## Solution
- Create a reproducible workflow to transform single cell expression data from different sources into a visualization of gene pathway enrichment
- Access data where it lives - possibly different “places” - and combine for the most robust dataset     
- Analyze collaboratively in a Terra workspace using reproducible tools where it’s most efficient - possibly two different clouds (AWS and GCP).

## Workflow diagram
<img width="945" alt="Screenshot 2025-04-04 at 8 54 05 AM" src="https://github.com/user-attachments/assets/3c3b26e1-e2a7-4f37-8b23-5952f866d412" />


# Use case #1: Macular Degeneration 
Age-related macular degeneration (AMD) affects 12% of Americans over 40 [1] and is a leading cause of blindness.  Better knowledge of the biomolecular causes of AMD would improve treatment, and improve American healthspans.  GTEx, an NIH CFDE project, has unique, rich, and systematic data on gene expression in human eyes [2, 3].  Data is publicly accessible on AnVIL.  Exporting this data to the Terra biomedical cloud analysis platform, conducting reproducible differential expression analysis on it, and exploring the resulting data in biological pathway diagrams will improve understanding of this complex disease's biochemical causes and effects, and stimulate the efficient development of better diagnostics and medical treatments for AMD.

[1] https://pmc.ncbi.nlm.nih.gov/articles/PMC9634594/      
[2] https://explore.anvilproject.org/datasets/e5aee011-bdb3-4caa-954c-a46678656270     
[3] https://pmc.ncbi.nlm.nih.gov/articles/PMC6441365/       


## Data overview

### HRCA: snRNA-seq of the human retina - all cells     
- Access from Single Cell Portal at https://singlecell.broadinstitute.org/single_cell/study/SCP2805/hrca-snrna-seq-of-the-human-retina-all-cells#study-summary. 

### GTEx public data         
-  Access GTEx public data in the AnVIL Data Explorer at https://explore.anvilproject.org/datasets/e5aee011-bdb3-4caa-954c-a46678656270. Note that you must be signed in with your Terra user ID to export data from the Data Explorer.     
- For step-by-step instructions on how to access and download data from the Data Explorer to a Terra workspace, see the support doc on how to export AnVIL data for analysis at [https://support.terra.bio/hc/en-us/articles/34607573660827](Part-3-Export-AnVIL-data-to-Terra-for-analysis). 
    

# Workflow overview (the analysis tools)

## 1. Filter raw data (H5ad -> NSForest ->  binary genes)

The ultimate goal is to include quality assurance with Silhouette score correlated to F-score.

### Identify marker and binary genes (NS Forest batch on AWS)      
**Advanced Analytics Module**
- EC Orchestration, 
- Nextflow Execution, 
- Cost management, 
- Workspace collaboration

**Dockerize the NSForest 4.1 Python package**      
- Dockerfile
- GitHub actions CI and Image publication     

- **Docker**:
Make sure Docker is installed and actively running in the background.
Verify Docker installation and status using:
  ```bash
  docker --version
  ```

**Forked NSForest - with Docker, GitHub actions CI, Publish**
[https://github.com/adeslatt/NSForest/blob/master/README.md](https://github.com/adeslatt/NSForest/blob/master/README.md)

**[Nextflow workflow (WIP](https://github.com/nih-nlm/nsforest-nf
)**
-  Updating to 4.1 
- greater modularization, autodocumentation with Sphinx


## 2. Enrich filtered data    

### 2.1. Enrichr    
INCLUDE brief analysis tool description and link here

### 2.2. CFDE Knowledge Center
INCLUDE brief analysis tool description and link here      

## 3. Differential Gene Expression (RStudio in Terra)

### 3.1. Gene Set Enrichment Analysis (GSEA) 
We created  the [gene-set-enrichment-analysis.ipynb](https://github.com/BioITHackathons/Interactive-Analysis-with-Biological-Pathways/blob/main/docs/notebooks/gene-set-enrichment-analysis.ipynb) Jupyter notebook to perform pathway enrichment analysis. 

The notebook takes a list of genes produced by an upstream analysis as input and uses the [gseapy](https://gseapy.readthedocs.io/en/latest/introduction.html) python library’s enrichr tool to perform pathway enrichment analysis to identify cell pathways that are statistically overrepresented in the input gene set. The enrichr tool was run with the WikiPathways_2024_Human gene set and produces a table containing the highest-scoring cell pathways, for that particular gene set, sorted in descending order. 

Finally, these pathways, along with their associated genes and any scores/values associated with each gene, are used to generate URLs that point to a downstream cell pathway visualization tool. 

An example run of this notebook and a table of example links to to the cell pathway visualization tool can be found at the following link in our Terra workspace:

(app.terra.bio/#workspaces/single-cell-portal-development/bio-it-hackathon-2025/analysis/launch/gene-set-enrichment-analysis.ipynb)


## 4. Render interactive biological pathways diagram
INCLUDE brief analysis tool description and link here.

# Reproducible Terra workspace 
LINK TO WORKSPACE AND ADD DESCRIPTION HERE



## Usage Guidelines
[https://github.com/omicscodeathon/Interactive-Analysis-with-Biological-Pathways/](https://github.com/BioITHackathons/Interactive-Analysis-with-Biological-Pathways/)

# Next steps 

## Sticking points 

INCLUDE things we wanted to do but couldn’t

## Further iterations


#  Team Members
- [Eric Weitz](https://github.com/eweitz): The Broad Institute
- [Anne  Deslattes Mays](https://github.com/adeslatt): Science and Technology Consulting, LLC
- Lei Ma: Harvard FAS Informatics Group
- [Olaitan I. Awe](https://github.com/laitanawe): Independent Bioinformatics Consultant.
- Peter Fan: Northeastern University Library
- Allie Cliffe: The Broad Institute


