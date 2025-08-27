# Exploring Relationship Between Land Surface Temperature (LST) and Spectral Indices in Urban and Rural Areas

This project investigates the relationship between **Land Surface Temperature (LST)** and key **spectral indices** — NDVI, NDWI, and NDBI — in **urban (Nashik City)** and **rural (Alandi Watershed)** areas of Maharashtra, India using **Landsat 8 (OLI & TIRS) imagery**.  
It highlights the role of vegetation, water bodies, and built-up areas in regulating land surface temperature, contributing to urban heat island (UHI) studies and sustainable urban planning.

---

## Objectives
- Analyze and compare **LST** with **NDVI, NDWI, and NDBI** in urban and rural areas.
- Quantify the **cooling effects** of vegetation and water bodies.
- Evaluate the **thermal impact of urbanization** and provide spatial evidence for sustainable land-use policies.

---

## Datasets
- **Satellite Data**: Landsat 8 OLI & TIRS (Surface Reflectance + Thermal Bands)
  - Band 4 (Red)  
  - Band 5 (NIR)  
  - Band 6 (SWIR)  
  - Band 10 (Thermal Infrared)  
- **Vector Data**:  
  - Nashik Municipal Corporation Boundary (`NMCf.shp`)  
  - Alandi Watershed Boundary (`Alandi_Watershed.shp`)  

Data Source: [USGS Landsat Collection](https://earthexplorer.usgs.gov/)  

---

## Tools & Libraries
The analysis was carried out in Python using the following geospatial libraries:
- `rasterio` – for raster reading/writing  
- `geopandas` – for vector data handling  
- `numpy` – for array manipulation & calculations  
- `matplotlib`, `seaborn` – for data visualization  

---

## Methodology
1. **Preprocessing**
   - Downloaded and reprojected Landsat bands to **UTM Zone 43N (EPSG:32643)**.
   - Clipped imagery using **urban (Nashik)** and **rural (Alandi)** shapefiles.
   
2. **Computation of Spectral Indices**
   - **NDVI** = (NIR – Red) / (NIR + Red)  
   - **NDWI** = (NIR – SWIR) / (NIR + SWIR)  
   - **NDBI** = (SWIR – NIR) / (SWIR + NIR)  

3. **Land Surface Temperature (LST)**
   - Derived from **Thermal Band 10** using radiative transfer equations.  
   - Converted radiance → brightness temperature → LST (in °C).  

4. **Visualization & Analysis**
   - Generated **NDVI, NDWI, NDBI, and LST maps**.  
   - Compared urban vs. rural statistics and correlations.  

---

## Results
- **Urban areas (Nashik)**:  
  - Low NDVI & NDWI, high NDBI → Higher LST (≈ 36°C).  
- **Rural areas (Alandi Watershed)**:  
  - High NDVI & NDWI, low NDBI → Lower LST (≈ 25–30°C).  

**Correlation Findings**:  
- LST vs NDVI → Negative (r = -0.72)  
- LST vs NDWI → Negative (r = -0.64)  
- LST vs NDBI → Positive (r = +0.79)  

Vegetation and water bodies **reduce LST** through evapotranspiration & higher albedo.  
Built-up surfaces **increase LST**, intensifying **Urban Heat Island** effects.  

---

## Repository Structure

