##Bay of Bengal Climate Change Analysis: Quantifying Sea Surface Temperature Warming (1982-2023)

I conducted a comprehensive climate change analysis of the Bay of Bengal, processing 42 years of satellite data to quantify sea surface temperature warming trends. The project involved a complete end-to-end geospatial workflow from data acquisition in Google Earth Engine to advanced statistical analysis in Python, identifying statistically significant warming patterns across the region.

The Complete Process:

Phase 1: Data Acquisition & Preparation (Google Earth Engine)
Dataset Selection: Used NOAA OISST V2.1 dataset - the gold standard for sea surface temperature monitoring
Temporal Scope: Extracted monthly data from January 1982 to December 2023 (504 months total)
Spatial Scope: Focused on Bay of Bengal region using custom geographic boundaries
Data Processing: Created monthly median composites to reduce noise and cloud contamination
Export Strategy: Generated multi-band GeoTIFF with 504 bands (one per month) for efficient time series analysis
Technical Implementation: Wrote Earth Engine JavaScript code to filter, process, and export data to Google Drive

Phase 2: Data Transfer & Infrastructure Setup
Cloud Pipeline: Established seamless data flow: Earth Engine → Google Drive → Google Colab
Storage Management: Organized 500+ MB of multi-temporal raster data for efficient access
Environment Setup: Configured Colab notebook with professional geospatial Python stack
Data Validation: Verified file integrity and spatial properties after transfer

Phase 3: Data Processing & Quality Control (Python/Colab)
Data Loading: Used Rasterio to read 504-band GeoTIFF with proper spatial referencing
Critical Discovery: Identified data storage issue - values stored with -273.15 offset (appeared as -250°C range)
Data Correction: Applied transformation: raw_data + 273.15 to obtain realistic 18-32°C SST range
Quality Validation: Verified corrected values against known Bay of Bengal temperature ranges
Temporal Alignment: Parsed band names to create proper datetime indices for time series analysis
Spatial Validation: Confirmed 5km resolution and proper geographic projection

Phase 4: Advanced Statistical Analysis
Regional Time Series: Calculated area-weighted average SST for each of 504 months
Trend Detection: Applied Ordinary Least Squares (OLS) regression to identify warming rate
Statistical Significance: Used p-value < 0.05 threshold and Mann-Kendall non-parametric test
Pixel-wise Analysis: Implemented vectorized linear regression across all 150,176 spatial pixels
Spatial Patterns: Mapped geographic distribution of warming trends and significance levels
Climate Context: Compared results against global ocean warming benchmarks from IPCC reports

Phase 5: Visualization & Professional Outputs
Time Series Plots: Created interactive charts showing 42-year trend with rolling averages
Spatial Maps: Generated publication-quality maps of mean SST and warming patterns
Statistical Dashboards: Built comprehensive visualizations of trend distributions and seasonal cycles
GIS Exports: Produced GeoTIFF files of trend maps for further spatial analysis
Data Reports: Compiled CSV files with time series data and statistical summaries

Phase 6: Interpretation & Climate Impact Assessment
Scientific Context: Compared Bay of Bengal warming against global ocean averages
Ecological Implications: Assessed potential impacts on marine ecosystems and fisheries
Climate Significance: Evaluated regional warming in context of global climate change
Methodological Validation: Verified results through multiple statistical approaches
Professional Documentation: Created comprehensive analysis report with methodology and findings

Key Outcomes & Implications

Primary Finding:
The Bay of Bengal is warming at 0.178°C per decade - 62% faster than the global ocean average, with this warming affecting 67.7% of the region at statistically significant levels.

Scientific Implications:
Accelerated coastal ecosystem changes and coral bleaching risks
Increased marine heatwave frequency impacting fisheries and biodiversity
Sea level rise contributions from thermal expansion effects
Regional climate pattern shifts affecting monsoon systems

Technical Achievement:
Transformed 504 raw satellite images into actionable climate insights through an end-to-end geospatial workflow.
