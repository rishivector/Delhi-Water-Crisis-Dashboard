# Analysis of Delhi's Water Bodies: A Data-Driven Look into an Urban Ecological Crisis

## 📖 Project Overview

This project presents a comprehensive analysis of the state of 893 water bodies within the National Capital Territory (NCT) of Delhi. Leveraging data from **India's first-ever Water Body Census**, this analysis aims to uncover the health, status, and threats facing these critical urban ecosystems.

The primary output of this project is an interactive dashboard that visualizes key metrics, identifies geographical hotspots of degradation, and diagnoses the root causes of water body decline in one of the world's most populous urban areas.

**URL to the Interactive Dashboard:** [Link to your live dashboard on Tableau Public, Power BI, etc.]

## 🎯 Key Objectives

*   **Quantify the Problem:** To establish baseline metrics on the number of defunct, encroached, and degraded water bodies in Delhi.
*   **Identify Hotspots:** To use geospatial analysis to pinpoint districts and areas where the crisis is most acute.
*   **Diagnose the Causes:** To determine the primary drivers of water body disuse, from pollution to urban encroachment.
*   **Inform Action:** To provide clear, data-driven insights that can be used by policymakers, environmental agencies, and citizens to advocate for and implement revival strategies.

## 📊 The Dataset

*   **Source:** The data is a subset from the **First Census of Water Bodies**, a landmark initiative by the Ministry of Jal Shakti, Government of India. This is the most current and comprehensive dataset available on the subject.
*   **File:** `WBC_DL_0.csv`
*   **Content:** The dataset contains detailed information for each of the 893 surveyed water bodies, including:
    *   Geographic details (District, Village, Coordinates)
    *   Physical characteristics (Type, Nature)
    *   Ownership details (Government, Private)
    *   Condition and Status (`In Use`, `Not In Use`, `Encroached`)
    *   Reasons for disuse (`Due to industrial effluents`, `Siltation`, etc.)
    *   Technical measurements (`Storage Capacity`, `Water Spread Area`)
    *   History of renovation efforts.

## 🛠️ Data Processing & Methodology

The raw data required significant cleaning and preparation before analysis. The key steps, performed using **[SQL Server Management Studio / Tableau Prep / Python Pandas]**, included:

1.  **Data Loading:** The raw CSV was imported into a staging table/environment.
2.  **Data Cleaning:**
    *   Standardized categorical data (e.g., corrected 'SOUH WEST' to 'SOUTH WEST').
    *   Replaced non-standard null values (e.g., 'NA') with true `NULL`s.
    *   Converted text-based numeric and date columns to their proper data types (`DECIMAL`, `INT`, `BIGINT`, `BIT`). `TRY_CAST` was used in SQL to handle conversion errors gracefully.
3.  **Feature Engineering:**
    *   Created a `Water Loss` metric calculated as `(Original Capacity - Present Capacity) / Original Capacity`.
    *   Developed a unified `Status` field to categorize each water body as 'In use', 'Not in use', or 'Encroached' for clear visualization.
4.  **Data Visualization:**
    *   An interactive dashboard was built using **[Tableau / Power BI]** to present the findings in an accessible and impactful manner.

## 📈 Key Insights from the Dashboard

The analysis revealed several critical findings:

1.  **A Widespread Crisis:** A staggering **73% (656) of Delhi's water bodies are no longer in use**, representing a massive loss of ecological infrastructure.
2.  **Encroachment is Rampant:** **16% (142) of water bodies are officially encroached upon**, with urbanization pressures being a primary threat.
3.  **Pollution is the Primary Culprit:** The leading reason for a water body becoming defunct is **"Due to industrial effluents,"** followed closely by **"Construction"** and **"Dried-up"** conditions.
4.  **Geographical Disparity:** The problem is most severe in the rapidly urbanizing **South West and North West districts**, which house the majority of Delhi's water bodies and also the highest numbers of defunct and encroached sites.
5.  **Ownership and Vulnerability:** Over **94% of water bodies are government-owned**, indicating that the responsibility for their protection and revival lies squarely with public agencies.

## 🚀 How to Use This Repository

1.  **Explore the Data:** The raw data is available in the `/data` folder (`WBC_DL_0.csv`).
2.  **Review the Cleaning Process:** The SQL cleaning script is available at `scripts/data_cleaning.sql`. *(Adjust this path as needed)*.
3.  **View the Final Dashboard:** The main findings are best explored through the [interactive dashboard](https://public.tableau.com/views/Dashbooard_17495787840700/FinalDashboard?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).
4.  **Check the Analysis:** The workbook file (`.twbx` for Tableau or `.pbix` for Power BI) is located in the `/dashboard` folder.

## 💡 Future Work & Potential Enhancements

*   **Correlational Analysis:** Integrate this data with other datasets like land use maps, industrial zone locations, or population density data to scientifically prove correlations (e.g., proximity to industrial areas and pollution).
*   **Predictive Modeling:** Build a model to predict which water bodies are at the highest risk of encroachment or degradation in the near future based on surrounding development.
*   **Policy Impact Analysis:** Track changes over time if and when future censuses are released to measure the impact of current government revival schemes.

---
