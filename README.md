# Sentinel‑1 & ASCAT Fusion

This repository provides tools merge Sentinel-1 data with ASCAT observations.

---

## Repository Structure

├── notebooks/
│ ├── 01_coarsing_s1.ipynb
│ └── 02_resampling_s1_to_ascat.ipynb
├── data
├── env.yml
├── paths.yml
├── Makefile
└── README.md


- **`env.yml`**: Conda environment definition to install necessary libraries (e.g., xarray, geopandas, rioxarray, ascat, pystac_client, dask).
- **`paths.yml`**: Contains local path configuration for ASCAT data storage and references to Sentinel-1 STAC.

---

## Notebook Overview

### `01_coarsing_s1.ipynb`

This notebook implements the data loading and processing of Sentinel-1 data. We mask the data to use only land over Europe and Africa. The 20m backscatter data from sentinel is grouped hourly, coarsened to 6km resolution and frontfilled. The data is then stored tilewise in zarr files using T3 tiles. 

---

### `02_resampling_s1_to_ascat.ipynb`

Here the Sentinel-1 values from the first Notebook are mapped to ASCAT observation using a nearest neighbour.

---