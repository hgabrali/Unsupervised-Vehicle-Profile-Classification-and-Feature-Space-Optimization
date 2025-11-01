#  Data Preparation


<img width="869" height="509" alt="image" src="https://github.com/user-attachments/assets/79f251ec-bc82-4c0b-b6d0-f6d56e0ac50b" />

## Distribution of Vehicle Classes 💜🚗🚌

This bar chart visualizes the frequency count for three distinct vehicle classes in the dataset.

| Class (X-axis) | Count (Y-axis) | Description |
| :--- | :---: | :--- |
| **van** | $\approx 200$ | Represents the lowest frequency in the dataset. |
| **car** | $\approx 420$ | Represents the **highest frequency** (the mode) in the dataset, dominating the distribution. |
| **bus** | $\approx 220$ | Represents a moderate frequency, higher than 'van' but significantly lower than 'car'. |

---
**Key Findings:**
* The 'car' class is the most frequent, with a count of approximately 420.
* The 'van' class is the least frequent, with a count of exactly 200.
* The total number of samples displayed in the chart is approximately $200 + 420 + 220 = 840$.


<img width="862" height="498" alt="image" src="https://github.com/user-attachments/assets/d7443858-5342-4be7-8027-3aa7e2761cd0" />

## Compactness vs. Circularity by Class 📊🔍

This scatter plot visualizes the relationship between the 'Compactness' (X-axis) and 'Circularity' (Y-axis) features, segmented by three vehicle classes: **van**, **car**, and **bus**.

### 📉 Axes and Data Range
* **X-axis (Compactness):** Ranges approximately from 75 to 120.
* **Y-axis (Circularity):** Ranges approximately from 30 to 60.

### 📌 Class Representation (Legend)
| Class | Symbol | Color |
| :--- | :---: | :--- |
| **van** | $\bullet$ (Filled Circle) | Darkest Purple |
| **car** | $\times$ (Cross) | Mid-tone Purple |
| **bus** | $\square$ (Square) | Lighter Purple |

### 💡 Key Distribution Findings
1.  **Positive Correlation:** There appears to be a **weak to moderate positive correlation** between Compactness and Circularity across the entire dataset; as Compactness increases, Circularity also tends to increase slightly.
2.  **'Van' Class ($\bullet$):**
    * Tends to cluster in the **lower-middle** region of the plot.
    * Mostly occupies the **lower Compactness** range (approx. 80 to 100) and **lower Circularity** range (approx. 35 to 45).
3.  **'Car' Class ($\times$):**
    * Shows a **wide distribution** across the plot, especially in the **mid-to-high Circularity** range (approx. 40 to 58).
    * It dominates the high Compactness and high Circularity region (e.g., Compactness > 100, Circularity > 50).
4.  **'Bus' Class ($\square$):**
    * Exhibits a distribution similar to 'car' but is slightly more spread out in the **middle and upper** parts of the Circularity range.
    * It also extends into the highest Compactness values (near 120).
5.  **Overlapping:** There is **significant overlap** among all three classes in the central region (Compactness $\approx 90-100$, Circularity $\approx 40-50$), indicating that these two features alone may not provide perfect separation for classification tasks.


<img width="1027" height="576" alt="image" src="https://github.com/user-attachments/assets/6c06848c-93d2-4f18-afec-fe7f9a06750c" />

## Radius Ratio Distribution by Vehicle Class  📊📏

This box plot visualizes the statistical distribution of the 'Radius Ratio' feature, segregated by three distinct vehicle classes: **van**, **car**, and **bus**.

### 📈 Approximate 5-Number Summary by Class

| Statistic | van (Darkest) | car (Mid-tone) | bus (Lightest) |
| :--- | :---: | :---: | :---: |
| **Minimum (Lower Whisker)** | $\approx 105$ | $\approx 105$ | $\approx 110$ |
| **Q1 (25th Percentile)** | $\approx 135$ | $\approx 160$ | $\approx 140$ |
| **Median (Q2 / 50th Percentile)** | $\approx 150$ | $\approx 185$ | $\approx 170$ |
| **Q3 (75th Percentile)** | $\approx 155$ | $\approx 205$ | $\approx 190$ |
| **Maximum (Upper Whisker)** | $\approx 175$ | $\approx 235$ | $\approx 250$ |
| **Outliers (Above Max)** | Yes (3 points: $\approx 230, 248, 305, 315$) | No | No (Only 1 point: $\approx 80$) |

