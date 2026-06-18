# AI-Driven Crop Type Mapping, Moisture Stress Detection and Irrigation Advisory

## Project overview
This project builds a simple AI-based pipeline to identify crop type, detect moisture stress across crop growth stages, and generate irrigation advisory maps using satellite data.

The system combines optical satellite data and SAR data to monitor crop condition through time. The goal is to create a pilot solution that can be demonstrated in a hackathon and later improved into a larger operational system.

## Problem statement
Farmers and water managers need timely information about:
- what crop is growing,
- whether the crop is under moisture stress,
- and whether irrigation is needed.

This is difficult to monitor manually over large agricultural areas. Satellite remote sensing and AI models can help automate this process.

## Our solution
The project uses:
- Optical satellite data for vegetation condition,
- Microwave SAR data for all-weather monitoring,
- AI/ML models for crop classification,
- Simple rule-based logic for irrigation advisory generation.

The final pipeline produces crop maps, stress maps, and irrigation advisory layers for a selected pilot area.

## Simple workflow
1. Collect satellite and supporting data for the pilot area.
2. Preprocess the data and prepare time-series features.
3. Train a crop classification model using labeled samples.
4. Detect moisture stress using vegetation and SAR indicators.
5. Estimate irrigation need using stress level and water deficit logic.
6. Generate maps, tables, and dashboard-ready outputs.

## Input data
The project uses the following input data:

### Satellite data
- Sentinel-2 or similar optical imagery
- Sentinel-1 or similar SAR imagery

### Ancillary data
- Rainfall data
- Reference evapotranspiration or weather data
- Canal command boundary or study area boundary
- Crop labels / ground truth data

## Expected input formats
Examples of input formats:
- `.tif` / `.tiff` for raster layers
- `.csv` for crop labels and tabular features
- `.geojson` / `.shp` for field boundaries or command area boundaries
- `.json` for configuration files

## Output data
The system is expected to generate:
- Crop type classification map
- Stage-wise moisture stress map
- Irrigation advisory map
- Time-series plots or dashboard summaries
- Validation metrics such as overall accuracy

## How the output looks
Examples of outputs:
- A color-coded map where each crop type has a different class color
- A moisture stress map with classes such as low, medium, and high stress
- An irrigation advisory layer with labels such as:
  - No irrigation needed
  - Monitor
  - Irrigate soon
  - Priority irrigation

## Repository structure
```text
crop-stress-irrigation-ai/
├── README.md
├── .gitignore
├── data/
├── notebooks/
├── src/
├── docs/
└── app/
```

## Current project phase
Phase 1: Repository setup and workflow definition.


