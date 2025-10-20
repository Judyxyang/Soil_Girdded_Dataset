# Soil_Girdded_Dataset
West_South_Briabne_Gridded Dataset Building 

A detailed research plan on gridded climate–soil data modelling for the West–South Brisbane region, which aligns closely with BoM’s Hydro-Informatics and Surface Observations objectives. 
The work outlines a one-year framework that integrates traditional interpolation, machine-learning, 
and deep-learning fusion methods using open-source and freely available BoM datasets, ensuring that all analysis can be conducted without paid or restricted data access.

OpenSource Data: 
Dataset	Provider / Platform	Variable / Type	Spatial Resolution	Temporal Resolution / Coverage	Access Type	Primary Use
BoM AGCD	Bureau of Meteorology (Australia)	Rainfall, Tmax, Tmin (Interpolated from AWS)	0.05° (~5 km)	Daily 1900 → present	Open (BoM Climate Data Services)	Baseline climate fields; bias-correction reference
SILO	Dept of Environment & Science (QLD)	Gridded and station climate series (rainfall, Tmax)	~5 km grid / point	Daily 1889 → present	Open (LongPaddock API)	Core predictor; station validation for ML model
DEA Sentinel-2 Surface Reflectance	Digital Earth Australia / GA	NDVI (VIS–NIR indices)	10 m native → 1 km aggregate	5-day composite 2015 → present	Open (DEA STAC Hub)	NDVI covariate for rainfall/soil-moisture fusion
DEA Landsat Surface Reflectance	Digital Earth Australia / USGS	NDVI (long-term archive)	30 m → 1 km	16-day 1986 → present	Open (DEA)	Historical NDVI trend analysis (> 30 yrs)
SMIPS (Australia)	TERN / ANU / BoM	Soil moisture (model–data fusion)	1 km	Daily 2000 → present	Open (TERN portal)	Primary soil-moisture dataset for training and validation
SMAP Downscaled (1 km)	NASA / NSIDC / CSIRO	Soil moisture (passive microwave + MODIS downscaling)	1 km	Daily 2015 → present	Open (NASA EarthData)	Independent soil-moisture benchmark and fusion feature
SRTM DEM v3.0	NASA / USGS	Elevation, slope, aspect	30 m → 1 km	Static	Open (EarthExplorer)	Terrain covariate for regression-kriging and DL inputs
Copernicus CGLS Land Cover 100 m	EEA / Copernicus Service	Land-use / land-cover classification	100 m → 1 km	Annual 2015 → present	Open (CGLS Hub)	Land-cover covariate for spatial generalization
