# Bay-of-Bengal-Temperature-Trends-1974-2023-

Workflow
Data Acquisition:
I imported the TerraClimate dataset, a global, high-resolution climate dataset.
I imported a custom-defined geometry representing the Bay of Bengal region from my Google Earth Engine (GEE) assets.

Data Preprocessing:
Variable Selection: I isolated the variable of interest, 'tmmx' (monthly maximum temperature), from the larger TerraClimate dataset.
Unit Conversion: The raw tmmx data is stored in Kelvin multiplied by 10. I created a function (scaleImage) to map over every image in the collection, converting the values to degrees Celsius by multiplying by 0.1. This is a crucial step for correct interpretation.
Metadata Preservation: The copyProperties function ensures the crucial timestamp for each image is retained after the scaling operation.

Data Filtering:
I filtered the scaled temperature collection by two criteria:
Temporal Filter: A 50-year period from 1974-01-01 to 2024-01-01.
Spatial Filter: The geographic boundary of the Bay of Bengal.

Time Series Visualization:
I used GEE's ui.Chart.image.series method to create a time series chart.
Aggregation: For each monthly image in the filtered collection, the ee.Reducer.mean() calculates the average maximum temperature over the entire Bay of Bengal region.
Scale: The scale parameter (4638 meters) defines the spatial resolution at which the reduction is performed, which is the native resolution of the TerraClimate tmmx band.

Chart Customization: 
I set various options like the title, axis labels, and styling to make the chart clear and publication-ready. interpolateNulls helps create a smooth line by filling in any missing data points.
