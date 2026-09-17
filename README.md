# hospital-utilization-patterns
Analysis of patient healthcare utilization using machine learning to identify distinct utilization profiles based on intensity, type, and diversity of care.

The original dataset is not included because it contains
confidential information.

For demonstration purposes, the repository uses synthetic data
with the same general structure as the analytical dataset.

## Problem

Healthcare organizations generate large volumes of data related to
patient utilization. However, utilization patterns are not always
easy to characterize using individual variables.

This project explores whether patients can be grouped according to
their observed healthcare utilization characteristics.

## Objective

The objective of this project is to identify distinct patient
utilization profiles using statistical and machine learning
techniques.

The analysis considers dimensions such as:

- Number of episodes
- Hospitalization rate
- Number of specialties involved
- Number of diagnoses

  ## Methodology

The project follows the following analytical workflow:

1. Data cleaning
2. Exploratory data analysis
3. Feature selection
4. Feature scaling
5. Gaussian Mixture Model training
6. Model evaluation
7. Patient profile characterization
8. Clinical interpretation

### Model

A Gaussian Mixture Model (GMM) was used to identify groups of
patients with similar healthcare utilization characteristics.

Different numbers of components were evaluated using quantitative
model evaluation criteria and the resulting profiles were analyzed
for interpretability.
