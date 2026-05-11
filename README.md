# B3Pred: Blood–Brain Barrier Penetrating Peptides Prediction Server

Welcome to the official repository for B3Pred, a machine-learning-based method for predicting and designing blood–brain barrier penetrating peptides (B3PPs). This resource is designed to support researchers in CNS drug delivery, peptide therapeutics, and computational biology.

Web Server: https://webs.iiitd.edu.in/raghava/b3pred/

ZENODO : https://doi.org/10.5281/zenodo.20093418

## Citation

Kumar, V., Patiyal, S., Dhall, A., Sharma, N., & Raghava, G. P. S. (2021).
B3Pred: A Random-Forest-Based Method for Predicting and Designing Blood–Brain Barrier Penetrating Peptides.
*Pharmaceutics*, 13, 1237. https://doi.org/10.3390/pharmaceutics13081237


## About the Method

B3Pred is a computational tool for predicting blood–brain barrier penetrating peptides (B3PPs) to facilitate drug delivery into the brain. B3PPs can act both as therapeutics and as drug delivery vehicles for CNS-related diseases such as Alzheimer's disease, Parkinson's disease, and glioblastoma.

Models were trained, tested, and evaluated on B3PPs obtained from the B3Pdb database, using over 9000 peptide descriptors and multiple machine learning classifiers. The best-performing random-forest model achieved **85.08% accuracy** with an **AUROC of 0.93**.

Data sources integrated include:

* B3Pdb — blood–brain barrier peptide database
* CPPsite 2.0 — cell-penetrating peptide repository
* Swiss-Prot / UniProtKB — for negative dataset generation


## Key Features

**Best Model Performance**

* 85.08% accuracy on training dataset (Dataset_3)
* AUROC of 0.93 (training) and 0.90 (validation)
* Random Forest classifier with top 80 selected features

**Three Datasets for Robust Validation**

* Dataset_1: 269 B3PPs vs. 269 CPPs
* Dataset_2: 269 B3PPs vs. 269 non-B3PPs (Swiss-Prot)
* Dataset_3: 269 B3PPs vs. 2690 non-B3PPs (10× imbalanced)

**Rich Feature Computation**

* 9189 descriptors computed using Pfeature
* 15 feature types: AAC, DPC, RRI, DDOR, CTD, PAAC, APAAC, QSO, TPC, SOCN, and more
* Feature selection via SVC-L1; feature ranking via LightGBM

**Multiple Machine Learning Classifiers**

* Random Forest (RF) — best overall
* XGBoost (XGB)
* Logistic Regression (LR)
* Support Vector Classifier (SVC)
* K-Nearest Neighbors (KNN)
* Gaussian Naive Bayes (GNB)
* Decision Tree (DT)


## Overview

B3Pred provides three functional modules:

* **Predict** — classifies submitted peptide sequences as B3PP or non-B3PP with a confidence score and physicochemical properties
* **Design** — generates all single-residue analogs of an input peptide, scores them, and ranks them to help design optimized B3PPs
* **Scan** — scans a full protein sequence for B3PP-containing regions using a user-specified window length

A standalone software version is also available for large-scale and genome-level screening.


### Amino Acid Composition Insights

Analysis of B3PPs revealed distinct compositional signatures:

* **Arginine** is the most enriched residue in both B3PPs and CPPs — critical for membrane penetration
* **Tyrosine** (aromatic) is uniquely elevated in B3PPs compared to CPPs and random peptides
* **Proline** and **Glycine** are prevalent in B3PPs relative to other peptide classes
* Two Sample Logo (TSL) analysis shows Tyrosine, Glycine, Arginine, and Lysine are preferred across B3PP positions


### Validation Strategy

* 80/20 train–validation split across all datasets
* 5-fold cross-validation on training data (internal validation)
* External validation on held-out 20% test set
* Metrics reported: Sensitivity, Specificity, Accuracy, AUROC, MCC

## Applications

* CNS drug delivery research
* Blood–brain barrier penetration prediction
* Peptide analog design and optimization
* Machine learning model benchmarking
* Neurological disease therapeutic discovery (Alzheimer's, Parkinson's, glioblastoma, epilepsy)
* Antiviral peptide research (e.g., Zika, dengue, COVID-19 neurological complications)


## Contact & Authors

**Prof. Gajendra P. S. Raghava**
raghava@iiitd.ac.in
http://webs.iiitd.edu.in/raghava/

Developed at the Department of Computational Biology,
Indraprastha Institute of Information Technology (IIIT Delhi), India


## License

This resource is distributed under the
Creative Commons Attribution License (CC BY 4.0)
https://creativecommons.org/licenses/by/4.0/


## Acknowledgements

Supported by:

* University Grant Commission (UGC)
* Department of Science and Technology (DST-INSPIRE)
* Department of Biotechnology (DBT), Government of India

We acknowledge all researchers whose experimental data on BBB-penetrating peptides contributed to this work.