### 💡 Key Distribution Insights

1.  **Median Comparison:** The **'car'** class exhibits the highest median Radius Ratio ($\approx 185$), suggesting that, on average, cars have a greater radius ratio compared to 'van' ($\approx 150$) and 'bus' ($\approx 170$).
2.  **Interquartile Range (IQR):**
    * **'car'** has the largest IQR ($\approx 45$), indicating a broader spread or higher variability in its central 50% of data points.
    * **'van'** has the smallest IQR ($\approx 20$), suggesting a tighter clustering of its central data points.
3.  **Overall Range:** The **'bus'** class has the largest overall range (Minimum to Maximum whisker: $\approx 140$), although the 'van' class contains the most significant high-end outliers.
4.  **Outliers:** The **'van'** class shows multiple high-value outliers significantly above its main data distribution, suggesting some instances with exceptionally high Radius Ratios for this class. The 'bus' class has a low-value outlier.


<img width="875" height="510" alt="image" src="https://github.com/user-attachments/assets/3a21a17d-d9de-443c-be73-880768c4db07" />

## Distribution of Elongatedness by Class  📈💜

This overlapping histogram and Kernel Density Estimate (KDE) plot visualizes the frequency distribution of the 'Elongatedness' feature, segmented by three vehicle classes: **van**, **car**, and **bus**.

### 📉 Axes and Data Range
* **X-axis (Elongatedness):** Ranges approximately from 25 to 60.
* **Y-axis (Frequency):** Ranges approximately from 0 to 120.

### 📌 Class Representation (Legend & Color)
| Class | Color/Tone | Density Peak Location (Approx.) |
| :--- | :---: | :---: |
| **van** | Darkest Purple Fill / Line | $\approx 43$ |
| **car** | Mid-tone Purple Fill / Line | $\approx 46$ |
| **bus** | Lightest Purple Fill / Line | $\approx 31$ |

### 💡 Key Distribution Findings (Based on KDE)

1.  **'van' Class Distribution:**
    * Exhibits a **multi-modal distribution**, with a primary, sharp peak (mode) around **Elongatedness $\approx 43$** (Frequency $\approx 55$).
    * Shows a secondary, smaller concentration in the range of $50-60$.
2.  **'car' Class Distribution (Mid-tone Purple):**
    * Displays a relatively **single, strong peak** (mode) around **Elongatedness $\approx 46$** (Frequency $\approx 80$), which is slightly higher than the 'van' peak.
    * This distribution is more compact and less spread out compared to 'van'.
3.  **'bus' Class Distribution (Lightest Purple):**
    * Exhibits a distribution with a **major, sharp peak** (mode) at **Elongatedness $\approx 31$** (Frequency $\approx 115$), indicating that buses generally have the lowest Elongatedness values.
    * The overall 'bus' distribution is heavily skewed to the left (low values).
4.  **Feature Separability:** The 'bus' class distribution is clearly distinct and well-separated from 'van' and 'car' based on this feature, suggesting **'Elongatedness' is a good discriminator** for the 'bus' class. However, 'van' and 'car' distributions show significant overlap in the range of $40-50$, indicating poor separability between these two classes using this single feature.

---

<img width="1251" height="274" alt="image" src="https://github.com/user-attachments/assets/deeaa229-077e-4d10-afeb-e62c27cf64f3" />


<img width="1249" height="281" alt="image" src="https://github.com/user-attachments/assets/2f732d7d-f305-40ef-8831-d272cbaec57a" />


<img width="1273" height="272" alt="image" src="https://github.com/user-attachments/assets/03f70164-997c-4019-8529-90d7c188dcf0" />


<img width="1241" height="276" alt="image" src="https://github.com/user-attachments/assets/75c82b0b-6e8e-4b7a-a4e1-93c50c1ef39e" />


<img width="1276" height="555" alt="image" src="https://github.com/user-attachments/assets/31a9bfd4-9f55-4038-b546-cbb964f8f5ce" />

