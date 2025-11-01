# 🚗💨 Unsupervised Vehicle Profile Classification and Feature Space Optimization

---

## 💡 1. Project Overview

This project focuses on solving a **vehicle classification problem** for **"Prospect Auto,"** a chain of car repair shops. The company seeks an automated solution to swiftly and accurately differentiate vehicle types for streamlined internal logistics, such as parts inventory and service bay allocation.

The core objective is to develop a robust predictive model capable of differentiating between **three distinct vehicle classes**—a double-decker bus, a Chevrolet van, and a third vehicle (either a Saab 9000 or Opel Manta)—based solely on geometric features extracted from their silhouette profiles.

Unlike previous attempts leveraging supervised learning, this iteration critically explores the efficacy of **unsupervised clustering techniques** for classification. A key focus is the **optimization of the feature space** through **Principal Component Analysis (PCA)** to assess dimensionality reduction's impact on model performance and efficiency.

[Vehicle-Silhouette-Classification-for-Prospect-Auto](https://github.com/hgabrali/Vehicle-Silhouette-)
---

## 📊 2. Dataset Description

The analysis utilizes the established **Cars Silhouette Dataset**. This dataset comprises **18 highly specific, numeric, and continuous features** derived from the silhouettes of vehicles captured at various angles.

| Feature Type | Detail |
| :--- | :--- |
| **Input Features (18)** | Geometric parameters, including aspect ratios, boundary box measurements, scale factors, and moments. All features are numeric. |
| **Target Classes (3)** | Bus (double-decker), Van (Chevrolet), and Car (Saab 9000 / Opel Manta). |

---

## ⚙️ 3. Project Workflow and Methodology

The project adheres to a rigorous data science methodology, with a specialized focus on unsupervised techniques and dimensionality reduction.

### 🧹 3.1 Data Preparation

* **Library Importation:** Importation of necessary Python libraries (`pandas`, `numpy`, `sklearn`, etc.).
* **Data Loading:** Reading the dataset from the provided source.
* **Data Preprocessing:**
    * **Normalization & Standardization:** Applying scaling techniques to ensure all geometric features contribute equally to the distance metrics used in clustering algorithms.
    * **Train/Test Split:** Partitioning the dataset into training and testing subsets to validate the final model's generalization capabilities, even for clustering-based validation.

### 🔬 3.2 Dimensionality Reduction Assessment (PCA)

* **Principal Component Analysis (PCA):** Implementation of PCA on the scaled feature set to identify the intrinsic dimensionality of the data.
* **Variance Preservation Analysis:** Determine the minimum number of principal components required to retain a high percentage (e.g., 90% to 95%) of the original data's variance.
* **Conclusion on Efficiency:** Evaluate the trade-off between reduced complexity and information loss to conclude whether dimensionality reduction is a beneficial preprocessing step for this specific problem.

### 🧩 3.3 Unsupervised Classification (Clustering)

* **Clustering Algorithm Implementation:** Application of suitable unsupervised clustering algorithms (e.g., **K-Means, DBSCAN, or hierarchical clustering**) to group the data points into the expected three vehicle classes.
* **Optimization:** Parameter tuning to achieve the optimal cluster assignment.

### ✅ 3.4 Model Evaluation

* **Clustering Metrics:** Evaluation of the unsupervised model's performance using **internal metrics** (e.g., Silhouette Score, Davies–Bouldin Index) and **external metrics** where applicable (using the original labels as ground truth), such as:
    * Adjusted Rand Index (ARI)
    * Homogeneity, Completeness, and V-measure

---

## ⚖️ 4. Final Comparative Analysis

The project's final and most critical phase is a comparative discussion that addresses Prospect Auto's core need:

* **Efficacy of Unsupervised Learning:** Detailed assessment of how well the clustering solution performs in distinguishing the three vehicle classes, particularly in the context of the high-dimensional silhouette data.
* **Supervised vs. Unsupervised Paradigm:** A conclusive statement determining which approach—the current unsupervised method or the previously employed supervised method—yields the superior and most reliable classification performance for the Prospect Auto requirement, supported by a comparison of key performance metrics.

---

## 💻 5. Technical Stack

| Category | Tool / Library |
| :--- | :--- |
| **Language** | Python 3.x |
| **Data Manipulation** | Pandas, NumPy |
| **Machine Learning** | Scikit-learn (PCA, Standard Scaler, K-Means) |
| **Visualization (Recommended)** | Matplotlib, Seaborn |
