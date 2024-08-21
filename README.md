# Gene Expression Analysis of RNA-seq in Bronchial Tissue: Premalignant Lung Lesions and Current Smoking Status

[View the whole analysis here](https://emmajslz.github.io/ge-analysis-bronchial-tissue/ge-analysis.html)

## Reproducing the project

To run the R notebook (ge-analysis.Rmd), clone the repository using

`git clone https://github.com/emmajslz/ge-analysis-bronchial-tissue.git`

To ensure all the necessary packages are available, use `renv` to create a new R environment with all the required packages, as listed in the file `renv.lock`

1. Install renv (if it's not already installed). Run the following on the R console.

`install.packages("renv")`

2. Activate the `renv` environment:

Navigate to the root directory of your cloned repository and activate the `renv` environment using:

`renv::activate()`

3. Restore the environment

After activating renv, restore the project's R environment using the renv.lock file.
This will install all the necessary packages specified in the lock file.

`renv::restore()`

Once the environment is restored, you can start using the project.
All package installations and updates will be managed by renv within this isolated environment.

## The analysis

### Introduction

Lung cancer is the leading cause of cancer-related death in the United States. The molecular events preceding the onset of disease are poorly understood, and no effective tools exist to identify smokers with premalignant lesions (PMLs) that will progress to invasive cancer. Previous research has identified molecular changes in the smoke-exposed airways. However, the focus of the paper “Detecting the Presence and Progression of Premalignant Lung Lesions via Airway Gene Expression” Beane et al. (2017) shifts the focus to the first stages of the disease progress. They utilize samples from the same airway field of injury to study PMLs and their potential in preventing lung cancer.

The researchers’ goal is to profile samples extracted from normal appearing bronchial mucosa by mRNA-Seq, and attempt to find differentially expressed gene sets and pathways between subjects with PMLs and without PMLs. From the original 82 samples, 50 subjects had PML, 25 didn’t, and 7 were excluded in the end.

The resulting raw RNA-seq data has been deposited at the Gene Expression Omnibus (GEO), where they are publicly available under accession GSE79209.

In this analysis, we attempted to formulate a new question to answer, using the dataset of the mentioned paper.

We’ll perform an Exploratory Data Analysis of the corresponding RNA-seq gene expression profiles generated as a table of counts using the DEE2 (https://dee2.io) pipeline by Ziemann, Kaspi, and El-Osta (2019), and further packaged into a SummarizedExperiment object with genes mapped to Entrez identifiers. This object also stores the phenotypic information about the profiled samples that has been also made available at GEO.

The EDA will allow us to look further into the dataset and have enough information for a new Experimental Design. Hierarchical clustering and batch identification will assist us in choosing a new way to group the 82 samples, with the goal of finding differentially expressed genes. We will perform functional enrichment analysis to analyse high-throughput experimental results in order to discover biological annotations that are over-represented in the list of DE genes.

### Analysis structure

The project has the following different parts:

1. Introduction
2. Quality Assessment
3. Differential Expression
4. Functional Analysis
5. Discussion
6. Conclusions
7. Session Information
References

### Conclusions

Differential Expression and Functional Analysis allowed us to identify differentially expressed genes and pathways between current smokers and former smokers, as well as samples with damaged lung tissue (dysplasia) vs. healthy lung tissue (no dysplasia).

We wanted to gain some insight into the effects of smoking on the airway, and whether or not there is significance in smokers vs. people that quit smoking. The fact that there is very significant differential expression between these groups, and that there are pathways that are differentially expressed, tells us that there are significant changes to the genome once the smoking stops. Comparing it to dysplasia status, and seeing so many pathways that are differentially expressed in one classification as well as the other, could indicate there’s a correlation between Histology degree and the smoking habit.

In our analysis of the effects of smoking on cellular functions using Differential Expression (DE), Gene Ontology (GO), and Gene Set Enrichment Analysis (GSEA) on RNA-seq data, we discovered significant molecular alterations between current and former smokers, and individuals with and without dysplasia.

Even though our process did yield significant results, we think it’s still superficial. We could add to this analysis by also sequencing genome from samples that never smoked, or try and go further into the changes the genome goes through once one stops smoking. We think this is a very relevant topic seeing as smoking is still really prevalent, and lung cancer is one of the leading causes of death in the United States.


