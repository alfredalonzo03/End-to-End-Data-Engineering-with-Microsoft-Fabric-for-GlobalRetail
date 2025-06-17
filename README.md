# End-to-End Data Engineering with Microsoft Fabric for GlobalRetail

Spearheaded the development of a scalable, end-to-end data lakehouse on Microsoft Fabric for GlobalRetail, transforming disparate global data (CSV, JSON, Parquet) into actionable insights. This solution slashed data processing time from 72 to under 6 hours, significantly boosting analytics, inventory forecasting, and customer personalization through Delta Lake, Fabric SQL Analytics Endpoint, and Power BI.

## Project Overview

This project details the design and implementation of a robust, scalable data lakehouse solution on the **Microsoft Fabric** platform for GlobalRetail, a multinational retail corporation operating across 27 countries and over 11,000 stores. The core objective was to overcome challenges in consolidating and analyzing massive, disparate daily data volumes to enable improved decision-making and operational efficiency.

The solution tackles critical issues like prolonged data processing times (previously up to 72 hours), varying data formats and schemas across regions, and complex ETL processes required for currency, time zone, and product code alignment.

## Data Sources

The data lakehouse ingests and processes data from three primary operational systems:

* **Customer Data:** Approximately **500 million records** in **CSV** format, sourced from CRM systems.

* **Product Catalog:** Around **0.5 million SKUs** in **JSON** format, obtained from inventory management systems.

* **Transaction History:** Annually, about **10 billion transactions** in **Parquet** format, collected from Point-of-Sale (POS) systems and e-commerce platforms.

## Architecture

A modern **Data Lakehouse architecture** was implemented, structured around the **Medallion Architecture** (Bronze, Silver, Gold layers) to ensure data quality, reliability, and accessibility.

* **Bronze Layer (Raw Data Ingestion):** This layer acts as the landing zone for all raw, unvalidated data from source systems. Data (CSV, JSON, Parquet) is ingested into immutable Delta Lake tables, preserving the original state.

* **Silver Layer (Cleaned & Transformed Data):** Data from the Bronze layer undergoes rigorous cleaning, standardization, and transformation based on business rules. This includes handling data quality issues, resolving schema variations, and applying complex ETL logic for currency conversion, time zone adjustments, and regional product code harmonization.

* **Gold Layer (Curated Business Views):** This final layer contains highly aggregated and denormalized data optimized for direct consumption by business intelligence and analytical tools. It includes a **unified customer view**, enabling comprehensive cross-channel and cross-region analysis.

* **Reporting & Dashboarding:** **Power BI** is connected to the Gold layer via **Fabric SQL Analytics Endpoint** to create interactive dashboards and reports, providing actionable insights for various business units.

### Architecture Diagram

To visualize the data flow, consider an architecture diagram similar to this conceptual representation:

+----------------+
|  Source Systems |
|  - CRM (CSV)   |
|  - Inventory   |
|    (JSON)      |
|  - POS/E-comm  |
|    (Parquet)   |
+----------------+
|
V
+-----------------+
|  Microsoft Fabric|
|  (Ingestion)    |
|  Bronze Layer   |
|  (Raw Delta)    |
+-----------------+
|
V
+-----------------+
|  Microsoft Fabric|
|  (Processing)   |
|  Silver Layer   |
|  (Cleaned Delta)|
+-----------------+
|
V
+-----------------+
|  Microsoft Fabric|
|  (Curated Views)|
|  Gold Layer     |
|  (Unified Delta)|
+-----------------+
|
V
+-----------------+
|  Power BI       |
|  (Reporting &   |
|   Dashboards)   |
+-----------------+

Below is a conceptual representation of the data flow. A detailed architectural diagram is available in the `images/` folder.

## Technologies Used

* **Microsoft Fabric:** Served as the central unified analytics platform for orchestrating end-to-end data ingestion, transformation, and serving across data engineering, warehousing, and BI components.

* **Delta Lake:** An open-source storage layer that brings ACID transactions, scalable metadata handling, and unified streaming and batch data processing to data lakes.

* **Apache Spark:** Leveraged within Microsoft Fabric for large-scale data processing and transformations.

* **Fabric SQL Analytics Endpoint:** Used for high-performance SQL querying and serving curated data to business intelligence tools.

* **Power BI:** Utilized for creating interactive dashboards and business intelligence reports.

## Business Impact & Outcomes

The implemented solution delivered significant business value by addressing GlobalRetail's key pain points:

* **Dramatic Processing Time Reduction:** Data processing time was reduced from **72 hours to under 6 hours**.

* **Improved Inventory Forecasting:** Enabled a **25% improvement** in inventory forecasting accuracy.

* **Enhanced Customer Personalization:** Contributed to a **15% boost** in repeat purchases.

* **Near Real-Time Financial Reporting:** Established capabilities for timely and accurate financial insights across all global regions.

* **Scalable & Robust Foundation:** Built an extensible data platform capable of supporting future growth and evolving analytical needs.
