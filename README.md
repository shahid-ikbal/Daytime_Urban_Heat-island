# Daytime_Urban_Heat-island
This script visualizes the Urban Heat Island (UHI) effect over Pakistan using Google Earth Engine (GEE). The UHI dataset used in this script highlights the difference in temperature between urban and rural areas, focusing on daytime heat intensity. The region of interest is defined using a shapefile for Pakistan, which is imported as a feature collection (`users/shahidiqbal/Pak`). This ensures that all subsequent analysis and visualization are limited to Pakistan's geographical boundaries.

The UHI dataset is loaded from the Google Earth Engine data catalog (`YALE/YCEO/UHI/Summer_UHI_yearly_pixel/v4`). The images within the dataset are mosaicked into a single layer using the `.mosaic()` method and clipped to the Pakistan boundary with `.clip(pakistan)` to exclude data outside the region of interest. Visualization parameters are then defined to display the "Daytime" band of the dataset, with a color palette transitioning from blue (low heat intensity) to red (high heat intensity). The minimum and maximum values for the visualization are set to -1.5 and 7.5, respectively, representing a range of UHI intensity levels.

The script adds the processed UHI dataset as a layer to the map using `Map.addLayer`, alongside a hollow blue outline representing Pakistan's boundary for reference. The map is then centered on Pakistan with a zoom level of 6 using `Map.centerObject`.

A legend is created to provide context for the visualization, showing the UHI intensity categories and their corresponding colors. The legend is dynamically built using a list of items, where each item specifies a color and a descriptive label for a range of UHI values. For example, colors like blue represent "Very Low" intensity (-1.5 to 0), while red shades represent "Critical" intensity (>7.5). The legend is styled and positioned at the bottom-left of the map and added using `Map.add`.

This script provides an intuitive visualization of the UHI effect in Pakistan, helping to identify areas with varying levels of heat intensity and facilitating informed decision-making for climate adaptation and urban planning.

In this code I have used the Pakistan you can change your AOI (area of interest)