## Univariate Feature Distribution Summary (Histograms) 🔍🟣

These histograms visualize the distribution of 18 features, showing the frequency count (Y-axis) against the feature value (X-axis). The analysis focuses on the general shape of the distribution: mode(s), range, and skewness.

| Feature Name | Approx. Value Range (X-axis) | Distribution Shape / Skewness | Primary Mode Location (Approx.) | Notes |
| :--- | :---: | :--- | :---: | :--- |
| **compactness** | $70 - 120$ | Close to Normal / Slightly Right-Skewed | $85 - 90$ | Moderate spread. |
| **circularity** | $35 - 60$ | Multi-modal (Bimodal/Trimodal) | $35-40, 45-50, 50-55$ | Highly irregular distribution with distinct peaks. |
| **distance_circularity** | $50 - 110$ | Strongly Left-Skewed | $65 - 80$ | Heavily concentrated towards lower values. |
| **radius_ratio** | $100 - 325$ | Right-Skewed | $140 - 160$ | Concentrated at lower values with a long tail. |
| **pr.axis_aspect_ratio** | $60 - 140$ | Heavily Right-Skewed | $60 - 70$ | Dominated by a large spike at the lower end. |
| **max.length_aspect_ratio** | $0 - 50$ | Heavily Right-Skewed | $0 - 5$ | Extremely concentrated at the lowest values. |
| **scatter_ratio** | $120 - 260$ | Bimodal | $140 - 160$ and $200 - 220$ | Two clear distinct clusters of data points. |
| **elongatedness** | $25 - 60$ | Bimodal | $30 - 35$ and $45 - 50$ | Two major groups, one with low and one with moderate elongatedness. |
| **pr.axis_rectangularity**| $18 - 28$ | Multi-modal | $18 - 19$ | Sharp spike at the minimum value. |
| **max.length_rectangularity**| $120 - 190$ | Close to Normal / Slightly Right-Skewed | $140 - 145$ | Relatively symmetric distribution. |
| **scaled_variance_major** | $125 - 325$ | Right-Skewed | $175 - 200$ | Steep drop-off after the peak. |
| **scaled_variance_minor** | $200 - 800$ | Right-Skewed | $300 - 400$ | Long tail extending to high values. |
| **scaled_radius_of_gyration**| $110 - 270$ | Close to Normal | $170 - 190$ | Relatively symmetric, slightly rugged shape. |
| **skewness_major** | $60 - 130$ | Heavily Right-Skewed | $65 - 70$ | Very sharp peak at the low end; sparse data past 110. |
| **skewness_minor** | $0 - 22$ | Heavily Right-Skewed | $0 - 2$ | Extremely high frequency at the lowest value. |
| **kurtosis_minor** | $0 - 40$ | Heavily Right-Skewed | $0 - 2$ | High frequency at the minimum value. |
| **kurtosis_major** | $175 - 205$ | Multi-modal | $180 - 185$ and $190 - 195$ | Complex distribution with multiple peaks. |
| **hollows_ratio** | $180 - 215$ | Multi-modal / Bimodal | $190 - 195$ and $200 - 205$ | Two major groups visible. |

---
**Summary of Distribution Types:**
* **Highly Skewed (Right/Positive):** `pr.axis_aspect_ratio`, `max.length_aspect_ratio`, `scaled_variance_minor`, `skewness_major`, `skewness_minor`, `kurtosis_minor`. These features are highly concentrated at lower values.
* **Bimodal/Multi-modal:** `circularity`, `scatter_ratio`, `elongatedness`, `kurtosis_major`, `hollows_ratio`. These features indicate potential sub-groups within the data that can be helpful for clustering or classification.

---

<img width="1022" height="416" alt="image" src="https://github.com/user-attachments/assets/b45fe4c8-b743-4ab4-bdc7-b7e05e708e3f" />

<img width="973" height="407" alt="image" src="https://github.com/user-attachments/assets/3eb3360f-9eb4-42db-8697-92324b5dc88e" />


<img width="972" height="420" alt="image" src="https://github.com/user-attachments/assets/e2b8d06d-7f26-45fe-8038-ec9cf5e7d9ab" />

## Univariate Distribution Summary by Vehicle Class (Box Plots) 📊🔍

