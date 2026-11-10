# Airport Operations Management System (AOMS)

## Project information

- **Institution:** Adventist University of Central Africa
- **Faculty:** Faculty of Information Technology
- **Course:** INSY 8311 — Database Development with PL/SQL (Group B)
- **Instructor:** Tr. Eric Maniraguha
- **Student:** Munezero David
- **Student ID:** 20251SEN104
- **Proposal deadline:** November 13, 2026

## Problem statement

Technological advances in aviation are outpacing small airports’ ability to adapt. These airports often lack specialized IT staff and cannot afford robust IT solutions. As a result, they struggle to meet their operational needs within budget constraints.

*Source: Airport Cooperative Research Program (2015).*

## Proposed solution

This project proposes a cost-free, easier-to-manage **Airport Operations Management System (AOMS)**.

The proposed system is intended to address the specialized IT staff issue through substantial automation and minimal technical-skill requirements. It is also intended to allow small airports to adopt the solution without making financial investments.

## Objective

The AOMS aims to manage airport-side operational information through a normalized database. The information in scope includes:

- Staff
- Runways
- Equipment
- Ground operations
- Inspection
- Air traffic control

The database is intended to integrate with **Microsoft Power BI** to display data visually and produce accurate and meaningful reports.

## Data source

The primary data source is the [Airport Operations Multi-Table Dataset on Kaggle](https://www.kaggle.com/datasets/sinanshereef/airport-operations-multi-table-dataset), uploaded by Shereef (n.d.).

The dataset simulates an airport operations database used at Indira Gandhi International Airport. It offers incomplete tables; other real-world datasets will be adapted to complete the planned database.

## Planned database tables

| Table | Description |
|---|---|
| **Staff** | Stores information about staff at the airport. |
| **ATC** | Stores additional information on air traffic controllers (specialized staff). |
| **Equipment** | Stores information on airport equipment such as aircraft, baggage handling equipment, light systems, ground support equipment, and emergency equipment. |
| **Runways** | Stores information about runways and taxiways at the airport. |
| **Maintenance logs** | Logs of ground operations on aircraft as well as equipment maintenance. |
| **Inspection** | Inspection logs of airport equipment. |

## Planned PL/SQL features

The project plans to implement the following PL/SQL features:

| Feature | Description |
|---|---|
| **Transactions** | Logical units of work that execute either all-or-nothing operations on the database. |
| **Procedures** | No-return subroutines that perform specific tasks. |
| **Functions** | Subprograms that manipulate data and return values. |
| **Exception handling** | Mechanism that allows errors related to invalid database operations or invalid user input to be caught. |
| **Records & collections** | Composite data types that hold multiple elements together for efficient data handling. |
| **Cursor** | Pointer to query results that allows for row-by-row processing and advanced query processing logic. |
| **Trigger** | Programs that automatically execute when some events occur, accommodating audits and event logging. |
| **Package** | Schema objects that group related items, such as variables, data types, and subprograms, into one unit for modularity. |

## Innovation: Microsoft Power BI

Microsoft Power BI is the technology selected to add an innovation layer to the project.

An analytics dashboard will be built to:

- Summarize key metrics in the database.
- Produce clean, accurate reports.
- Support decision-making.

## References

Airport Cooperative Research Program. (2015). *Alternative IT delivery methods and best practices for small airports*. The National Academies Press. https://doi.org/10.17226/22198

Shereef. (n.d.). *Airport operations multi-table dataset* [Data set]. Kaggle. https://www.kaggle.com/datasets/sinanshereef/airport-operations-multi-table-dataset
