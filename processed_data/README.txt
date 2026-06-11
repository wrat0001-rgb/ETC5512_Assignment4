README — South Australia Tap Water Characteristics Project

## Dataset Overview
This project investigates whether tap water characteristics differ across regions in South Australia. The analysis focuses on comparing regional variation in tap water characteristics, identifying which water quality parameters vary the most between regions, and investigating whether regional averages mask variation between individual water supply systems.

Two processed datasets were created for analysis:
1. sawater_quality_apr26_processed.csv – a processed water quality dataset derived from the SA Water Quality Performance Results dataset. It contains selected water quality parameters representing mineral composition, taste and appearance characteristics, and water treatment characteristics across South Australian water supply systems.
2. sa_operational_geom.rds - a processed spatial dataset derived from the South Australian Government Regions dataset. It contains geographic boundaries aggregated to approximate SA Water operational regions for mapping and spatial visualisation.

These datasets were derived from publicly available datasets published through the South Australian Government Open Data Portal.

## Key contacts
Author: Waranya Ratirotjanakul
Date created: 4 June 2026

## Description of folder/file contents
Raw Data:
1. sawater_quality_apr26.xlsx – original SA Water Quality Performance Results dataset.
2. SAGovtRegions_GDA2020.shp and associated files – original South Australian Government Regions shapefile.

Processed Data:
1. sawater_quality_apr26_processed.csv – processed water quality dataset used for analysis.
2. sawater_quality_apr26_processed_metadata.txt – metadata describing the water quality dataset, including data source, variables, processing steps, coverage, limitations, and licensing information.
3. sa_operational_geom.rds – processed spatial dataset used for mapping and visualisation.
4. sa_operational_geom_metadata.txt – metadata describing the spatial dataset, including data source, spatial processing steps, coverage, limitations, and licensing information.
5. data_dictionary.csv – data dictionary containing variable names, descriptions, data types, and example values for the processed datasets.

## Data Sources
Dataset 1: SA Water Quality Performance Results
Published by SA Water through the South Australian Government Open Data Portal.
The dataset contains drinking water quality information for operational regions and water supply systems across South Australia.

Dataset 2: South Australian Government Regions
Published by the South Australian Government through the Open Data Portal.
The dataset contains administrative regional boundaries used for government planning and service delivery.

## Processing Summary
1. Water Quality Dataset
The raw water quality dataset was processed by:
- removing footer rows,
- standardising variable names,
- removing unnecessary variables,
- converting water quality measurements to numeric format,
- selecting representative water quality parameters.

2. Spatial Dataset
The regional boundary dataset was processed by:
- importing the GDA2020 shapefile,
- creating a correspondence table between South Australian Government regions and SA Water operational regions,
- aggregating regional boundaries into six operational regions,
- saving the resulting spatial dataset as an RDS file.

## How to Use the Data
1. Water Quality Dataset
- Load the processed water quality dataset using: read.csv("data/sawater_quality_apr26_processed.csv")
- This dataset can be used to: compare tap water characteristics across SA Water operational regions, identify water quality parameters with the greatest regional variation, investigate variation between water supply systems within the same region, calculate summary statistics and variation measures such as the coefficient of variation (CV).

2. Spatial Dataset
- Load the processed spatial dataset using: readRDS("data/sa_operational_geom.rds")
- This dataset can be used to: create maps of regional water quality characteristics, visualise spatial patterns in tap water characteristics across South Australia, support geographic comparison of SA Water operational regions.

The two datasets can be joined using the operational region variable to support spatial visualisation and regional analysis.

## Assumptions and Limitations
- Water quality results are reported as rolling 12-month averages and may not capture short-term or seasonal variation.
- Operational regions contain multiple water supply systems, which may mask local differences within a region.
- Exact sampling locations are not provided.
- Representative water quality parameters were selected from the original dataset to support analysis of tap water characteristics.
- Detailed information about water sources for individual supply systems was not available in the dataset. As a result, differences in water quality characteristics could not be directly linked to specific water sources.
- Long-term trend analysis would require combining multiple historical dataset releases.
- SA Water operational regions do not align directly with South Australian Government regions; therefore, an approximate correspondence table was created for mapping purposes.
- The processed spatial dataset is intended for exploratory visualisation and does not represent official SA Water operational boundaries.

## License
1. Water Quality Dataset
Derived from the SA Water Quality Performance Results dataset published by SA Water under the Creative Commons Attribution 4.0 International (CC BY 4.0) licence.

2. Spatial Dataset
Derived from the South Australian Government Regions dataset published by the Government of South Australia under the Creative Commons Attribution 4.0 International (CC BY 4.0) licence.