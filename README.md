🚗 Road Risk and Claim Assessment for Guardian Insurance Co.

## 📌 Project Overview
This project analyzes a massive dataset of over 1.3 million US traffic accidents to provide actionable, data-driven recommendations for **Guardian Insurance Co.** The analysis aims to optimize dynamic premium pricing, automate claim triage processes, and enhance proactive risk management through geospatial clustering and statistical modeling.

## 🎯 Business Objectives
* **Hyper-Local Risk Pricing:** Identify specific, high-risk intersections (hotspots) to adjust premiums based on policyholder commute routes.
* **Automated Claim Triage:** Analyze accident severity distributions to reserve human adjusters for high-impact claims while automating standard ones.
* **Weather Risk Assessment:** Statistically evaluate the true impact of weather conditions on accident frequency and severity, avoiding common base-rate fallacies.

## 🛠️ Tech Stack & Tools
* **Language:** Python
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, SciPy, Scikit-Learn (DBSCAN)
* **Environment:** Google Colab / Jupyter Notebook

## 🔍 Methodology
1. **Data Cleaning & Preprocessing:** 
   * Handled over 46,000 duplicate `Record_ID`s to prevent downstream data leakage.
   * Cleansed critical geospatial and temporal fields, and corrected null value categorizations (e.g., standardizing weather condition NaNs).
2. **Geospatial Clustering (Machine Learning):**
   * Applied **DBSCAN** (Density-Based Spatial Clustering of Applications with Noise) using the Haversine metric.
   * Tuned hyperparameters (`eps = 50 meters`) to isolate hyper-local intersections rather than massive metropolitan highway blobs.
3. **Statistical Analysis:**
   * Utilized the **Mann-Whitney U Test** to evaluate severity differences across various conditions, distinguishing carefully between statistical significance (p < 0.05) and practical business significance.

## 📊 Key Insights & Business Implications
1. **Hyper-Local Pricing Model:** Accident hotspots are heavily concentrated at specific intersections. Guardian can use these precise coordinates to adjust pricing dynamically based on the frequency a customer's route intersects these zones.
2. **Straight-Through Processing:** The 25th, 50th, and 75th percentiles for accident severity all sit exactly at Level 2. Guardian can automate standard Level 2 claims, drastically reducing operational costs.
3. **The Weather "Exposure" Fallacy:** While absolute accident counts are highest in "Fair" weather, this reflects driving exposure (base rates). Average severity is actually higher in "Clear" (2.37) and "Overcast" (2.39) conditions compared to "Fair" (2.14). Pricing should reflect normalized rates, not raw counts.


## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/Insurance-Road-Risk-Analysis.git](https://github.com/your-username/Insurance-Road-Risk-Analysis.git)
