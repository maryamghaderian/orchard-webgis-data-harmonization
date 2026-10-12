# Technical Notes

This document provides additional technical notes for the Orchard WebGIS portfolio project.  
It complements the main README by describing the data structure, database logic, publication workflow, and prototype scope in more technical terms.

---

## 1. Data Organization Logic

The project was designed around the idea that orchard information should be organized using stable tree-level spatial units.

In this workflow, the crown polygon layer was treated as the main operational spatial layer. Each crown polygon represented one tree-level unit that could be stored, queried, published, and inspected through the WebGIS.

The apple-observation layer was organized as a complementary point layer. Each point represented a clustered apple-observation location and was linked to the corresponding crown polygon through the `polygon_id` field.

This structure allowed the WebGIS to display both crown polygons and linked observation points in a consistent tree-level framework.

---

## 2. Crown Layer Preparation

The final crown layer was selected for WebGIS publication because the system required complete and stable tree-level spatial units.

Before publication, the crown layer was prepared with the following requirements:

- valid polygon geometries
- unique tree identifiers
- consistent coordinate reference system
- publication-ready attribute structure
- stable feature identity for WebGIS inspection

The final publication layer contained 56 tree-crown polygons.

---

## 3. Apple-Observation Harmonization

The original apple-observation records were not published directly.

They were first harmonized through:

- duplicate reduction
- point-in-polygon linkage
- distance-based clustering
- linkage to crown polygons through `polygon_id`

This process produced 103 representative clustered apple-observation points.

The purpose of this step was to transform raw observation records into a cleaner point layer that could be displayed and queried in relation to tree-crown polygons.

---

## 4. Spatial Database Structure

The harmonized data were organized in PostgreSQL/PostGIS.

The database design separated internal storage from publication-ready layers. This distinction is important because a WebGIS does not always need to expose the complete internal database structure.

The general logic was:

- storage tables keep the more complete internal dataset
- publication layers expose only the fields needed for visualization, querying, and WebGIS interaction
- geometry and identifier consistency are preserved before publication

This structure made the data easier to manage, publish, and inspect.

---

## 5. WebGIS Publication Workflow

GeoServer was used as the map-service layer between the PostGIS database and the WebGIS client.

The publication workflow followed this general sequence:

1. Harmonized spatial layers were stored in PostGIS.
2. Publication-ready layers were prepared for WebGIS use.
3. GeoServer published the selected layers as web services.
4. The WebGIS client requested and displayed the published layers in the browser.

This approach avoided treating the WebGIS as a simple static map. Instead, the system followed a database-driven WebGIS workflow.

---

## 6. WebGIS Client

The browser-based WebGIS client was implemented using Leaflet, TypeScript, and Vite.

The client supported:

- display of tree-crown polygons
- display of clustered apple-observation points
- layer visibility control
- Tree ID search
- feature inspection
- pop-up information
- feature selection
- basemap switching
- distance measurement

The WebGIS interface was used to verify that the harmonized layers could be accessed and inspected through a browser-based environment.

---

## 7. Local Deployment Environment

The prototype was developed and tested in a local deployment environment.

The main components were:

- PostgreSQL/PostGIS for spatial data storage
- GeoServer for spatial layer publication
- Nginx for serving the WebGIS client
- Docker for organizing the local services

This local architecture was suitable for testing the complete workflow from database storage to browser-based WebGIS access.

---

## 8. Prototype Scope and Limitations

This repository presents the portfolio version of an academic thesis project.

The system should be interpreted as a local read-only WebGIS prototype, not as a production-ready deployment.

The original orchard datasets are not included in this repository because they may contain project-specific or restricted research data.

The main purpose of this repository is to document the workflow, technical structure, and WebGIS publication logic rather than to distribute the original research data.

---

## 9. Skills Represented

This project demonstrates applied experience in:

- GIS workflow design
- spatial data harmonization
- tree-crown polygon preparation
- LiDAR-derived orchard data organization
- PostgreSQL/PostGIS database structuring
- GeoServer layer publication
- Leaflet-based WebGIS implementation
- Docker-based local deployment
- technical documentation for geospatial projects
