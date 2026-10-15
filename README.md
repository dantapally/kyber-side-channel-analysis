# ML-Based Side-Channel Leakage Detection in CRYSTALS-Kyber (PQC)

A machine learning-based approach for detecting and analyzing side-channel leakage in CRYSTALS-Kyber (ML-KEM) implementations using power trace analysis.

## Overview

CRYSTALS-Kyber, standardized by NIST as ML-KEM, is a post-quantum cryptographic algorithm designed to protect key encapsulation against quantum computing threats. However, practical hardware implementations may expose sensitive information through physical side channels, such as power consumption.

This project investigates power-based side-channel leakage in Kyber's Number Theoretic Transform (NTT) implementation using correlation analysis and machine learning techniques.

The project focuses on:

- Establishing Correlation Power Analysis (CPA) as a baseline for leakage detection.
- Identifying Points of Interest (POIs) associated with potential leakage.
- Applying machine learning classifiers to distinguish between leaking and mitigated traces.
- Evaluating a targeted noise-based countermeasure for reducing detectable leakage.

## Objectives

- Analyze power traces associated with Kyber NTT operations.
- Investigate correlations between power consumption and intermediate computational values.
- Identify time samples that exhibit potential side-channel leakage.
- Evaluate machine learning models for leakage detection.
- Assess the effectiveness of targeted noise injection as a leakage mitigation technique.

## Repository Structure

```text
kyber-side-channel-analysis/
├── kyber.ipynb
├── requirements.txt
└── README.md
```

## Methodology

### 1. Power Trace Analysis
Analyze the available power traces collected during Kyber NTT execution to investigate possible data-dependent leakage.

### 2. Correlation Power Analysis (CPA)
Use correlation-based analysis to examine relationships between observed power samples and modeled intermediate values.

### 3. Points of Interest (POI) Selection
Identify time samples with stronger correlations to relevant intermediate computations to localize potential leakage.

### 4. Machine Learning-Based Detection
Apply machine learning classifiers, including:

- Random Forest
- Support Vector Machine (SVM)

Use selected power trace features to evaluate the models' ability to distinguish between the evaluated trace classes.

### 5. Countermeasure Evaluation
Investigate targeted Gaussian noise injection at selected Points of Interest and compare leakage detection results before and after mitigation.

## Experimental Results

The reported experimental results are summarized below.

| Model | Before Mitigation | After Mitigation |
|---|---:|---:|
| Random Forest | 77.00% | 53.67% |
| SVM | 69.17% | 53.83% |

The experiments also reported an approximately 72% reduction in the leakage score after targeted POI suppression.

These results suggest that the evaluated countermeasure reduced the classifiers' ability to distinguish the tested trace classes. Accuracy close to 50% alone does not prove that all side-channel leakage has been eliminated.

## Technologies Used

- Python
- NumPy
- Pandas
- SciPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

## Installation and Usage

### Prerequisites

Install Python and ensure that pip is available.

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run the Project

1. Clone or download this repository.
2. Install the required dependencies.
3. Open `kyber.ipynb` using Jupyter Notebook or JupyterLab.
4. Run the notebook cells sequentially, ensuring that any required datasets are available.

## Dataset Availability

The power traces and related cryptographic data are not included in this repository because the dataset was provided as part of the IIT Kanpur Hardware Security Challenge (HSC).

Running the complete analysis may require access to the original dataset and the corresponding input files.

## Project Context

This project was conducted as part of the IIT Kanpur Hardware Security Challenge (HSC), focusing on side-channel leakage analysis in CRYSTALS-Kyber / ML-KEM implementations.

The work combines correlation-based cryptanalysis, machine learning, and countermeasure evaluation to study implementation-level security risks in post-quantum cryptography.


## Author

**Pavani Dantapalli**  
B.Tech — CSE (Cybersecurity)  
Geethanjali College of Engineering and Technology
