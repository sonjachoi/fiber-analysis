# Project Overview

This repository contains analysis notebooks, data, and automation scripts for throughput analysis and FRD (focal ratio degradtaion) setup automation.


## Notebooks

1. **`plot_throughput.ipynb`**:  
   This notebook visualises the throughput data. It takes input data and produces graphs.

2. **`frd-setup-automation.ipynb`**:  
   This notebook automates the FRD setup and takes far field images of the fiber output end.

3. **`frd-analysis.ipynb`**:  
   This notebook analyses the images taken by frd-setup-automation.ipynb.


   
## Automation with Snakemake

The project uses **Snakemake** to automate the execution of notebooks and workflows. There are two Snakemake files:

### 1. **`Snakefile-throughput`**:  
   This file automates the execution of the **`plot_throughput.ipynb`** notebook. 

### 2. **`Snakefile-frd`**:  
   This file automates the execution of both **`frd-analysis.ipynb`** and **`frd-setup-automation.ipynb`** notebooks. 
   

## Prerequisites

Make sure you have the following dependencies installed before running the notebooks or Snakemake workflows:

- Python 3.x
- Jupyter Notebook
- Snakemake
- Required Python libraries (see individual notebooks for specific dependencies)


## Running the notebooks

# How to Run Throughput Tests:
1. Use Snakefile-onlythroughput 
2. Do $ snakemake --snakefile Snakefile-onlythroughput 

# How to Run FRD Tests:
1. Use Snakefile-onlyfrd
2. Do $ snakemake --snakefile Snakefile-onlyfrd 


- When running the FRD test, you may get the following error: 
```bash
WildcardError in rule all in file /Users/sonjachoi/Desktop/astr501-lab/final_project/fiber1/Snakesnake, line 2:
Wildcards in input files cannot be determined from output files: (rule all, line 2, /Users/sonjachoi/Desktop/astr501-lab/final_project/fiber1/Snakesnake)
'date'
```
or, 
```bash
Complete log: .snakemake/log/2024-12-03T210102.212112.snakemake.log
WorkflowError:
At least one job did not complete successfully.
```
- This may be due to the connection to the experiment set up is lost, please double check the serial connection port. 