This summary table analyzes the distribution (Median and IQR) of 18 features across the 'van', 'car', and 'bus' classes, highlighting key differences for classification.

| Feature Name | Primary Separability Insight | Median Rank (Low to High) | IQR Comparison (Variability) |
| :--- | :--- | :--- | :--- |
| **compactness** | **Good Separability** (van $\ll$ car, bus) | van $\ll$ bus $\approx$ car | van $<$ car $\approx$ bus |
| **circularity** | **Moderate Separability** (bus $\ll$ car) | van $\approx$ bus $<$ car | bus $<$ van $<$ car |
| **distance_circularity** | **Good Separability** (van $\ll$ car) | van $\ll$ bus $\ll$ car | bus $<$ van $<$ car |
| **radius_ratio** | **Poor Separability** | van $\ll$ bus $\approx$ car | van $<$ bus $\approx$ car |
| **pr.axis_aspect_ratio** | **Poor Separability** | van $\approx$ car $\ll$ bus | van $\approx$ car $\approx$ bus |
| **max.length_aspect_ratio** | **Poor Separability** (Low values for all) | car $\approx$ bus $\ll$ van | bus $\ll$ car $\approx$ van |
| **scatter_ratio** | **Good Separability** (van $\ll$ car, bus) | van $\ll$ bus $<$ car | van $\approx$ bus $\approx$ car |
| **elongatedness** | **Good Separability** (van $\gg$ car, bus) | bus $\approx$ car $\ll$ van | car $<$ bus $<$ van |
| **pr.axis_rectangularity**| **Moderate Separability** (van $\ll$ bus $\ll$ car) | van $\ll$ bus $\ll$ car | van $<$ bus $\approx$ car |
| **max.length_rectangularity**| **Good Separability** (van $\ll$ bus $\ll$ car) | van $\ll$ bus $\ll$ car | bus $<$ van $<$ car |
| **scaled_variance_major** | **Moderate Separability** (van $\ll$ bus $\ll$ car) | van $\ll$ bus $\ll$ car | van $\ll$ bus $<$ car |
| **scaled_variance_minor** | **Moderate Separability** (van $\ll$ bus $\ll$ car) | van $\ll$ bus $\ll$ car | bus $<$ van $\approx$ car |
| **scaled_radius_of_gyration**| **Moderate Separability** (van $\ll$ car $\approx$ bus) | van $\ll$ car $\approx$ bus | van $\ll$ bus $\ll$ car |
| **skewness_major** | **Poor Separability** | car $\approx$ van $\approx$ bus | van $\approx$ bus $\approx$ car |
| **skewness_minor** | **Poor Separability** | van $\approx$ bus $\approx$ car | van $\approx$ bus $\approx$ car |
| **kurtosis_minor** | **Moderate Separability** (van $\approx$ bus $\ll$ car) | bus $\approx$ van $\ll$ car | van $\approx$ bus $\ll$ car |
| **kurtosis_major** | **Moderate Separability** (bus $\ll$ van $\ll$ car) | bus $\ll$ van $\ll$ car | bus $\ll$ van $\approx$ car |
| **hollows_ratio** | **Moderate Separability** (bus $\ll$ van $\ll$ car) | bus $\ll$ van $\approx$ car | bus $\ll$ van $\approx$ car |

---
**Key Interpretation:**
* **"$\ll$" (Much Less Than):** Indicates a clear separation in the median/box location.
* **"$\approx$" (Approximately Equal):** Indicates significant overlap or very similar median/IQR.
* **Good Separability:** Features like **`elongatedness`** and **`scatter_ratio`** show distinct median values and minimal box overlap, making them highly effective for initial classification.
* **Poor Separability:** Features like **`skewness_major`** and **`skewness_minor`** show high box overlap and similar medians across all classes, suggesting they are weak individual predictors.



---
<img width="987" height="415" alt="image" src="https://github.com/user-attachments/assets/18341618-8cca-4dc1-95e5-d7d9669976bb" />


<img width="989" height="414" alt="image" src="https://github.com/user-attachments/assets/5b0dc39b-45f5-47fa-b731-5d310c4bbf08" />



