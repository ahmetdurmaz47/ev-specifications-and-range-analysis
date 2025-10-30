
# Analyzing the Relationship Between Electric Vehicle Specifications and Driving Range

## Overview

This project explores how different **technical specifications of electric vehicles (EVs)** influence their **real-world driving range**.
Using a structured dataset containing detailed parameters such as battery capacity, weight, power, torque, and efficiency, the study applies **exploratory data analysis (EDA)** to discover meaningful patterns and correlations.
The goal is to identify which features have the strongest impact on how far an EV can travel on a single charge.

---

## Motivation

The driving range of an electric vehicle is one of the most important factors for users and manufacturers.
While battery capacity is often considered the main determinant, other technical aspects such as **vehicle weight, power output, and drivetrain type** can also play major roles in overall performance and efficiency.
This project aims to **quantify the relationship between EV design features and real-world range**, offering insights that may help improve both consumer awareness and design optimization.

---

## Data Source

* **Dataset:** JSON-formatted dataset of electric vehicle technical specifications.
* **Main variables include:**

  * `Battery_Capacity_Useable` — usable battery size (kWh)
  * `Dims_Weight` — vehicle weight (kg)
  * `Drivetrain_Power` — motor power (kW)
  * `Efficiency_Real` — real energy efficiency (kWh/100km)
  * `Range_Real` — real-world range (km)
  * `Misc_Segment` — vehicle class or category
  * `Performance_Acceleration` — 0–100 km/h time (s)
* **Source:** [EV Database](https://ev-database.org)
* **File location:** `data/ev_technical_data.json`

All values will be parsed into a pandas DataFrame for analysis.

---

## Analysis Plan

1. **Data Preparation**

   * Convert the JSON dataset into a structured pandas DataFrame.
   * Clean missing or inconsistent values.
   * Select relevant numerical and categorical features.
   * Compute derived metrics if necessary (e.g., range per battery size).

2. **Exploratory Data Analysis (EDA)**

   * Descriptive statistics for main variables.
   * Correlation analysis between `Range_Real` and other numerical features.
   * Visual comparisons across different segments (`Misc_Segment`).
   * Distribution plots for range, battery, and efficiency values.

3. **Visualization**

   * Scatter plots showing relationships such as:

     * Battery Capacity vs Range
     * Vehicle Weight vs Range
     * Efficiency vs Range
   * Correlation heatmap to highlight strongest relationships.
   * Boxplots comparing range across vehicle segments.

4. **Interpretation**

   * Identify the most influential features on driving range.
   * Discuss trade-offs (e.g., higher power vs reduced efficiency).
   * Provide insights on design and performance optimization.

---

## Expected Outcomes

* A clear statistical and visual understanding of how technical parameters affect EV range.
* Identification of the strongest predictors of driving range (e.g., battery capacity, efficiency).
* Insightful visualizations demonstrating the interaction between EV design and performance.
* A clean, reproducible Jupyter Notebook suitable for academic evaluation.

---

## Tools and Dependencies

* **Programming Language:** Python 3.8+
* **Libraries:**

  * pandas
  * numpy
  * matplotlib
  * seaborn
  * plotly (for optional interactive charts)
  * jupyterlab

All required packages will be listed in `requirements.txt`.

---

## Limitations and Future Work

* The dataset includes aggregated specifications rather than real driving test data.
* External factors such as weather, terrain, and driving style are not considered.
* Future work may extend this analysis by integrating environmental or usage-based data.

---

## License

This project is prepared for the **Introduction to Data Science (DSA 210)** course.
The dataset and analysis are used strictly for educational and academic purposes.
All sources, including the **EV Database**, will be properly cited.
