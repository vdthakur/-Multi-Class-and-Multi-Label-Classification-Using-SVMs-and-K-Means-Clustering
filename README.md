# Multi-Class and Multi-Label Classification Using Support Vector Machines and K-Means Clustering

This repository contains an analysis of multi-class and multi-label classification and clustering tasks using the **Anuran Calls (MFCCs) Dataset**. The project explores Support Vector Machines (SVMs) for classification and K-Means for clustering, with a focus on handling class imbalance and evaluating multi-label metrics.

---

## Table of Contents

- [Introduction](#introduction)
- [Data](#data)
- [Project Tasks](#project-tasks)
  - [Multi-Class and Multi-Label Classification Using SVMs](#multi-class-and-multi-label-classification-using-svms)
  - [K-Means Clustering on Multi-Class and Multi-Label Data](#k-means-clustering-on-multi-class-and-multi-label-data)
- [Results](#results)

---

## Introduction

This project investigates:
1. Multi-class and multi-label classification using SVMs with various kernels and penalties.
2. Class imbalance handling using techniques like SMOTE.
3. Clustering analysis with K-Means, focusing on label consistency within clusters.

---

## Data


### Dataset Details:
- **Attributes**: MFCC (Mel Frequency Cepstral Coefficient) features of frog calls.
- **Labels**: Three hierarchical levels: Family, Genus, and Species.
- **Objective**:
  - Multi-label classification: Predict Family, Genus, and Species.
  - Clustering: Group instances and evaluate label consistency.

---

## Project Tasks

### Multi-Class and Multi-Label Classification Using SVMs

1. **Data Splitting**:
   - Randomly split the dataset into 70% training and 30% testing sets.

2. **Binary Relevance for Multi-Label Classification**:
   - Train an independent SVM classifier for each label (Family, Genus, Species).

3. **Evaluation Metrics**:
   - Research and apply:
     - **Exact Match**: Percentage of instances where all labels match the true labels.
     - **Hamming Score and Loss**: Measure agreement/disagreement across multiple labels.

4. **Gaussian Kernel SVM**:
   - Use Gaussian kernels and one-vs-all classifiers.
   - Tune the SVM penalty (\( \lambda \)) and Gaussian kernel width (\( \sigma \)) using 10-fold cross-validation.
   - Report results with both standardized and raw features.

5. **L1-Penalized SVM**:
   - Train SVMs with an L1 penalty using a linear kernel.
   - Standardize the attributes.
   - Use 10-fold cross-validation to determine the best penalty weight.

6. **Class Imbalance Handling**:
   - Use SMOTE or other techniques to address class imbalance.
   - Retrain the SVMs with the pre-processed data and compare results.

7. **Classifier Chain (Extra Practice)**:
   - Research and apply the **Classifier Chain** method for multi-label classification.
   - Compare its performance with Binary Relevance.

8. **Additional Evaluation Metrics (Extra Practice)**:
   - Research how metrics like Confusion Matrix, Precision, Recall, ROC, and AUC are defined for multi-label classification.
   - Compute these metrics for the trained classifiers.

---

### K-Means Clustering on Multi-Class and Multi-Label Data

1. **Clustering**:
   - Apply K-Means clustering to the full dataset (no train-test split).
   - Automatically determine \( k \) (number of clusters) using:
     - CH (Calinski-Harabasz), Gap Statistics, Scree Plots, or Silhouettes.

2. **Label Analysis**:
   - For each cluster, determine the majority label for Family, Genus, and Species.

3. **Cluster Evaluation**:
   - Assign each cluster a majority label triplet (Family, Genus, Species).
   - Evaluate clustering performance using:
     - **Hamming Distance**: Average number of label mismatches per instance.
     - **Hamming Score**: Proportion of correct label matches.
     - **Hamming Loss**: Proportion of label mismatches across all labels.

4. **Monte Carlo Simulation**:
   - Repeat the clustering process 50 times.
   - Report the average and standard deviation of the Hamming Distance, Score, and Loss.

---

## Results

- **SVM Classifiers**:
  - Comparison of Gaussian kernel and L1-penalized SVMs.
  - Effectiveness of class imbalance techniques like SMOTE.
- **K-Means Clustering**:
  - Optimal \( k \) determined using CH, Gap Statistics, or Silhouettes.
  - Consistency of Family, Genus, and Species labels within clusters.
- **Monte Carlo Results**:
  - Stability of clustering results across multiple iterations.