<img width="971" height="419" alt="image" src="https://github.com/user-attachments/assets/d81cf8a8-795d-4918-8aff-620569bc4e17" />

## Univariate Feature Density Distribution Summary (KDE Plots) 📊🟣

These KDE plots visualize the probability density function (Y-axis) of 18 features across their respective value ranges (X-axis). The analysis focuses on the distribution shape (unimodal, bimodal, or skewed) and the location of the primary peak(s).

| Feature Name | Approx. Value Range (X-axis) | Distribution Shape / Modality | Primary Peak Location (Approx.) | Skewness (Visual) |
| :--- | :---: | :--- | :---: | :--- |
| **compactness** | $70 - 120$ | Unimodal (Broad) | $90 - 95$ | Slightly Right |
| **circularity** | $30 - 65$ | Bimodal | $40 - 45$ and $50 - 55$ | Complex |
| **distance_circularity** | $40 - 120$ | Bimodal | $70 - 80$ and $100 - 110$ | Left-Skewed (Mainly) |
| **radius_ratio** | $100 - 350$ | Unimodal (Sharp) | $150 - 170$ | Right |
| **pr.axis_aspect_ratio** | $40 - 140$ | Unimodal (Very Sharp) | $50 - 60$ | Heavily Right |
| **max.length_aspect_ratio** | $0 - 60$ | Unimodal (Very Sharp) | $5 - 10$ | Heavily Right |
| **scatter_ratio** | $100 - 300$ | Bimodal | $140 - 160$ and $200 - 220$ | Complex |
| **elongatedness** | $20 - 60$ | Bimodal | $30 - 35$ and $45 - 50$ | Complex |
| **pr.axis_rectangularity**| $16 - 30$ | Bimodal | $18 - 20$ and $24 - 26$ | Complex |
| **max.length_rectangularity**| $120 - 200$ | Unimodal (Broad) | $140 - 150$ | Slightly Right |
| **scaled_variance_major** | $100 - 350$ | Bimodal | $160 - 180$ and $220 - 240$ | Right |
| **scaled_variance_minor** | $200 - 1200$ | Bimodal | $300 - 400$ and $600 - 800$ | Heavily Right |
| **scaled_radius_of_gyration**| $100 - 300$ | Unimodal (Broad) | $170 - 190$ | Slightly Right |
| **skewness_major** | $60 - 140$ | Unimodal (Sharp) | $65 - 70$ | Heavily Right |
| **skewness_minor** | $-5 - 25$ | Unimodal (Broad) | $0 - 5$ | Heavily Right |
| **kurtosis_minor** | $0 - 50$ | Unimodal (Broad) | $0 - 5$ | Heavily Right |
| **kurtosis_major** | $170 - 210$ | Bimodal (Weak) | $185 - 190$ and $195 - 200$ | Complex |
| **hollows_ratio** | $180 - 215$ | Bimodal | $185 - 190$ and $200 - 205$ | Complex |

---
**Insights on Modality and Separability:**
* **Bimodal/Multi-modal Features:** Features like `circularity`, `distance_circularity`, `scatter_ratio`, `elongatedness`, `pr.axis_rectangularity`, `scaled_variance_major`, `scaled_variance_minor`, `kurtosis_major`, and `hollows_ratio` show multiple peaks. In classification tasks, this often indicates that the feature contributes to separating two or more underlying classes (as seen in the previous analysis).
* **Heavily Skewed Features:** Features like `pr.axis_aspect_ratio`, `max.length_aspect_ratio`, `skewness_major`, `skewness_minor`, and `kurtosis_minor` are concentrated on one side of their range. This heavy skewness suggests the need for data transformation (e.g., logarithmic) before applying models that assume Gaussian distributions.

---


<img width="977" height="741" alt="image" src="https://github.com/user-attachments/assets/f9e57ad1-4518-4686-9ec3-56ba6108cdc1" />

## Feature Correlation Matrix 💜📈

