# ⚙️ Data Preprocessing Pipeline Summary

This document summarizes the core data preparation steps taken to ensure the vehicle silhouette data is optimized and ready for **distance-based clustering algorithms**.

---

## 🧹 Key Preprocessing Steps

| Step | Goal & Method | Technical Detail |
| :--- | :--- | :--- |
| **1. Missing Value Imputation** | To address data integrity issues (NaNs) in the numerical features. | **Median Strategy** was used. This is a robust method, preferred when the data might contain outliers, as the median is less sensitive to extreme values than the mean. |
| **2. Feature Standardization** | To ensure all 18 geometric features contribute equally to the distance metrics in clustering. | Applied **StandardScaler** ($\mathbf{Z-Score}$). Features are transformed to have a mean ($\mu$) of $\mathbf{0}$ and a standard deviation ($\sigma$) of $\mathbf{1}$. This prevents features with larger initial ranges from dominating the analysis. |
| **3. Train/Test Split** | To partition the dataset for rigorous model development and validation. | The cleaned and scaled dataset was split into an **80% training set** and a **20% testing set**. |

---

## 📊 Data Partition Details

The final partitioning resulted in the following dataset sizes:

* **Training Set (80%):** **676 samples** (Used for clustering model development and parameter tuning).
* **Testing Set (20%):** **170 samples** (Reserved for final model performance assessment and generalization validation).

---

# 💻 Technical Explanation: Data Preprocessing

* This code block executes the critical steps required to prepare the raw vehicle silhouette data for the subsequent machine learning pipeline, specifically ensuring the data is suitable for distance-based algorithms like K-Means clustering.

## 1. Feature and Target Separation

* The feature set ($\mathbf{X}$) is created by dropping the categorical target variable ('class') from the DataFrame (df_veh). The target variable ($\mathbf{y}$) is saved separately. Although this project uses unsupervised learning, $\mathbf{y}$ is retained for calculating external clustering validation metrics such as the Adjusted Rand Index (ARI).


## 2. Missing Value Imputation (Median Strategy)

* Missing values (NaNs) in the feature set ($\mathbf{X}$) are handled using the SimpleImputer. The median strategy is chosen because the median is less sensitive to outliers compared to the mean, offering a more robust estimation for the geometric features. The imputer is fitted and transformed on $\mathbf{X}$, and the result is cast back to a DataFrame.


* The data is standardized using the StandardScaler to transform the features to a $\mathbf{Z-score}$ distribution, where each feature has a mean ($\mu$) of $\mathbf{0}$ and a standard deviation ($\sigma$) of $\mathbf{1}$. This is vital for clustering algorithms, as it ensures all 18 features contribute equally to the distance metrics, preventing features with large magnitudes from artificially dominating the clustering process.

## 4. Train/Test Split (80/20)

* The fully cleaned and scaled data ($\mathbf{X_{scaled\_df}}$ and $\mathbf{y}$) is partitioned into training (80%) and testing (20%) subsets. The $\mathbf{X_{train}}$ set (features) will be used to fit the K-Means clustering model. The $\mathbf{X_{test}}$ set is reserved as an unseen data subset for final, unbiased evaluation of the clustering solution's generalizability. The random_state=42 ensures the split is reproducible.

## 💡 Why Standardization is Crucial for Clustering

Clustering algorithms like K-Means rely on calculating the distance between data points (e.g., Euclidean distance). If the features are not scaled, the distance calculation will be overwhelmingly influenced by features with the largest magnitudes, effectively ignoring the contribution of features with smaller ranges. Standardization neutralizes this effect.

---

# 📉 Principal Component Analysis (PCA) Results

<img width="879" height="525" alt="image" src="https://github.com/user-attachments/assets/c4d568b8-d619-4827-9297-9b97074eb7db" />


## 💡 Overview
PCA was applied to the **18 standardized features** of the training set to identify the intrinsic dimensionality of the data while preserving the majority of the variance.

---

## 1. Variance Preservation Analysis 📊

The cumulative explained variance ratios show the trade-off between complexity (number of components) and information loss (variance retained).

| Variance Threshold | Required Components (N) | Variance Retained | Implication |
| :--- | :--- | :--- | :--- |
| **90%** | **5** | **91.4%** | Significant dimensionality reduction is possible while maintaining high fidelity. |
| **95%** | **7** | **96.2%** | **7 components** are sufficient to preserve almost all (96.2%) of the relevant information. |

---

## 2. Conclusion on Efficiency 🚀

**PCA is highly beneficial for this specific clustering problem.**

* **Original Feature Space Size:** 18 dimensions.
* **Optimal Reduced Space Size:** **7 components**.

By choosing 7 components (a reduction of **61%** from 18 features), we retain **over 96%** of the information content.

### Benefits of Dimensionality Reduction:

1.  **Improved Model Efficiency:** Substantially reduces the computational load and training time for the subsequent clustering algorithms.
2.  **Noise Reduction:** Likely mitigates noise and multicollinearity in the feature space.
3.  **Cleaner Results:** Expected to lead to **cleaner and more interpretable clustering results** by focusing on the most informative axes of the data.

---

*The visual representation of this analysis is typically provided in a **Scree Plot**, which graphically confirms that the curve flattens significantly after the 7th component.*
