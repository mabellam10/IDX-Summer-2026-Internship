# IDX Exchange Data Analyst Internship

## Overview
IDX Exchange is a real estate technology company offering SaaS solutions for brokers, agents, and homeowners. The company's cloud-based platform helps real estate professionals generate and convert leads, deepen client relationships, and run smarter operations — powered by home valuation tools, predictive lead scoring, market intelligence dashboards, and fully customizable IDX websites, all through a flexible subscription model.

## Week 1 - Monthly Dataset Aggregation 
Individual monthly files are combined into unified datasets that span multiple months, enabling trend analysis over time.
### Objective
Load and concatenate all monthly MLS files from January 2024 through the most recently completed calendar month into analysis-ready combined datasets.
### Outputs
* Combined sold transactions datasets
* Combined listing dataset
### Skills learned
* Multi-file dataset management
* Data aggregation with Pandas
* Preparing time-series datasets for analysis

---
## Week 2&3 - Dataset Structuring and Validation 
Before analytics begins, the dataset must be inspected and filtered to ensure only relevant residential property records are used. This week also covers foundational EDA steps that inform every phase that follows.
### Dataset understanding
* Identify number of rows and columns
* Review column data types
* Identify high-missing columns
* Separate market analysis fields from metadata fields
### Objective
Fetch the FRED MORTGAGE30US series, resample it from weekly to monthly frequency, and merge it onto both combined datasets using a year-month key derived from transaction dates.
### Skills learned
* Fetching live data from a public API (FRED)
* Resampling time-series data from weekly to monthly frequency
* Creating join keys from datetime fields
* Left merging external economic data onto a transaction dataset
* Validating merge completeness with null checks

---
## Week 4&5 - Data Cleaning and Preparation
Raw MLS data contains formatting inconsistencies, missing values, and fields that need transformation before analysis. This phase prepares the dataset for reliable analytics.
### Tasks
* Convert date fields to datetime format (CloseDate, PurchaseContractDate, ListingContractDate,ContractStatusChangeDate)
* Remove unnecessary or redundant columns
* Handle missing values appropriately
* Ensure numeric fields are properly typed
* Remove or flag invalid numeric values: ClosePrice <= 0, LivingArea <= 0, DaysOnMarket < 0, negative Bedrooms or Bathrooms
### Skills learned
* Data cleaning and transformation
* Preparing analysis-ready datasets
* Working with datetime fields in Pandas

---
## Week 6 - Feature Engineering and Market Metrics
With clean data in hand, you will engineer the key market indicators that power the Tableau dashboards.
### Segment analysis
After creating your engineered metrics, group the analysis by key dimensions to uncover market patterns.
Generate summary statistics for each segment:
* PropertyType and PropertySubType
* CountyOrParish and MLSAreaMajor
* ListOfficeName and BuyerOfficeName (for competitive intelligence)

---
## Week 7 - Outlier Detection and Data Quality
Extreme values in price, price per square footage, close to list ratio, or days on market can distort market averages and trends. You will implement a statistical method to identify and remove these records.