| Feature | compactness | circularity | distance_circularity | radius_ratio | pr.axis_aspect_ratio | max.length_aspect_ratio | scatter_ratio | elongatedness | pr.axis_rectangularity | max.length_rectangularity | scaled_variance_major | scaled_variance_minor | scaled_radius_of_gyration | skewness_major | skewness_minor | kurtosis_minor | kurtosis_major | hollows_ratio |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **compactness** | **Strong Positive** | **Strong Positive** | **Strong Positive** | Moderate Positive | Weak/None | Moderate Positive | **Strong Positive** | **Strong Negative** | **Strong Positive** | Weak/None | **Strong Positive** | Weak/None | Moderate Positive | Weak/None | Weak/None | Weak/None | Weak/None | Moderate Negative |
| **circularity** | **Strong Positive** | **Strong Positive** | **Strong Positive** | **Strong Positive** | Weak/None | Moderate Positive | **Strong Positive** | **Strong Negative** | **Strong Positive** | Weak/None | **Strong Positive** | Weak/None | Moderate Positive | Weak/None | Weak/None | Weak/None | Weak/None | Moderate Negative |
| **distance_circularity** | **Strong Positive** | **Strong Positive** | **Strong Positive** | **Strong Positive** | Weak/None | Moderate Positive | **Strong Positive** | **Strong Negative** | **Strong Positive** | Weak/None | **Strong Positive** | Weak/None | Moderate Positive | Weak/None | Weak/None | Weak/None | Weak/None | Moderate Negative |
| **radius_ratio** | Moderate Positive | **Strong Positive** | **Strong Positive** | **Strong Positive** | Moderate Negative | Moderate Positive | Moderate Positive | Moderate Negative | Moderate Positive | Weak/None | Moderate Positive | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None |
| **pr.axis_aspect_ratio** | Weak/None | Weak/None | Weak/None | Moderate Negative | **Strong Positive** | Weak/None | Moderate Negative | Moderate Positive | Weak/None | Weak/None | Moderate Negative | Weak/None | Weak/None | Weak/None | Moderate Negative | Weak/None | Weak/None | Moderate Negative |
| **max.length_aspect_ratio** | Moderate Positive | Moderate Positive | Moderate Positive | Moderate Positive | Weak/None | **Strong Positive** | Moderate Positive | Moderate Negative | Moderate Positive | Weak/None | Moderate Positive | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None |
| **scatter_ratio** | **Strong Positive** | **Strong Positive** | **Strong Positive** | Moderate Positive | Moderate Negative | Moderate Positive | **Strong Positive** | **Strong Negative** | **Strong Positive** | Moderate Positive | **Strong Positive** | Moderate Positive | Moderate Negative | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None |
| **elongatedness** | **Strong Negative** | **Strong Negative** | **Strong Negative** | Moderate Negative | Moderate Positive | Moderate Negative | **Strong Negative** | **Strong Positive** | **Strong Negative** | Moderate Negative | **Strong Negative** | Moderate Negative | Moderate Positive | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None |
| **pr.axis_rectangularity** | **Strong Positive** | **Strong Positive** | **Strong Positive** | Moderate Positive | Weak/None | Moderate Positive | **Strong Positive** | **Strong Negative** | **Strong Positive** | Weak/None | **Strong Positive** | Moderate Negative | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Moderate Negative |
| **max.length_rectangularity** | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Moderate Positive | Moderate Negative | Weak/None | **Strong Positive** | Weak/None | Moderate Positive | Moderate Negative | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None |
| **scaled_variance_major** | **Strong Positive** | **Strong Positive** | **Strong Positive** | Moderate Positive | Moderate Negative | Moderate Positive | **Strong Positive** | **Strong Negative** | **Strong Positive** | Weak/None | **Strong Positive** | Weak/None | Moderate Negative | Weak/None | Weak/None | Weak/None | Weak/None | Moderate Negative |
| **scaled_variance_minor** | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Moderate Positive | Moderate Negative | Moderate Negative | Moderate Positive | Weak/None | **Strong Positive** | Moderate Negative | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None |
| **scaled_radius_of_gyration** | Moderate Positive | Moderate Positive | Moderate Positive | Weak/None | Weak/None | Weak/None | Moderate Negative | Moderate Positive | Weak/None | Moderate Negative | Moderate Negative | Moderate Negative | **Strong Positive** | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None |
| **skewness_major** | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | **Strong Positive** | Weak/None | Moderate Positive | Weak/None | Strong Positive |
| **skewness_minor** | Weak/None | Weak/None | Weak/None | Weak/None | Moderate Negative | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | **Strong Positive** | Weak/None | Moderate Negative | Weak/None |
| **kurtosis_minor** | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Moderate Positive | Weak/None | **Strong Positive** | Moderate Negative | Strong Positive |
| **kurtosis_major** | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Weak/None | Moderate Negative | Moderate Negative | **Strong Positive** | Weak/None |
| **hollows_ratio** | Moderate Negative | Moderate Negative | Moderate Negative | Weak/None | Moderate Negative | Weak/None | Weak/None | Weak/None | Moderate Negative | Weak/None | Moderate Negative | Weak/None | Weak/None | Strong Positive | Weak/None | Strong Positive | Weak/None | **Strong Positive** |

