# Interactive-Analysis-with-Biological-Pathways
The Autopath project explores how to surface biological pathways for two diseases, as a way to make it easier to draw insight from the raw data. Our two case studies are Age-related Macular Degeneration and Systemic Lupus Erythematosus (SLE), a chronic autoimmune disease where the immune system mistakenly attacks healthy tissues and organs, leading to inflammation and damage. 

## Project Objectives - What's the problem?   
How can we leverage existing data to understand and treat disease? 

## Challenges 
- There's too much data and it's too hard to find the right data
- Analysis tools require too much comp bio wrangling and are not user-friendly (for biologists)

## The Solution
- Create a workflow to transform single cell expression data to a visualization of gene pathway enrichment
- Access data where it lives - possibly different “places” -  and analyze collaboratively where it’s most efficient - possibly two different clouds (AWS and GCP).

# Workflow 
![General Workflow](https://github.com/BioITHackathons/Interactive-Analysis-with-Biological-Pathways/blob/main/img/biological-pathways-workflow.jpg)


# Use case: Macular Degeneration 

## Data overview
INCLUDE DATA DESCRIPTION 
- **HRCA: snRNA-seq of the human retina - all cells** ([https://singlecell.broadinstitute.org/single_cell/study/SCP2805/hrca-snrna-seq-of-the-human-retina-all-cells#study-summary](Single Cell Portal))
- 

## Analysis overview

### 1. Identify marker and binary genes (NS Forest batch on AWS)
INCLUDE TOOL DESCRIPTION AND LINK HERE

- **Docker**:
Make sure Docker is installed and actively running in the background.
Verify Docker installation and status using:
  ```bash
  docker --version
  ```

### 2. Gene Set Enrichment Analysis (GSEA) 
INCLUDE ANALYSIS/TOOL DESCRIPTION AND LINK HERE

### 3. Differential Gene Expression (RStudio on Terra)
INCLUDE ANALYSIS/TOOL DESCRIPTION AND LINK HERE

### 4. Render interactive biological pathways diagram
INCLUDE ANALYSIS/TOOL DESCRIPTION AND LINK HERE

## Terra workspace 
LINK TO WORKSPACE AND LINK HERE

# Use case: Lupus 

## Data overview
INCLUDE DATA DESCRIPTION 
- 
- 

## Analysis overview

### 1. Identify marker and binary genes (NS Forest batch on AWS)
INCLUDE TOOL DESCRIPTION AND LINK HERE

- **Docker**:
Make sure Docker is installed and actively running in the background.
Verify Docker installation and status using:
  ```bash
  docker --version
  ```

### 2. Gene Set Enrichment Analysis (GSEA) 
INCLUDE ANALYSIS/TOOL DESCRIPTION AND LINK HERE

### 3. Differential Gene Expression (RStudio on Terra)
INCLUDE ANALYSIS/TOOL DESCRIPTION AND LINK HERE

### 4. Render interactive biological pathways diagram
INCLUDE ANALYSIS/TOOL DESCRIPTION AND LINK HERE

## Usage Gudelines
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

