# Analyzing the Relationship Between Electric Vehicle Specifications and Driving Range  

## Overview  
This project explores how different **technical specifications of electric vehicles (EVs)** influence their **real-world driving range**.  
Using two structured datasets containing both **technical specifications and market/manufacturing information**, the study applies **exploratory data analysis (EDA)** and **formal hypothesis testing** to discover meaningful patterns, correlations, and statistically significant differences.  

The goal is to identify which features have the strongest impact on how far an EV can travel on a single charge.

---

## Motivation  
The driving range of an electric vehicle is one of the most important factors for users and manufacturers.  
While battery capacity is often considered the main determinant, other technical aspects such as **vehicle weight, power output, drivetrain performance, acceleration, segment, and country of manufacture** can also play major roles in overall performance and efficiency.  

This project aims to **quantify the relationship between EV design features and real-world range using both visual analysis and hypothesis testing**, offering insights that may help improve both consumer awareness and design optimization.

---

## Data Source  
This project uses **two different datasets** that are merged during the analysis:

### 1. Technical Dataset  
* **Format:** JSON  
* **Main variables include:**  
  * `Battery_Capacity_Useable` — usable battery size (kWh)  
  * `Dims_Weight` — vehicle weight (kg)  
  * `Drivetrain_Power` — motor power (kW)  
  * `Efficiency_Real` — real energy efficiency (kWh/100km)  
  * `Range_Real` — real-world range (km)  
  * `Misc_Segment` — vehicle class or category  
  * `Performance_Acceleration` — 0–100 km/h time (s)  
* **Source:** [EV Database](https://ev-database.org)  
* **File location:** `data/ev-technical-dataset.json`  

### 2. Market & Manufacturing Dataset (Kaggle)  
* **Platform:** Kaggle  
* **Dataset Title:** EV Electrical Vehicles Dataset (3K+ Records – 2025)  
* **Provider:** Pratyush Puri  
* **Format:** CSV  
* **Main variables include:**  
  * `Manufacturer`, `Model`, `Year`  
  * `Country_of_Manufacture`  
  * `Price_USD`  
  * `Battery_Capacity_kWh`, `Range_km`  
  * `Autonomous_Level`, `Safety_Rating`, `Units_Sold_2024`, `Warranty_Years`  
* **File location:** `data/ev-market-dataset.csv`  

This dataset is used to enrich the technical vehicle specifications with market and manufacturing information.

Both datasets are merged using the common identifier **`Vehicle_ID`**.

---

## Analysis Plan  

### 1. **Data Preparation**
* Load and clean both datasets.  
* Merge technical and market data using `Vehicle_ID`.  
* Handle missing values and select relevant numerical and categorical features.  
* Create a final clean dataset for analysis.

### 2. **Exploratory Data Analysis (EDA)**
* Descriptive statistics for main variables.  
* Distribution analysis of real-world driving range.  
* Correlation analysis between `Range_Real` and numerical features.  
* Visual comparisons across:
  * Vehicle segments (`Misc_Segment`)  
  * Countries of manufacture (`Country_of_Manufacture`)

### 3. **Visualization**
* Scatter plots showing relationships such as:
  * Battery Capacity vs Range  
  * Vehicle Weight vs Range  
  * Power vs Range  
  * Acceleration vs Range  
* Correlation heatmap to highlight strongest relationships.  
* Boxplots comparing range across vehicle segments and countries.

### 4. **Hypothesis Testing**
* **Pearson correlation tests** between:
  * Battery capacity and range  
  * Weight and range  
  * Power and range  
  * Acceleration and range  
* **One-way ANOVA tests** to evaluate:
  * Range differences between vehicle segments  
  * Range differences between countries of manufacture  

### 5. **Interpretation**
* Identify the most influential features on driving range.  
* Statistically verify visual findings using hypothesis tests.  
* Discuss trade-offs (e.g., higher performance vs reduced range).  
* Provide insights on EV design, performance, and manufacturing differences.

---

## Expected Outcomes  
* A clear statistical and visual understanding of how technical parameters affect EV range.  
* Identification of the strongest predictors of driving range (especially battery capacity and performance metrics).  
* Statistically significant evidence of differences across vehicle segments and countries.  
* A clean, reproducible Jupyter Notebook suitable for academic evaluation.

---

## Tools and Dependencies  
* **Programming Language:** Python 3.8+  
* **Libraries:**  
  * pandas  
  * numpy  
  * matplotlib  
  * seaborn  
  * scipy  
  * statsmodels  
  * jupyter  
  * ipykernel  

All required packages are listed in `requirements.txt`.

---

## Limitations and Future Work  
* The dataset includes aggregated technical specifications rather than real-time driving test data.  
* External factors such as weather, terrain, traffic conditions, and driving style are not considered.  
* Future work may include:
  * Multivariate regression modeling  
  * Machine learning-based range prediction  
  * Integration of real-world driving behavior and environmental data  

---

## References  

Pratyush Puri. (2025). *EV Electrical Vehicles Dataset (3K+ Records)*. Kaggle.  
Electric vehicle specifications and market-level information dataset used for academic analysis.

---

## License  
This project is prepared for the **Introduction to Data Science (DSA 210)** course.  
The datasets and analysis are used strictly for **educational and academic purposes**.  
All external sources, including the **EV Database** and **Kaggle datasets**, are properly cited.
