#This project examines gene expression data first made available by the TCGA Pan Cancer analysis project, and included in the UCI Machine Learning Repository, including a multi-class outcome. This outcome is the ‘dependent variable’ that we want to be able to accurately predict using a trained model. The source data has been sampled so that there is enough data for us to train models, without being too bulky to easily store locally or in the cloud. In total it includes 801 instances (i.e. samples/rows), and 20,531 gene expression features (i.e. independent variables/columns), and 5 cancer subtypes as the multi-class outcome (with class imbalance). Given that this is real-world data it is uncertain how many predictive vs. non-predictive features are in this dataset, however previous analysis of this dataset indicates that models can be trained on this data with high predictive accuracy.

The primary goals of this project are to (1) utilize unsupervised learning approaches to explore relationships between gene expression features in this data, and (2) utilize supervised learning approaches to classify cancer type based on the gene expression features. 

Unsupervised learning approaches could, for example, include dimensionality reduction (such as principal component analysis), and clustering (comparing instances in discovered clusters to the true class labels of cancer subtypes.

Supervised learning approaches could, for example, include applying multi-class machine learning modeling with any number of potential algorithms (e.g. decision tree, random forests, support vector machines, artificial neural networks, etc.), as well as strategies for feature learning and feature selection.

Ultimately the challenge is to assemble unsupervised and/or supervised learning elements into an analysis pipeline to examine relationships between features and outcome in order to achieve the best prediction performance possible. In other words: What ML algorithm or algorithm(s) perform best? Also, what is the most effective way to set up a data analysis/machine learning pipeline that adheres to best practices in data science?

A secondary goal of this project is to seek to explain or interpret the models or findings from this analysis (e.g. model feature importance estimation). In other words:  What gene expression features are most important for driving accurate model performance, vs. features likely to be non-predictive or include redundant information?

As a simpler starting point, as well as to be able to try out the Automated Machine Learning Tool, ‘STREAMLINE’ (which as of 3/14/24 only handles binary classification), this gene expression dataset could also be encoded as a binary classification problem, with BRCA encoded as class 0 and all other classes encoded as class 1. This effectively changes the classification task to ask: How well can the BRCA cancer subtype be distinguished from the other four?

Further, while the gene expression features in the included dataset are given dummy names the original probe names are available through external sites, which can allow exploration of the biological relevance of the findings. Analyses such as gene-set enrichment could be conducted, for example.

 

Abstract from the UCI Dataset Repository

This collection of data is part of the RNA-Seq (HiSeq) PANCAN data set, it is a random extraction of gene expressions of patients having different types of tumor: BRCA, KIRC, COAD, LUAD and PRAD.

 

Abstract from the Original Publication (Weinstein et al., 2013):

The Cancer Genome Atlas (TCGA) Research Network has profiled and analyzed large numbers of human tumors to discover molecular aberrations at the DNA, RNA, protein and epigenetic levels. The resulting rich data provide a major opportunity to develop an integrated picture of commonalities, differences and emergent themes across tumor lineages. The Pan-Cancer initiative compares the first 12 tumor types profiled by TCGA. Analysis of the molecular aberrations and their functional roles across tumor types will teach us how to extend therapies effective in one cancer type to others with a similar genomic profile.

 

Dataset Sources:

Dataset files are included in the folder ‘data’ (please scroll down to the bottom of this page). Once this project is downloaded and unzipped, these datasets are ready to work with. 

These data files are alternatively available from the UCI repository: https://archive.ics.uci.edu/dataset/401/gene+expression+cancer+rna+seq

From the UCI repository the data is downloaded as the file: TCGA-PANCAN-HiSeq-801x20531.tar

To work with this alternative file download, first extract the dataset from the ‘.tar’ file.  For example, you can unzip the .tar file, as well as secondary .tar file that is unpacked to get the two underlying data files (‘data.csv’, and ‘labels.csv’).

The original data in its entirety can also be downloaded. This dataset includes original probe names, but is a good deal larger and more difficult to work with: https://www.synapse.org/#!Synapse:syn4301332

 

Dataset Information:

‘data.csv’ includes the ‘X’ part of the dataset (i.e., rows of instances, identified by sample identifier, and columns of gene expression features)

‘labels’ includes the ‘y’ part of the dataset (i.e., rows of class-outcome, also identified by the same sample identifier)

It may be useful to start by merging these two elements together into a single dataset or dataframe (in pandas).

Samples (instances) are stored row-wise. Variables (features) of each sample are RNA-Seq gene expression levels measured by illumina HiSeq platform. There are no missing values.

A dummy name (gene_XX) is given to each feature. Check the original data from www.synapse.org or the platform specs for the complete list of probes name. The features are ordered consistently with the original data.

 

Cancer Subtypes in the Dataset (Multi-class outcomes)

• BRCA: Breast Invasive Carcinoma

• KIRC: Kidney Renal Clear Cell Carcinoma

• COAD: Colon Adenocarcinoma

• LUAD: Lung Adenocarcinoma

• PRAD: Prostate Adenocarcinoma
