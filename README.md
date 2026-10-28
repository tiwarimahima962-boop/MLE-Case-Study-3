Case Study - 3(Machine Learning essentials)

# E-commerce Customer Segmentation Using Clustering

## Overview
This case study explores **unsupervised machine learning** techniques to segment e-commerce customers using RFM-style features: **Recency, Frequency, and Monetary**. The notebook performs exploratory data analysis, scales the features, applies K-Means and DBSCAN clustering, and visualizes the resulting customer groups using t-SNE and PCA.

## Objectives
- Inspect and understand the customer dataset.
- Explore the distributions of Recency, Frequency, and Monetary values.
- Standardize the features before clustering.
- Use the Elbow Method to examine candidate values of *K* for K-Means.
- Create customer segments with K-Means and DBSCAN.
- Evaluate K-Means clustering with the Silhouette Score.
- Visualize clusters using scatter plots, t-SNE, and PCA.

## Dataset
The notebook loads a CSV file named `ecommerce_rfm_unlabeled.csv`.

The dataset should contain these columns:
- `Recency` — how recently a customer made a purchase.
- `Frequency` — how frequently a customer purchases.
- `Monetary` — a measure of the customer's monetary spend/value.

Place the CSV file in the same directory as the notebook, or update the path in the notebook to match its location. The dataset is not included in this repository unless you add it separately.

## Tools and Libraries
- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- Jupyter Notebook

## Workflow
1. **Load the data** from `ecommerce_rfm_unlabeled.csv`.
2. **Inspect the dataset** using sample rows, shape, data types, missing-value counts, and descriptive statistics.
3. **Explore feature distributions** with histograms for Recency, Frequency, and Monetary.
4. **Scale the features** using `StandardScaler` so differences in feature scales have less influence on distance-based clustering.
5. **Choose a K-Means cluster count** by plotting within-cluster sum of squares (WCSS) for `K = 1` through `K = 10` with the Elbow Method.
6. **Fit K-Means** using `n_clusters=7` and `random_state=42`, then assign cluster labels to the data.
7. **Inspect and visualize K-Means clusters** using cluster counts, feature averages, a count plot, and a Recency-versus-Frequency scatter plot.
8. **Evaluate K-Means** with the Silhouette Score.
9. **Apply DBSCAN** with `eps=0.16` and `min_samples=5`, then inspect cluster counts and average feature values. DBSCAN may label outliers as `-1`.
10. **Visualize the K-Means assignments** in two dimensions using t-SNE and PCA. The PCA section also reports the explained variance ratio.

## Setup

### 1. Clone or download the project
Keep the notebook and dataset in the same project folder.

### 2. Create and activate a virtual environment (optional but recommended)

**Windows PowerShell**
```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

**macOS / Linux**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 4. Start Jupyter Notebook
```bash
jupyter notebook
```
Open `MLE_CA case study(3).ipynb` and run the cells in order.

## Project Files
```text
.
├── MLE_CA case study(3).ipynb
├── ecommerce_rfm_unlabeled.csv   # required input dataset; add separately
└── README.md
```

## Results and Interpretation
The notebook produces:
- Dataset summaries and missing-value checks.
- Histograms for the three RFM features.
- An Elbow Method plot.
- K-Means cluster sizes and per-cluster feature averages.
- A K-Means Silhouette Score.
- DBSCAN cluster sizes and per-cluster feature averages.
- t-SNE and PCA visualizations of the K-Means labels.

Use the printed cluster averages to interpret each segment in business terms—for example, customers with lower recency values may have purchased more recently, while higher frequency or monetary values may indicate more active or higher-value customers. Confirm these interpretations against the dataset's definitions and actual results.

**Note:** The notebook sets K-Means to 7 clusters; this is a chosen setting in the notebook, not proof that seven is the optimal number. Review the Elbow Method and Silhouette Score before drawing conclusions. DBSCAN's results depend on its `eps` and `min_samples` settings.

## Reproducibility
The notebook uses `random_state=42` for K-Means and the t-SNE visualization. For reproducible runs, keep the same dataset and compatible library versions.

## Future Improvements
- Compare several K-Means values of *K* using both the Elbow Method and Silhouette Score.
- Tune DBSCAN's `eps` and `min_samples` systematically.
- Add business-friendly names and actionable recommendations for each segment.
- Investigate outliers and skewed feature distributions.
- Save the final customer labels to a CSV file for downstream analysis.

## Author
Add your name, course, institution, and submission details here if required.
