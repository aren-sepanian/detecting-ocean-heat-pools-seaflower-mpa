# Detecting Ocean Heat Pools in the Seaflower MPA

Remote sensing analysis of ocean heat and cold pools in the Seaflower Marine Protected Area near San Andrés and Providencia, Colombia.

**An application of remotely sensed data in San Andrés, Colombia**

**Authors:** Andrew Halaby, Aren Sepanian, Mario Giraldo  
**Affiliation:** California State University, Northridge  
**Date:** January 13, 2026

---

## Project Overview

This project investigates ocean heat and cold pools in the **Seaflower Marine Protected Area (MPA)**, focusing on the islands of **San Andrés** and **Providencia** in Colombia. Using remotely sensed sea surface temperature data, we explored spatial patterns in thermal variability and assessed whether seasonal subsets of the data suggest potential temperature trends over time.

The project was developed as part of undergraduate geospatial and environmental research at California State University, Northridge.

---

## Objectives

- Identify **heat pools** and **cold pools** around the islands of San Andrés and Providencia  
- Explore **seasonal patterns** in sea surface temperature  
- Identify **potential trends** in sea surface temperature using seasonal subsets of remotely sensed data  

---

## Study Area

The study focuses on the **Seaflower Marine Protected Area**, particularly the waters surrounding **San Andrés** and **Providencia**, located in the Caribbean Sea off the coast of Colombia.

---

## Methodology

### Python Workflow

The Python-based analysis focused on preprocessing, visualization, and statistical evaluation of sea surface temperature data:

- Utilized **Rasterio** for loading and handling satellite raster scenes  
- Generated visualizations including **maps, histograms, and summary statistics** to explore spatial temperature distributions  
- Grouped data into **seasonal subsets** to isolate wintertime patterns  
- Applied **linear regression** and the **Mann–Kendall trend test** to evaluate temporal trends  

---

### ArcGIS Workflow

ArcGIS Pro was used for advanced spatial and spatiotemporal analysis:

- Constructed a **multidimensional raster dataset** from surface temperature rasters  
- Performed **yearly hot spot analysis** using the **Getis–Ord Gi\*** statistic  
- Converted raster datasets into **point datasets** for spatial analysis  
- Created a **space-time cube** to analyze spatiotemporal patterns  

#### Space-Time Cube Configuration

- Generated from the multidimensional raster layer  
- **Empty bins filled with zero values** to account for missing data (land/cloud cover)  
- Applied **fixed distance spatial relationships** with a neighborhood distance of **45 m** (1.5× raster cell size)  
- Each timestep compared with **one temporal neighbor**  

#### Emerging Hot Spot Analysis

- Applied **emerging hot spot analysis** to detect persistent and evolving spatial patterns  
- Computed **Getis–Ord Gi\*** statistics with **False Discovery Rate (FDR) correction**  
- Performed **Mann–Kendall trend tests** on each bin  
- Combined **z-scores and p-values** to classify statistically significant hot and cold spots  

---

## Results

### Trend Analysis

Linear regression and Mann–Kendall analyses revealed **no statistically significant trends** in wintertime sea surface temperature within the coastal regions of San Andrés from 2015 to 2025.

High p-values and associated statistics suggest that **data artifacts may have influenced the results**, potentially masking underlying trends. While a trend may exist, it was not detectable within the constraints of this analysis.

---

### Hotspot Analysis

Both individual and emerging hot spot analyses consistently identified **temperature hot spots along coastal shorelines**.

However, detection of hot and cold spots in offshore regions was inconsistent, likely due to **artifacts present in Landsat 8 thermal data**, which limited the reliability of spatial pattern detection beyond nearshore areas.

---

## Limitations

- Presence of artifacts in Landsat 8 thermal data  
- Limited temporal resolution of seasonal subsets  
- Reduced reliability of offshore temperature detection  
- Potential masking of true trends due to data quality constraints  

---

## Repository Contents

- `notebooks/` — Jupyter notebooks for data processing and analysis  
- `data/` — raw and processed datasets *(raw data not included due to size)*  
- `outputs/` — figures, maps, and visualizations  
- `docs/` — supporting materials and summaries  

---

## ArcGIS StoryMap / Project Link

View the full interactive project here:  
👉 https://arcg.is/4jXmP1

---

## Tools & Technologies

- Python (Rasterio, NumPy, Pandas, Matplotlib)  
- ArcGIS Pro (Space-Time Cube, Emerging Hot Spot Analysis)  
- Landsat 8 Thermal Data  

---

## Future Work

- Apply workflow to alternative datasets (e.g., land surface temperature or coarser-resolution SST products)  
- Extend analysis to **longer temporal scales (30+ years)** for climatological insights  
- Perform trend analysis on **seasonal and annual timescales**  
- Improve artifact correction and preprocessing techniques for more reliable offshore analysis  

---

## Credits

California State University, Northridge  

This work was supported by the **NASA MOSAICS program** (Grant award #40046020)

---

## Citation

Halaby, A., Sepanian, A., & Giraldo, M. (2026).  
*Detecting Ocean Heat Pools in the Seaflower MPA: An application of remotely sensed data in San Andrés, Colombia.*  
California State University, Northridge.