**Interpretation Key:**
* **Strong Positive:** Correlation value near +1.00 (Dark Magenta/Purple)
* **Moderate Positive:** Correlation value between +0.50 and +0.75 (Lighter Magenta/Purple)
* **Weak/None:** Correlation value near 0.00 (White/Lightest Lilac)
* **Moderate Negative:** Correlation value between -0.25 and -0.50 (Light Lilac/Faint Purple)
* **Strong Negative:** Correlation value near -1.00 (Bright Violet/Blue-Purple)

<img width="701" height="649" alt="image" src="https://github.com/user-attachments/assets/a38467e2-25dd-4622-9cb7-604195b348f9" />

## Pairplot of Key Features by Vehicle Class  📊💜

This pairplot visualizes the univariate distributions (diagonal) and pairwise relationships (off-diagonal) for three key features: `elongatedness`, `scatter_ratio`, and `skewness_minor`, segmented by the vehicle class: **van** (darkest), **car** (mid-tone), and **bus** (lightest).

### 📈 Diagonal (Univariate Distributions - KDE Plots)

| Feature | Distribution Shape | Class Separability | Key Observation |
| :--- | :--- | :--- | :--- |
| **elongatedness** | Multi-modal (Bimodal/Trimodal) | **High** | 'bus' (lightest) peaks significantly lower ($\approx 30$), clearly separated from 'van' and 'car' ($\approx 45-55$). |
| **scatter_ratio** | Multi-modal (Bimodal/Trimodal) | **Moderate** | 'van' (darkest) and 'car' (mid-tone) distributions overlap considerably, while 'bus' (lightest) shows a minor, separate peak ($\approx 125$). |
| **skewness_minor** | Heavily Right-Skewed | **Poor** | All three class distributions are heavily overlapping and concentrated near 0, making separation difficult with this feature alone. |

## 🔗 Off-Diagonal (Pairwise Relationships - Scatter Plots)

### 1. elongatedness vs. scatter_ratio (Lower Left & Upper Right)
* **Relationship:** Shows a **strong, non-linear (inverse/curvilinear) correlation**. As `elongatedness` increases, `scatter_ratio` sharply decreases.
* **Class Separation:**
    * **'bus'** points cluster tightly in the **high elongatedness/low scatter_ratio** area ($\text{elongatedness} > 50, \text{scatter\_ratio} < 175$).
    * **'van'** and **'car'** points overlap significantly across the moderate-to-low $\text{elongatedness}$ range.
    * This pair of features offers **excellent separation** between the 'bus' class and the 'van'/'car' classes.

### 2. elongatedness vs. skewness_minor (Lower Left & Upper Right)
* **Relationship:** Shows a **very weak or negligible correlation**. Points are widely scattered across the plot.
* **Class Separation:**
    * No clear boundaries or distinct clusters are visible. All three classes largely **overlap**, demonstrating poor joint separability for this feature pair.

### 3. scatter_ratio vs. skewness_minor (Lower Left & Upper Right)
* **Relationship:** Shows a **very weak or negligible correlation**. Points are widely scattered.
* **Class Separation:**
    * Minimal distinction between the classes. The majority of points for all classes are concentrated at lower $\text{skewness\_minor}$ values. **Poor joint separability.**

---
**Conclusion:** The **`elongatedness`** and **`scatter\_ratio`** pair demonstrates the highest potential for classification, particularly for isolating the **'bus'** class due to its distinct position in the feature space.
