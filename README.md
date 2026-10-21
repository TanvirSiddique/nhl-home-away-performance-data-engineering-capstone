# NHL Home vs Away Performance Data Engineering Capstone
This group ELT (Extract, Load, Transform) project explores the NHL (National Hockey League) home-versus-away performance using historical NHL game data from Kaggle.

The dataset contains 13 related tables covering various aspects like games, teams, players, game statistics, individual plays, player shifts and other game events. Our objective is to build a reliable data foundation that can support meaningful performance analysis and downstream reporting. Also tried to avoid unnecessary data loss.

We implemented a Medallion Architecture in Microsoft Fabric consisting of Bronze, Silver, and Gold layers.

# Technology Stack
- Platform: Microsoft Fabric
- Architecture: Medallion architecture (Bronze, Silver, Gold)
- Data processing: PySpark and Spark SQL, where applicable
- Storage: Fabric Lakehouse and Delta tables

# Data Architecture
The project follows the medallion architecture:
- Bronze Layer - The original NHL CSV datasets were ingested into the Microsoft Fabric Lakehouse. This layer preserves the source data for subsequent processing.
- Sliver Layer - Focused on data cleaning, profiling, and validation.
- Gold Layer -  Developed a star schema, consisting of a game fact table connected to Date, Team, Season, and Venue dimension tables.

# My Scope 
My individual contribution focused mainly on the Bronze-to-Silver transformation pipeline, including data cleaning, duplicate handling, missing-value investigation, relational integrity checks, and automated data validation.

I have also developed a Power BI analytical dashboard in Fabric using the Gold-layer semantic model. Worked with the existing star schema, configured DAX measures, and developed interactive visualizations to analyze home and away performance.

# Problem Statement
The main problem I addressed was how to transform large volumes of raw historical data into clean, consistent and trustworthy analytical data. The source data contained duplicate records, missing values, inconsistent representations of missing data, incomplete team mappings and broken relationships between tables. Without proper validation, these issues could affect the accuracy of our analysis.

# Key Contributions
- Data cleaning: Investigated duplicate records and applied deduplication rules across the source tables.
- Missing-value analysis: Examined null values in context rather than automatically treating every null as an error.
- Relational integrity: Validated primary and foreign-key relationships across interconnected datasets.
- Exception handling: Investigated invalid references and orphaned records, with appropriate handling for records requiring further review.
- Automated validation: Developed tests for foreign-key integrity and verified the validation results.
- Silver-layer preparation: Prepared cleaned and validated tables for downstream analytical use.
- Investigated semantic quality issue: Checked whether venue-related timezone values were consistent with the expected context. Considered the implications of inconsistent venue or timezone information for downstream analysis and interpretation.

# Project Outcome
The project established a structured data preparation workflow for the NHL dataset and supported the wider team's analysis of home-versus-away performance.

My main takeaway was that reliable analytics depends on more than successful ingestion: data quality, traceability, and relational consistency are essential parts of a robust data engineering pipeline.

# Acknowledgements
This was a collaborative capstone project. The repository documents my individual contribution alongside the wider project context.
