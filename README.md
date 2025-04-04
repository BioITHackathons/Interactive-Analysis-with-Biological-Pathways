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
INSERT GENERAL DESCRIPTION OF THIS USE CASE AND WHY IT’S IMPORTANT TO ENABLE THE FUNCTIONALITY FROM THE HACKATHON. 

## Data overview
INCLUDE DATA DESCRIPTION 

### HRCA: snRNA-seq of the human retina - all cells     
- Access from  [https://singlecell.broadinstitute.org/single_cell/study/SCP2805/hrca-snrna-seq-of-the-human-retina-all-cells#study-summary](Single Cell Portal)   
- INCLUDE overview of how to access and where to put the data

### GTEx public data         
-  Access from  [https://explore.anvilproject.org/datasets/e5aee011-bdb3-4caa-954c-a46678656270](GTEx public data in the AnVIL Data Explorer). Note that you must be signed in with your Terra user ID to export data from the Data Explorer.     
- For step-by-step instructions on how to access and download data from the Data Explorer to a Terra workspace, see [https://support.terra.bio/hc/en-us/articles/34607573660827-Part-3-Export-AnVIL-data-to-Terra-for-analysis](Export AnVIL data for analysis). 
    

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

### 3.1. Gene Set Enrichment Analysis (GSEA) 
INCLUDE brief analysis tool description and link here

## 3. Differential Gene Expression (RStudio on Terra)
INCLUDE brief analysis tool description and link here. 

## 4. Render interactive biological pathways diagram
INCLUDE brief analysis tool description and link here.

# Reproducible Terra workspace 
LINK TO WORKSPACE AND ADD DESCRIPTION HERE

# Use case: Lupus 

## Data overview
INCLUDE DATA DESCRIPTION 
- 
- 

## Analysis overview

### 1. Filter raw data to identify marker and binary genes    
**NS Forest batch on AWS**       
INCLUDE TOOL DESCRIPTION AND LINK HERE

- **Docker**:
Make sure Docker is installed and actively running in the background.
Verify Docker installation and status using:
  ```bash
  docker --version
  ```

### 2. Enrich filtered data 

**Enricher + CFDE Knowledge Center** 

### 3. Downstream analysis    

#### 3.1. Gene Set Enrichment Analysis (GSEA) 
INCLUDE ANALYSIS/TOOL DESCRIPTION AND LINK HERE

#### 3.2 Differential Gene Expression (RStudio on Terra)
INCLUDE ANALYSIS/TOOL DESCRIPTION AND LINK HERE

### 4. Results and insight    
**Render interactive biological pathways diagram**       
INCLUDE ANALYSIS/TOOL DESCRIPTION AND LINK HERE

## Usage Guidelines
[https://github.com/omicscodeathon/Interactive-Analysis-with-Biological-Pathways/](https://github.com/BioITHackathons/Interactive-Analysis-with-Biological-Pathways/)

# Next steps 

## Sticking points 

INCLUDE tthings we wanted to do but couldn’t

## Further iterations


#  Team Members
- [Eric Weitz](https://github.com/eweitz): The Broad Institute
- Anne  Deslattes Mays: Founder, Scitechcon LLC
- Lei Ma: Harvard FAS Informatics Group
- [Olaitan I. Awe](https://github.com/laitanawe): Independent Bioinformatics Consultant.
- Peter Fan: Northeastern University Library
- Allie Cliffe: The Broad Institute


