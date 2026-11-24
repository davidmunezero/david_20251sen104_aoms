# Dataset Card

## Kaggle Dataset
* **Source link:** https://www.kaggle.com/datasets/sinanshereef/airport-operations-multi-table-dataset
* **Licence:** Creative Commons Attribution 4.0
* **Format:** CSV files
* **Size:** 9 files 
* **Date Collected:** 2026-11-04
* **Tables Collected:** Staff, ATC, and Maintenance logs 

## Minnesota Geospatial Commons
* **Source link:** https://gis.data.mn.gov/datasets/tpp2050-aviation/explore?layer=3
* **Licence:** Public Domain under the Minnesota Government Data Practices Act
* **Format:** CSV file
* **Size:** 1 file 
* **Date Collected:** 2026-11-24
* **Tables Collected:** Runways

## FAA
* **Source link:** https://external.apic4e.faa.gov/sdrs/retrieve/SDR-2026.csv
* **Licence:** Public Domain 
* **Format:** CSV file
* **Size:** 1 file 
* **Date Collected:** 2026-11-24
* **Tables Collected:** Inspections

## Disclosure
I could not find readily accessible airport equipment data online, so I generated a synthetic unstructured dataset (airport_equipment.csv) using Claude from Anthropic on 24 November 2026, from prompts describing typical airport equipment categories (baggage handling, airfield lighting, GSE, emergency equipment).

## Data Analysis Report
| File | Records | Quality Findings |
| --- | --- | --- |
| staff_shifts.csv | 600 | 15 unnamed columns; 600 missing values in one column |
| inspections.csv | 53,670 | 76 columns; 2,660,045 missing cells; sparse optional fields |
| airport_equipment.csv | 178 | 4 duplicate rows; 10 missing asset IDs; inconsistent dates and categories |
| Airport_Runways.csv | 30 | 5 missing values; 27 whitespace-only cells | 
| maintenance_logs.csv | 400 | 	16 unnamed columns; 6 repeated first-column identifiers | 
