# LOD2_heating_demand
# Overview

This repository contains the necessary scripts and data to calculate the heating demand of buildings using Level of Detail 2 (LOD2) 3D building data, along with specific U-values, air change rates, and other building parameters. It is capable of filtering building geometries based on OpenStreetMap data and address lists, calculating 3D polygon areas, and processing LOD2 data to determine the thermal characteristics of buildings.

# Structure

The repository is structured as follows:

    data/: Contains TRY (Test Reference Year) data used for calculating the heating demand.
    examples/: Contains example GeoJSON and shapefiles for the cities of Bautzen, Görlitz, and Zittau.
    scripts/: Contains Python scripts for filtering LOD2 data and calculating heating demand.
    The root directory contains license information, requirements, and this README.

# Scripts

    filter_LOD2.py: Filters LOD2 building data based on OpenStreetMap and a list of addresses. It also includes functions to spatially filter data using a polygon and to calculate areas of 3D polygons.
    heat_requirement_DIN_EN_12831.py: Defines the Building class that calculates the heating demand and warm water demand based on DIN EN 12831 standards. It uses building dimensions, U-values, and weather data.

# How to Use

To use the scripts and calculate heating demand:

    Ensure you have the required dependencies installed by running pip install -r requirements.txt.
    Place your LOD2 data and shapefiles within the examples/ directory according to the city you are focusing on.
    Adjust the file paths in the script filter_LOD2.py to match your LOD2 and shapefile data locations.
    Run the filter_LOD2.py script to filter the LOD2 data based on OSM data and address lists.
    Use the calculate_heat_demand_for_lod2_area function in heat_requirement_DIN_EN_12831.py to calculate the heat demand for the filtered LOD2 area. Set the paths to your input files accordingly.

# Data Format

The expected data format for the input files is as follows:

    TRY data: A .dat file with hourly temperature data for the reference year.
    GeoJSON for LOD2 and OSM data.
    CSV for address lists, containing at least the columns Stadt and Adresse.

# To Do

At present, the LOD2 data must be procured in the form of a shapefile, which then requires opening with QGIS and exporting as a GeoJSON file for subsequent processing in Python. Additionally, the required polygon must be constructed using QGIS.

# License

This project is licensed under the MIT License - see the LICENSE file for details.
