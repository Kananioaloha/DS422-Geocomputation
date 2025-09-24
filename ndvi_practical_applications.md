# 🌿 NDVI Analysis Project Worksheet  

This worksheet will guide you through the process of designing and carrying out an NDVI-based analysis in R. Fill in the prompts for your chosen research question, location, time period, data sources, and methods.  

---

## 1. Framing the Question  

**What environmental or social issue will you explore?**  
Forest health and invasive grass spread around Kealakekua Mountain Reserve

---

**Why is NDVI an appropriate tool for this question?**  
NDVI shows “greenness,” so it’s good for spotting healthy canopy vs. dry/invaded areas.
- Spatial, stalite, identify areas

---

**Who might find your results meaningful or useful?**  
Hiki Ola/KMR crews, DLNR, local schools, community partners, and fire/fuel managers.

---

## 2. Choosing a Place and Time  

**What geographic area will you focus on?**  
Kealakekua Mountain Reserve (ma uka of Kona) and a small buffer around it.

---

**What time frame makes sense for your question?**  
(e.g., single date, multiple years, seasonal patterns)  
Seasonal check (wet vs. dry) across multiple years, e.g., 2019–2025.

---

**How will you define the scope of your analysis?**  
Compare fenced/restoration plots vs. nearby unfenced areas at the same elevation bands.


---

## 3. Finding Data  

**Where could you get satellite imagery or NDVI data?**  
Copernicus Browser Sentinel-2 L1C, two images a year from 2019-2025 wet and dry seasons

---

**What resolution and frequency are appropriate?**  
low cloud coverage

---

**Will you download data manually or use an R package? Which one?**  
download manually off of capernicus browser

---

## 4. Bringing Data into R  

**What R packages can help you work with spatial data?**  
terra (rasters), sf (vectors), dplyr (wrangle), ggplot2 (maps/plots), lubridate (dates), ggspatial

---

**How will you handle projections, boundaries, or missing data?**  
na.rm = TRUE
- load data for mapping, reproject, treat clouds as N/A

---

**What file formats will you be working with?**  
Inputs: Sentinel-2 JP2 bands inside .SAFE folders; AOI as Shapefile or GeoJSON.
Outputs: NDVI GeoTIFF (.tif), summary CSV, and map figures PNG.

---

## 5. Calculating NDVI  

**What is the NDVI formula?**  
NDVI = (NIR − Red) / (NIR + Red)

---

**Which spectral bands are needed?**  
Sentinel-2: B8 (NIR, 10 m) and B4 (Red, 10 m).

---

**How will you apply this formula in R?**  
Load B4 and B8 with terra, crop to my AOI, compute (nir - red)/(nir + red), mask clouds/shadows using the Sentinel-2 SCL layer, and save NDVI as a GeoTIFF.

---

## 6. Exploring and Visualizing Data  

**How will you summarize NDVI values?**  
(maps, plots, tables)  
Make a simple NDVI map (wet vs. dry), a histogram of NDVI, a boxplot comparing areas (e.g., inside vs. outside fence), and a small table with mean/median NDVI by season × year.

---

**Will you compare locations, beofre and after events, look at seasonal patterns, or study long-term trends?**  
(1) Locations: inside fenced/restoration plots vs. nearby unfenced areas; (2) Before/After: weed control or planting events; (3) Seasonal: wet vs. dry season each year; (4) Long-term: trends from 2019–2025.

---

**How will you make your visualizations clear and interpretable?**  
Use the same NDVI color scale and breaks across maps; add titles with date/season, a legend, and AOI/plot outlines. Mask clouds/shadows so they show as NA/blank. Keep large labels, simple fonts, and include a scale bar & north arrow. For plots, label axes, show sample sizes, and use boxplots/time-series with clear captions.

---

## 7. Interpreting Results  

**What patterns or relationships do you expect to see?**  
Higher NDVI inside fences vs. outside; wet season > dry season; gradual NDVI increase over years where restoration is working; possible dips after drought/wildfire; lower NDVI at hotter, lower-elevation grass areas.

---

**How do they relate to your research question?**  
They show whether restoration is improving canopy/ground cover, where invasive grasses persist, and how seasonal affects fuel buildup—guiding where to focus planting, weeding, and monitoring.

---

**What uncertainties or data limitations should you acknowledge?**  
Clouds/shadows and terrain effects; mixed pixels at 10 m; NDVI saturation in dense canopy; NDVI can’t tell native vs. invasive by itself; date mismatches between “before” and “after”; sensor/atmospheric differences across scenes.

---

## 8. Reflecting on Impact  


**Could your results inform decisions, policies, or further research?**  
Yes—prioritize weeding/planting sites, schedule work before dry season, support funding reports, update fuel-risk maps, and share with local schools/community partners.
---

**What new questions emerge from your findings?**  
Which species or structure drive NDVI gains? How do NDVI changes track rainfall/elevation? Can adding NDWI/NBR improve drought or burn-scar detection? What ground-truth data (plots, photo-points) is needed to verify trends?
