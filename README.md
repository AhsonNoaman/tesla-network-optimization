# ⚡️ Tesla Service Network Optimization

### *A Geospatial Capacity Planning Model using Python & Tableau*

<img width="1050" height="568" alt="Screenshot 2026-02-18 at 9 33 45 PM" src="https://github.com/user-attachments/assets/5d0896ec-0626-4bb4-94fb-035909704f50" />


## 📌 Executive Summary
As Tesla's fleet scales in Canada, the service network must evolve from "Urban Density" coverage to "Destination Support." This project answers the question: **"Where is the most underserved high-value market in Ontario?"**

Using 2021 Census Data and geospatial distance modeling, this analysis identified **Prince Edward County (FSA K0K)** as a massive outlier—a region with significant wealth density that effectively sits in a "Service Desert."

## 🔍 The "K0K" Finding
Most expansion models focus purely on population density (Urban). My model weighed **Service Friction** (Distance) and **Economic Capability** (Income) equally.

* **The Anomaly:** Prince Edward County (K0K) appeared as a Top-5 Opportunity Zone despite being rural.
* **The Reason:** It is the "Hamptons of Ontario"—a hub for high-net-worth vacation properties and wineries. Owners here face a **>90km drive** to the nearest service centers (Kingston or Toronto).
* **Strategic Recommendation:** The data supports a **Mobile Service Fleet Base** in this region. A full service center may have too much overhead, but a Mobile Hub would capture high-margin maintenance work without the real estate costs.

## 🛠️ Technical Approach

### 1. Data Engineering (Python)
* **Ingestion:** Parsed 2021 Statistics Canada Census data to extract Population and Median Household Income by FSA.
* **Geospatial Logic:** Used `pgeocode` to calculate the Haversine distance between every Ontario FSA and the nearest existing Tesla Service Center.
* **The Algorithm:**
    $$\text{Opportunity Score} = \frac{\text{Population} \times \text{Median Income}}{\text{Distance to Service}^2}$$
    *(Distance is weighted to prioritize accessibility).*

### 2. Visualization (Tableau)
* **Dual-Axis Mapping:**
    * **Layer 1 (Polygons):** Heat map of "Opportunity Score" (Green = High Potential).
    * **Layer 2 (Circles):** Pin map of "Distance to Service" (Orange = >50km Gap).
* **Insight:** The visualization instantly highlighted K0K as a **Green Region** (High Wealth) covered in **Orange Dots** (Zero Service).

## 📂 Repository Structure
* `notebooks/capacity_planning.ipynb`: Python logic for data cleaning and score calculation.
* `data/`: Processed datasets (Cleaned CSVs).
* `visuals/`: Dashboard screenshots.

## 🚀 How to Run
1.  Clone the repo:
    ```bash
    git clone [https://github.com/AhsonNoaman/tesla-network-optimization.git](https://github.com/AhsonNoaman/tesla-network-optimization.git)
    ```
2.  Install requirements:
    ```bash
    pip install pandas pgeocode numpy
    ```
3.  Run the notebook to reproduce the "Service Burden" scores.

## 📬 Contact
**Ahson Noaman**
[LinkedIn](https://www.linkedin.com/in/ahson-noaman)
