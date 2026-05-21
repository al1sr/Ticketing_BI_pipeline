# End to end ticketing business intelligence pipeline (ETL, SQL and Tableau)

![Apache Hop](https://img.shields.io/badge/Apache_Hop-24265D?style=for-the-badge&logo=apache&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97628?style=for-the-badge&logo=tableau&logoColor=white)

## Description of the project
This repository contains a full analytics and data engineering solution implemented to transform raw ticketing data into strategic business insights. The project focuses on service monitoring, tracking service level agreement (SLA) compliance, and analyzing IT backlog management.

The core infrastructure relies on a structured medallion architecture (bronze, silver, and gold layers) designed to isolate extraction, data curation, and analytical modeling.

**Dataset context:** the workflow processes real-world transactional incident logs, restructuring fields such as dates, severities, and infrastructure environments to ensure consistency across reporting tools.

## Architecture overview
The data engineering process is split into three main iterative steps:

1. **Bronze layer (ingestion):** direct extraction of structural source variables from flat csv formatting into an initial staging schema within a relational database.
2. **Silver layer (cleaning and curation):** filtering of corrupted records, text normalization, handling of missing descriptors, and application of target corporate business rules using structured query language (SQL).
3. **Gold layer (dimensional modeling):** optimization of data structures into a star schema comprising specialized dimension tables and an analytical fact table to support business queries.

## Technologies and pipeline components
* **Apache Hop**: open-source data integration platform utilized to orchestrate the etl processes through visual pipelines (`.hpl`) and data workflows (`.hwf`).
* **MySQL**: relational database engine managing data validation, structural constraints, and storage across the different validation layers.
* **Tableau**: enterprise analytics platform utilized to construct interactive and dynamic dashboards connected directly to the gold analytical layer.

## Repository structure
* `/hop_ticketing`: contains the native configurations for the automated ingestion steps (`10.bronze.hpl`, `20.silver.hpl`, `30.dims.hpl`, `31.dims.hpl`, and `40.facts.hpl`), managed by the global workflow controller (`00.Todo.hwf`).
* `export_database_ticketing.sql`: comprehensive sql dump schema containing table configurations, primary keys, and data definitions for the operational environment.
* `dashboard_ticketing.twbx`: fully packed tableau file containing the interactive frontend reporting system, key performance indicators, and time-series trends.

## Core indicators monitored
* **SLA compliance metrics:** tracking target response and resolution windows across high-priority environments.
* **Backlog duration dynamics:** assessing total operational volume and identifying internal team bottlenecks.
* **Environment segmentation:** isolation of trends within production instances versus development or staging environments to assist with operational resource allocation.

## Academic context
This project was developed as a comprehensive practical deliverable for the **Business Intelligence and Data Warehouse** curriculum, illustrating full technical capability in extracting raw transactions, enforcing database schema integrity, and presenting executive insights.

**Developed by:** Alicia Santamaría Román  
📩 **Contact:** [LinkedIn](https://linkedin.com/in/aliciasantamariaroman)
