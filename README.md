# Environmental Mapping Pipeline

## Overview
This repository contains a comprehensive pipeline for environmental image analysis and segmentation using high-resolution satellite imagery. The pipeline focuses on identifying and visualizing forested areas, grassy zones, and other land cover types within a 1000 ft radius around the Metropolitan Museum of Art (NYC). It leverages Google Earth Engine (GEE) for data retrieval, HSV-based color segmentation, KMeans clustering, and a grid-based undirected graphical model for spatial analysis.

## Purpose
The project aims to provide a scalable, interpretable, and GIS-compatible tool for environmental monitoring, urban planning, and disaster preparedness. It processes satellite imagery into a 350x350 pixel grid and offers color-coded visualizations to support decision-making in geospatial contexts.

## Features
- **Accurate Vegetation Segmentation**: Uses HSV color space (Hue 35–90°, Saturation, Value) and post-KMeans refinement to distinguish forest, grass, and urban areas.
- **Spatial Modeling**: Implements a grid graph with 4-neighbor edges to model pixel relationships, visualized in `image_350x350.png`.
- **Proximity-Based Classification**: Highlights vegetation within 200 ft (blue) and 200–1000 ft (orange) from the center, with a line to the nearest forest cluster.
- **Visual Outputs**: Generates `segmentation_map.png`, `segmentation_overlay.png`, and `image_350x350.png` for intuitive interpretation.
- **GIS Readiness**: Supports export to GeoTIFFs or Shapefiles for integration with QGIS/ArcGIS.

## Requirements
- Python 3.11+
- Required libraries:
  - `earthengine-api`
  - `geemap`
  - `folium`
  - `numpy`
  - `opencv-python`
  - `scikit-image`
  - `pgmpy` (for graphical models)
- Google Earth Engine account and API authentication

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/simreteabmekbib/pgm-hw3.git