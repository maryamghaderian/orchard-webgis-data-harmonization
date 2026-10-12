# Orchard WebGIS: Data Harmonization to Publication

This repository presents the portfolio version of my Master’s thesis project:

**Design and Implementation of an Orchard WebGIS: Data Harmonization to Publication**  
Master’s Degree in Agritech Engineering  
Politecnico di Torino, 2026

---

## Project Overview

This project demonstrates a complete GIS and WebGIS workflow for transforming orchard spatial data into structured, harmonized, and publishable geospatial information.

The workflow starts from LiDAR-derived orchard data and tree-crown spatial units, continues through crown delineation evaluation and data harmonization, and ends with the publication of orchard layers through a local WebGIS architecture.

The final system was designed to support tree-level visualization, feature inspection, layer interaction, and browser-based access to harmonized orchard information.

---

## Main Objectives

- Generate and evaluate tree-crown spatial units from LiDAR-derived orchard data
- Compare crown delineation outputs using object-level and geometric metrics
- Select a stable crown layer suitable for WebGIS publication
- Harmonize apple-observation records and link them to crown polygons
- Organize the spatial layers in PostgreSQL/PostGIS
- Publish the harmonized layers through GeoServer
- Implement a browser-based WebGIS client using Leaflet, TypeScript, and Vite

---

## Workflow

The implemented workflow includes the following stages:

1. LiDAR-derived orchard data preparation
2. Tree-crown delineation and method comparison
3. Crown-layer validation and selection
4. Apple-observation data harmonization
5. Spatial database structuring in PostgreSQL/PostGIS
6. WebGIS layer publication through GeoServer
7. Browser-based visualization using Leaflet

---

## Technical Stack

- **GIS and spatial analysis:** QGIS, LiDAR-derived spatial data, crown polygons
- **Spatial database:** PostgreSQL/PostGIS
- **Map server:** GeoServer
- **WebGIS client:** Leaflet, TypeScript, Vite
- **Deployment environment:** Docker, Nginx
- **Coordinate reference system:** EPSG:32632

---

## Key Results

- A validated crown layer containing **56 tree-crown polygons** was prepared for WebGIS publication.
- Apple-observation records were harmonized into **103 clustered observation points**.
- The crown polygons and apple-observation points were linked through a spatial relationship using `polygon_id`.
- The harmonized layers were stored in PostGIS and published through GeoServer.
- A local WebGIS prototype was implemented for layer visualization, Tree ID search, feature inspection, filtering, selection, basemap switching, and distance measurement.

---

## Repository Structure

```text
orchard-webgis-data-harmonization/
│
├── assets/      # Screenshots, diagrams, and visual material
├── data/        # Data availability notes
├── database/    # Database schema and PostGIS-related documentation
├── docs/        # Thesis and project documentation
├── webgis/      # WebGIS implementation notes and client-related files
└── README.md
```

---

## Data Availability

The original orchard datasets are not publicly included in this repository because they may contain project-specific or restricted research data.

This repository focuses on documenting the workflow, data harmonization logic, database structure, WebGIS publication process, and thesis outputs.

---

## Project Status

This project is presented as an academic and professional portfolio project.  
The implemented WebGIS was developed and tested as a local prototype.

---

## Author

**Maryam Ghaderian**  
Master’s Graduate in Agritech Engineering  
Politecnico di Torino  
GIS | WebGIS | Spatial Data Harmonization | PostGIS | GeoServer | Leaflet
