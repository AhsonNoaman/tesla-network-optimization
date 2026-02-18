# ⚡️ Tesla Service Network Optimization: Ontario 2026

### *A Geospatial Capacity Planning Model using Python & Tableau*
<img width="1440" height="776" alt="Screenshot 2026-02-18 at 4 01 36 PM" src="https://github.com/user-attachments/assets/061b98b8-2494-44c9-b2b9-8ed3170ca690" />



## 📌 Executive Summary
As Tesla's vehicle delivery numbers continue to scale in Canada, service infrastructure must keep pace to maintain customer satisfaction. This project answers a critical business question: **"Where should Tesla open its next Service Center in Ontario to maximize impact?"**

By correlating **2021 Census Data** (Population & Income) with **Drive-Time Latency**, this model identified a critical coverage gap in the **Kitchener-Waterloo-Guelph** corridor—a high-income, high-density region currently underserviced by existing hubs.

## 🔍 Key Insights
* **The "Hidden" Bottleneck:** While Toronto and Mississauga are well-covered (<15km avg distance), the **Kitchener-Waterloo** region shows a high concentration of qualified buyers (Household Income >$100k) with a service distance exceeding **45km**.
* **Expansion Opportunity:** Opening a facility in **Guelph (N1C)** would reduce the "Service Burden" for over **150,000** potential customers and alleviate overflow at the Mississauga center.
* **Quantified Impact:** The model projects a **15% reduction** in average drive-time for owners in Western Ontario if a new node is added.

## 🛠️ Technical Approach
This project utilizes a **Python-to-Tableau** workflow to perform geospatial analysis.

### 1. Data Engineering (Python/Pandas)
* **Ingestion:** Processed raw CSV data from **Statistics Canada (2021 Census)** to extract population and median household income by Forward Sortation Area (FSA).
* **Geocoding:** utilized `pgeocode` to convert Canadian postal codes into Latitude/Longitude coordinates.
* **Logic:** Developed a custom **"Expansion Score"** algorithm:
    $$\text{Score} = \frac{\text{Population} \times \text{Median Income}}{\text{Distance to Nearest Tesla Center}}$$

### 2. Visualization (Tableau)
* **Spatial Mapping:** Joined analysis output with **StatCan Cartographic Boundary Files (.shp)**.
* **Dual-Axis Mapping:** Layered a "Heat Map" of Opportunity Scores against "Pin Maps" of existing Tesla locations to visually isolate gaps.

## 📂 Repository Structure
* `notebooks/analysis.ipynb`: The Python code used for data cleaning and distance calculations.
* `data/`: Contains the cleaned datasets (Raw census data not included due to size).
* `visuals/`: High-resolution screenshots of the dashboard.

## 🚀 How to Run
1.  **Clone the Repo:**
    ```bash
    git clone [[https://github.com/AhsonNoaman/tesla-network-optimization.git]](https://github.com/AhsonNoaman/tesla-network-optimization)
    ```
2.  **Install Dependencies:**
    ```bash
    pip install pandas pgeocode numpy
    ```
3.  **Run the Analysis:**
    Open `analysis.ipynb` in Jupyter Notebook or Google Colab to reproduce the "Service Burden" calculations.

## 📬 Contact
**Ahson Noaman**
[LinkedIn](https://www.linkedin.com/in/ahson-noaman) | [Email](mailto:ahsonnoaman@gmail.com)

*Project created for the Tesla Business Intelligence Internship application (Fall 2026).*
