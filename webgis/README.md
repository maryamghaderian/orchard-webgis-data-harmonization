# WebGIS Documentation

This folder documents the WebGIS implementation logic used in the Orchard WebGIS project.

The WebGIS client was designed to provide browser-based access to harmonized orchard spatial layers published from a PostGIS and GeoServer workflow.

---

## WebGIS Role

The WebGIS acted as the final access layer of the project.

Its purpose was to make the harmonized orchard information visible, searchable, and inspectable through a browser-based interface rather than through desktop GIS software only.

The WebGIS was used to display:

- validated tree-crown polygons
- clustered apple-observation points
- linked spatial information between crowns and observations

---

## WebGIS Architecture

The WebGIS followed a database-driven publication workflow:

```text
PostgreSQL/PostGIS
        ↓
GeoServer
        ↓
Web map services
        ↓
Leaflet WebGIS client
        ↓
Browser-based user interface
```

This structure allowed the spatial data to remain managed in the database while the user accessed the published layers through the WebGIS interface.

---

## Client-Side Implementation

The browser-based client was implemented using:

- **Leaflet** for interactive web mapping
- **TypeScript** for organizing client-side code
- **Vite** as the frontend development and build tool
- **Nginx** for serving the local WebGIS client
- **Docker** for organizing the local deployment environment

---

## Main WebGIS Functions

The implemented WebGIS prototype supported:

- tree-crown polygon visualization
- clustered apple-observation point visualization
- layer visibility control
- Tree ID search
- feature inspection
- popup-based attribute display
- feature selection
- basemap switching
- distance measurement

These functions were used to verify that the harmonized orchard layers could be accessed and inspected through a browser-based environment.

---

## Published Layers

The WebGIS focused on two main publication layers:

1. **Tree-crown polygon layer**  
   This was the main operational layer of the WebGIS. Each polygon represented one tree-level spatial unit.

2. **Apple-observation point layer**  
   This was a complementary point layer. Each point represented a clustered apple-observation location linked to a crown polygon through `polygon_id`.

Together, these layers allowed the WebGIS to support tree-level visualization and linked observation inspection.

---

## Prototype Scope

The WebGIS was developed and tested as a local read-only prototype.

It was designed to demonstrate the complete publication chain from harmonized spatial data to browser-based access.

The prototype should not be interpreted as a production-ready WebGIS deployment. Additional work would be required for public hosting, authentication, editing tools, performance testing, and multi-user access.

---

## Notes

The original WebGIS source code and raw project datasets are not included in this repository.

This folder documents the WebGIS design and implementation logic for portfolio and technical review purposes.
