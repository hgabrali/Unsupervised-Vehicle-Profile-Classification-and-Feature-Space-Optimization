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

## 💡 Why Standardization is Crucial for Clustering

Clustering algorithms like K-Means rely on calculating the distance between data points (e.g., Euclidean distance). If the features are not scaled, the distance calculation will be overwhelmingly influenced by features with the largest magnitudes, effectively ignoring the contribution of features with smaller ranges. Standardization neutralizes this effect.

# 📉 Dimensionality Reduction Assessment (PCA)

## 🎯 Variance Retention Analysis

This table summarizes the analysis conducted using **Principal Component Analysis (PCA)** on the standardized vehicle features. The goal was to determine the minimum number of principal components required to retain a high percentage of the original data's variance.

| Component Count | Cumulative Explained Variance | Conclusion on Information Retention |
| :--- | :--- | :--- |
| **1** | 0.380 | Retains 38.0% of the total variance. |
| **2** | 0.584 | Retains 58.4% of the total variance. |
| **3** | 0.730 | Retains 73.0% of the total variance. |
| **4** | 0.817 | Retains 81.7% of the total variance. |
| **5** | 0.865 | Retains 86.5% of the total variance. |
| **6** | 0.897 | Retains 89.7% of the total variance. |
| **7** | 0.925 | Retains 92.5% of the total variance. |
| **8** | 0.941 | Retains 94.1% of the total variance. |
| **9** | 0.954 | Retains 95.4% of the total variance. |
| **10** | 0.966 | Retains 96.6% of the total variance. |
| **11** | 0.975 | Retains 97.5% of the total variance. |
| **12** | 0.982 | Retains 98.2% of the total variance. |
| **13** | 0.987 | Retains 98.7% of the total variance. |
| **14** | 0.992 | Retains 99.2% of the total variance. |
| **15** | 0.995 | Retains 99.5% of the total variance. |
| **16** | 0.998 | Retains 99.8% of the total variance. |
| **17** | 0.999 | Retains 99.9% of the total variance. |
| **18** | 1.000 | Retains 100% of the total variance. |

---

## ✅ Key Insights

* **90% Variance Threshold:** Only **7 components** are needed to retain over 90% ($\mathbf{92.5\%}$) of the original data variance.
* **95% Variance Threshold:** Only **9 components** are needed to retain over 95% ($\mathbf{95.4\%}$) of the original data variance.
* **Efficiency:** Reducing the 18-dimensional feature space to **9 dimensions** while preserving over 95% of the information is a strong justification for implementing PCA before clustering to improve model efficiency and reduce noise.

# 💾 PCA Data Projection Summary

## 🔄 Transforming the Dataset

Following the analysis that determined the optimal number of components required to retain variance (95% retention achieved with 9 components), this section details the projection of the scaled data onto the reduced feature space.

| Step | Data Set | Original Shape (Features) | Target Shape (Components) | Description |
| :--- | :--- | :--- | :--- | :--- |
| **1. PCA Initialization** | N/A | 18 | **9** | PCA model is re-initialized and fitted to the training set, setting `n_components=9` to capture 95.4% of the variance. |
| **2. Training Data Projection** | $\mathbf{X_{train}}$ | (676, 18) | **(676, 9)** | The standardized training features are transformed (projected) onto the 9 principal components. This reduced data set is used for clustering. |
| **3. Testing Data Projection** | $\mathbf{X_{test}}$ | (170, 18) | **(170, 9)** | The standardized testing features are transformed using the *same* PCA model fitted on $X_{train}$. This ensures consistency and prepares the testing data for model validation. |
| **4. Final Training Features** | $\mathbf{X_{train\_pca}}$ | N/A | **(676, 9)** | The final training set ready for Unsupervised Clustering (e.g., K-Means). |
| **5. Final Testing Features** | $\mathbf{X_{test\_pca}}$ | N/A | **(170, 9)** | The final testing set reserved for robust model evaluation. |

---

## 🚀 Impact of Dimensionality Reduction

Reducing the dimensionality from **18 features** to **9 principal components** is a critical optimization:

* **Efficiency:** Significantly reduces the computational load and training time for the subsequent clustering algorithms.
* **Noise Reduction:** Helps mitigate the impact of multicollinearity and noise inherent in the original 18-dimensional feature space, potentially leading to purer clusters.
