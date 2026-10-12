# Database Documentation

This folder documents the spatial database logic used in the Orchard WebGIS project.

The project used PostgreSQL/PostGIS to organize harmonized orchard spatial layers before publication through GeoServer and visualization in the WebGIS client.

---

## Database Role

The spatial database was used to store and manage the harmonized orchard layers in a structured and queryable format.

The database workflow focused on:

- storing validated tree-crown polygons
- preserving unique tree identifiers
- maintaining a consistent coordinate reference system
- linking apple-observation points to crown polygons
- separating internal storage from publication-ready layers

---

## Spatial Data Model

The database structure was based on two main spatial layer types:

1. **Tree-crown polygons**  
   These represented stable tree-level spatial units used as the main operational layer of the WebGIS.

2. **Apple-observation points**  
   These represented clustered apple-observation locations linked to crown polygons through the `polygon_id` field.

This structure allowed the WebGIS to support tree-level visualization, feature inspection, and linked observation display.

---

## Storage and Publication Logic

The database design separated internal storage layers from simplified publication layers.

This separation was useful because the WebGIS did not need to expose the full internal database structure. Instead, publication-ready layers were prepared with the fields required for visualization, querying, and feature inspection.

The general logic was:

```text
Internal spatial data
        ↓
PostGIS storage tables
        ↓
Publication-ready layers
        ↓
GeoServer services
        ↓
Leaflet WebGIS client
```

---

## Key Database Concepts

The database workflow emphasized:

- valid geometries
- stable feature identifiers
- consistent CRS management
- simplified publication views
- spatial linkage between polygons and points
- WebGIS-ready attribute organization

---

## Notes

The original database dump and raw project data are not included in this repository.

This folder is intended to document the database design logic used in the thesis project rather than distribute restricted research data.
