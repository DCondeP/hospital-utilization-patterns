# Hospital Utilization Patterns

Analysis of patient healthcare utilization using machine learning to identify distinct utilization profiles based on intensity, type, and diversity of care.

## Data

The original analytical dataset is not included in this repository because it contains confidential information.

For reproducibility and demonstration purposes, this project uses a synthetic dataset designed to reproduce the general analytical structure of the original dataset without deriving individual records or sensitive information from the original data.

## Problem

Healthcare organizations generate large volumes of data describing how patients use healthcare services. However, individual utilization variables provide only a partial view of these patterns.

The analytical challenge addressed in this project is to identify groups of patients with similar healthcare utilization characteristics and determine whether these groups can be meaningfully characterized using measurable dimensions of healthcare utilization.

## Objective

The objective of this project is to identify and characterize distinct patient healthcare utilization profiles using statistical and machine learning techniques.

The analysis focuses on three dimensions of healthcare utilization:

* **Intensity:** measures related to the volume of healthcare utilization.
* **Type:** characteristics describing how healthcare services are utilized, including hospitalization-related utilization.
* **Diversity:** number of medical specialties involved in patient care.

Additional variables, such as the number of diagnoses, are used to support the characterization and interpretation of the resulting profiles.

## Methodology

The analysis follows these main stages:

1. Data import and validation
2. Exploratory analysis of variable distributions
3. Variable transformation
4. Variable standardization
5. Review and validation of analytical dimensions
6. Evaluation of different numbers of GMM components
7. Cluster size comparison
8. Structural comparison between solutions
9. Assignment confidence assessment
10. Utilization profile characterization
11. Visualization and interpretation of results

### Gaussian Mixture Model

A **Gaussian Mixture Model (GMM)** was used to identify groups of patients with similar healthcare utilization characteristics.

Different numbers of components were evaluated to examine the underlying structure of the population and determine an appropriate level of segmentation.

The resulting profiles were analyzed using quantitative evaluation criteria, cluster size comparisons, transition analysis, assignment confidence, and profile characterization.

## Model Comparison

Two solutions were examined in greater detail:

* **K=6:** captures the main structure of patient healthcare utilization.
* **K=8:** provides a more granular segmentation of specific utilization profiles.

The transition between the two solutions was analyzed to determine whether increasing the number of components substantially changed the underlying structure or primarily divided existing profiles into more specific groups.

## Results

The comparison between the K=6 and K=8 solutions shows a stable clustering structure. Four of the six profiles identified in the K=6 solution remain structurally consistent when the number of components is increased to eight, while the remaining profiles are further divided into more specific segments.

The main refinement occurs among outpatient patients with comprehensive clinical records, where the K=8 solution distinguishes between lower- and higher-intensity healthcare utilization.

A second refinement occurs among hospitalized patients, separating profiles with different levels of clinical characterization.

Overall, the K=6 solution captures the main structure of healthcare utilization, while K=8 provides a more granular segmentation of specific patient groups without substantially changing the broader utilization patterns.

### Cluster Stability

A transition matrix between the K=6 and K=8 solutions was used to examine how patient assignments changed when the number of components increased.

The analysis indicates that most of the structure identified with K=6 is preserved in the K=8 solution. The additional components primarily represent subdivisions of existing profiles rather than entirely new utilization patterns.

### Assignment Confidence

Assignment confidence was evaluated for the K=8 solution to assess how clearly patients were associated with their assigned profiles.

These confidence measures provide additional information for interpreting the resulting segmentation and distinguishing well-defined profiles from observations with greater assignment uncertainty.

## Project Structure

```text
hospital-utilization-patterns/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── README.md
│   └── synthetic_patients.csv
│
├── notebooks/
│   └── 01_hospital_utilization_analysis.ipynb
│
└── results/
    ├── figures/
    └── tables/
```

## Notebook Structure

The analysis notebook is organized into the following sections:

```text
DATA PREPARATION
├── Data Import
├── Dataset Validation
├── Variable Distribution Analysis
├── Variable Transformation
├── Variable Standardization
└── Dimension Review
    └── Index Validation

MODEL DEVELOPMENT
└── Evaluation of Different Numbers of Components

MODEL ANALYSIS
├── Cluster Size Comparison
├── Utilization Profile K=6
├── Utilization Profile K=8
├── Transition Matrix K=6 → K=8
└── Assignment Confidence K=8

PROFILE CHARACTERIZATION
├── Master Profile Table
├── Relative Position
├── Structural Cluster Characterization
└── Variable Visualization

CONCLUSIONS
```

## Reproducibility

The repository includes the synthetic dataset and the analysis notebook required to reproduce the main analytical workflow.

The synthetic data are generated independently from the original confidential dataset. Values and parameters controlling relationships between variables are not derived directly from the original patient records.

A fixed random seed is used to ensure reproducibility of the synthetic dataset.

## Limitations

This project has several limitations that should be considered when interpreting the results:

* The publicly available dataset is synthetic and does not represent individual real-world patients.
* The identified profiles describe statistical patterns of healthcare utilization and should not be interpreted as clinical diagnoses.
* The number of GMM components affects the granularity of the resulting segmentation.
* Cluster interpretation requires domain knowledge in addition to statistical analysis.
* Assignment confidence varies across observations and should be considered when interpreting individual patient profiles.
* The analysis is focused on utilization characteristics and does not attempt to establish causal relationships.

## Conclusions

The analysis demonstrates how unsupervised machine learning can be used to characterize heterogeneous patterns of healthcare utilization.

The comparison of different GMM configurations shows that increasing the number of components can provide additional detail while preserving much of the broader utilization structure.

The resulting profiles provide a quantitative framework for describing differences in healthcare utilization based on measurable characteristics rather than relying exclusively on individual variables.

Further analysis could incorporate temporal information and predictive modeling to study how utilization profiles evolve and whether patient-level utilization patterns can be used to anticipate future healthcare events.
