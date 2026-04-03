# Hydraulic Modelling Python

A curated collection of Python examples, notebooks, and scripts focused on **hydraulic and wastewater network modelling workflows**. Each folder covers a specific library and demonstrates how it can be applied in the context of drainage engineering, flood analysis, catchment processing, and results visualisation.

This repository is intended for hydraulic modellers looking to extend their toolkit beyond commercial software interfaces such as InfoWorks ICM, by leveraging Python for data processing, spatial analysis, and visualisation of modelling outputs.

---

## Repository Structure

```
Hydraulic-Modelling-Python/
├── pandas/
├── matplotlib/
├── seaborn/
├── plotly_express/
├── geopandas/
├── scipy/
├── folium/
├── shapely/
└── rasterio/
```

---

## Libraries

### [pandas](./pandas/)

`pandas` is the go-to Python library for tabular data manipulation. In hydraulic modelling, it is used to process exported results from InfoWorks ICM (CSV exports of node/pipe results), manipulate time-series flow data, clean survey datasets, and perform statistical summaries of simulation outputs. Its `DataFrame` and `Series` structures make it straightforward to filter, group, resample, and join large datasets.

**Typical uses:**
- Loading and processing ICM results CSV exports
- Time-series resampling of flow/level data
- Joining spatial and tabular model data
- Summarising survey and asset data

---

### [matplotlib](./matplotlib/)

`matplotlib` is Python's foundational plotting library, providing fine-grained control over static charts and figures. In a hydraulic modelling context it is used to produce publication-quality plots of simulation results, such as hydrographs, depth-duration-frequency curves, longitudinal profiles, and calibration comparisons.

**Typical uses:**
- Plotting hydrographs and flow time-series
- Longitudinal pipe/node profiles
- Calibration plots (observed vs. simulated)
- Flood depth frequency curves

---

### [seaborn](./seaborn/)

`seaborn` builds on `matplotlib` and provides a high-level interface for statistical visualisation. It is particularly useful for exploring distributions and relationships in large modelling datasets, such as comparing results across multiple simulations, visualising rainfall-runoff relationships, or identifying outliers in survey data.

**Typical uses:**
- Distribution plots of flood depths or flow peaks
- Correlation heatmaps of model parameters
- Box plots comparing multiple simulation scenarios
- Pairplots for calibration parameter exploration

---

### [plotly_express](./plotly_express/)

`plotly.express` provides interactive, browser-based charts with minimal code. Unlike `matplotlib`, plots are zoomable and hoverable, making them ideal for sharing results with stakeholders or exploring large time-series datasets. It pairs well with tools like Dash for building lightweight web dashboards around hydraulic model outputs.

**Typical uses:**
- Interactive hydrograph viewers
- Animated flood extent maps over time
- Multi-scenario comparison charts
- Stakeholder-facing result dashboards

---

### [geopandas](./geopandas/)

`geopandas` extends `pandas` to support spatial data, making it one of the most important libraries for hydraulic modelling GIS workflows. It allows reading, writing, and analysing shapefiles, GeoJSONs, and GeoPackages directly in Python. It is central to processing catchment boundaries, pipe network geometries, flood outlines, and spatial joins between model assets and GIS datasets.

**Typical uses:**
- Reading and writing ICM GIS exports (shapefiles, GeoJSON)
- Spatial joins between subcatchments and land-use data
- Processing OS MasterMap building and hardstanding polygons
- Flood outline generation and area calculations
- Coordinate reference system transformations (e.g. EPSG:27700 to WGS84)

---

### [scipy](./scipy/)

`scipy` provides a wide range of scientific computing tools built on top of `numpy`. In hydraulic modelling it is used for statistical analysis of flow data, curve fitting for rainfall-runoff relationships, interpolation of results, and signal processing of flow meter time-series. Its `stats` module is particularly useful for flood frequency analysis.

**Typical uses:**
- Flood frequency analysis (GEV, log-normal distributions)
- Curve fitting for flow-depth relationships
- Interpolation of sparse measurement data
- Signal processing and noise filtering of telemetry data
- Nash-Sutcliffe Efficiency and other goodness-of-fit calculations

---

### [folium](./folium/)

`folium` generates interactive web maps using Leaflet.js, rendered directly from Python. It is well suited for visualising spatial outputs from hydraulic models in a browser, such as flood extents, pipe networks, catchment boundaries, and monitoring locations, without requiring a GIS desktop application.

**Typical uses:**
- Interactive flood extent maps
- Pipe and node network visualisation
- Gauge and monitoring location mapping
- Catchment boundary overlays on basemaps
- Sharing spatial results with non-GIS stakeholders

---

### [shapely](./shapely/)

`shapely` is a Python library for manipulation and analysis of geometric objects, such as points, lines, and polygons. In hydraulic modelling it underpins most spatial processing workflows, including polygon intersection, buffering, union of catchment areas, and point-in-polygon tests. It is used extensively within `geopandas` but can also be used directly for custom geometry operations.

**Typical uses:**
- Merging building and hardstanding polygons for subcatchment definition
- Buffering pipe centrelines to identify nearby assets
- Polygon intersection for impervious area calculations
- Point-in-polygon checks for asset-catchment assignment
- Geometry validation and cleaning of GIS exports

---

### [rasterio](./rasterio/)

`rasterio` provides tools for reading, writing, and processing raster datasets such as Digital Elevation Models (DEMs) and LiDAR data. In hydraulic modelling it is used to extract terrain information for model build, clip and reproject rasters to catchment extents, and process flood depth grids exported from simulations. It works closely with `numpy` for array-based raster operations.

**Typical uses:**
- Reading Scottish Public Sector LiDAR data from GeoTIFFs
- Clipping DEMs to catchment or model extents
- Extracting invert levels and surface elevations at node locations
- Processing flood depth rasters from ICM 2D results
- Reprojecting rasters between coordinate systems (e.g. EPSG:27700)

---

## Getting Started

Each folder contains its own `README.md` with a summary of key methods and example scripts relevant to hydraulic modelling. It is recommended to work through them in the following order if you are new to Python for engineering workflows:

1. `pandas` — data wrangling foundation
2. `matplotlib` — basic plotting
3. `scipy` — statistical analysis
4. `geopandas` and `shapely` — spatial data handling
5. `rasterio` — raster/terrain processing
6. `seaborn` and `plotly_express` — advanced visualisation
7. `folium` — interactive web mapping

---

## Requirements

Install all libraries with:

```bash
pip install pandas matplotlib seaborn plotly geopandas scipy folium shapely rasterio
```

> Note: `geopandas` and `rasterio` may require additional system dependencies. On Windows, installation via `conda` is recommended:
> ```bash
> conda install geopandas rasterio
> ```

---

## Author

**Sebastian Madrid Ontiveros**
Senior Hydraulic Modeller, Edinburgh
[GitHub: Sebasmadridmx](https://github.com/Sebasmadridmx)
