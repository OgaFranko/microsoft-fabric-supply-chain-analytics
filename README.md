# Microsoft Fabric Supply Chain Analytics

An end-to-end Microsoft Fabric and Power BI portfolio project that transforms synthetic laboratory purchasing, inventory, and material-usage data into analytics-ready models and interactive reports.

## Project Overview

Laboratory supply-chain data was distributed across five CSV files containing duplicates, missing values, inconsistent date formats, and invalid reference records. This project consolidates and cleans the data, models it for analytics, and delivers reporting for purchasing spend, inventory accuracy, and material consumption.

> **Note:** All data used in this project is synthetic and contains no confidential company or client information.

## Solution Architecture

**Raw CSVs → Bronze Lakehouse → Dataflow Gen2 → Silver Lakehouse → Warehouse Staging → Gold Star Schema → Semantic Model → Power BI Reports**

The solution follows a medallion architecture:

- **Bronze:** Preserves the five raw source datasets.
- **Silver:** Standardizes data types, resolves inconsistent dates, removes duplicate business keys, and prepares trusted records.
- **Gold:** Organizes analytics-ready fact and dimension tables within a Fabric Warehouse.
- **Semantic model:** Connects shared dimensions to purchasing, inventory-count, and material-usage facts through one-to-many relationships.

## Data Sources

- `materials.csv`
- `lots.csv`
- `purchases.csv`
- `inventory_counts.csv`
- `outtakes.csv`

## Data Model

### Dimensions

- `DimDate`
- `DimFacility`
- `DimMaterial`
- `DimVendor`

### Facts

- `FactPurchases`
- `FactInventoryCounts`
- `FactOuttakes`

## Power BI Reports

- **Purchasing Overview:** Purchasing volume, total spend, monthly spend trends, and vendor-level spend concentration.
- **Purchasing Details:** Spending by material category, average vendor lead times, and purchase-status distribution.
- **Inventory Overview:** Count accuracy, absolute and net discrepancies, and materials driving inventory variance.
- **Usage Overview:** Total consumption, monthly usage trends, high-usage materials, and facility-level consumption.

## Key Findings

- Purchasing activity totaled approximately **$1.81 million**.
- Inventory counts achieved **98% overall accuracy**.
- Absolute inventory discrepancies totaled **256 units**.
- Net inventory discrepancy was **-138 units**.
- Approximately **10,000 units** of material were consumed.

## Tools and Skills Demonstrated

- Microsoft Fabric
- Data Factory pipelines
- Dataflow Gen2
- Lakehouse and Delta tables
- Fabric Warehouse and SQL
- Medallion architecture
- Dimensional and semantic modeling
- DAX measures
- Power BI reporting
- Git version control

## Portfolio

[View the complete portfolio PDF](docs/Microsoft-Fabric-Portfolio.pdf)

## Repository Structure

```text
.
|-- README.md
|-- docs/
|   `-- Microsoft-Fabric-Portfolio.pdf
|-- images/
|   |-- purchasing-overview.png
|   |-- purchasing-details.png
|   |-- inventory-overview.png
|   `-- usage-overview.png
|-- sql/
`-- data/
