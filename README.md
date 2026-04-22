# Inventory Digital — Tanzania Coastal Marine Monitoring

An interactive web-based digital inventory for benthic ecological surveys and fisheries monitoring along the coastal waters of Tanzania. Built with R (Quarto) and Leaflet, this tool visualises monitoring stations, marine managed areas, community fisheries zones, benthic habitat classifications, and catch assessment data within a single interactive map interface.

Developed in partnership with **[The Nature Conservancy](https://www.nature.org/)**.

---

## Overview

Tanzania's coastal and marine ecosystems — coral reefs, seagrass beds, and soft-sediment communities — support critical biodiversity and the livelihoods of millions of people. This project provides a spatial inventory tool to:

- Track benthic habitat condition across key monitoring sites
- Visualise Community Fisheries Management Areas (CFMAs) and Community Managed Groups (CMGs)
- Display Marine Managed Areas (MMAs) and their spatial extent
- Map landing sites and associated Catch Assessment Survey (CAS) data
- Explore Allen Coral Atlas benthic habitat classifications

---

## Features

| Feature | Description |
|---|---|
| 🗺️ Interactive maps | Toggle between OpenStreetMap, Satellite (Esri), and Light (CartoDB) base layers |
| 📍 Monitoring stations | Clickable markers showing station name, MMA, zone, coral cover %, and bleaching level |
| 🟦 Monitoring zones | Colour-coded polygons by management zone |
| 🐠 Benthic habitat | Allen Coral Atlas classes (Coral/Algae, Seagrass, Rock, Rubble, Sand, Microalgal Mats) |
| ⚓ Landing sites | CAS-linked landing sites with catch composition popups (species priority breakdown) |
| 🏞️ CFMAs & MMAs | Community fisheries management zones and marine managed areas |
| ✏️ Draw toolbar | Draw polylines, polygons, circles, rectangles, and markers on the map |
| 📥 GeoJSON export | Export drawn annotations as a `.geojson` file |
| 🔍 Station search | Search for monitoring stations by name |
| 📏 Measurement tool | Measure distances (km/m) and areas (sqm/ha) |
| 🧭 Mini-map | Collapsible overview mini-map |
| 📌 Locate me | GPS-based centering |

---

## Data Sources

| File | Description |
|---|---|
| `allen_benthic_simplified_mapshaper.gpkg` | Allen Coral Atlas benthic habitat polygons (simplified) |
| `cfmas.gpkg` | Community Fisheries Management Areas (CFMAs) and CMG polygons |
| `mma.gpkg` | Marine Managed Areas with management class and region |
| `unguja_north_benthic.gpkg` | North Unguja benthic survey data |
| `labelset.csv` | Benthic label taxonomy (name, short code, functional group) |
| `monitoring_stations.csv` | Monitoring station coordinates, MMA, zone assignments *(not tracked in git)* |
| `monitoring_zones.gpkg` | Monitoring zone polygons *(not tracked in git)* |
| `landing_sites.gpkg` | Coastal landing site locations *(not tracked in git)* |
| `CAS Data_Indian Ocean_...csv` | Catch Assessment Survey data *(not tracked in git)* |

### Benthic Label Categories (`labelset.csv`)

| Functional Group | Labels |
|---|---|
| Hard coral | Hard coral (branching, encrusting, massive), *Porites* branching |
| Other Invertebrates | Sea urchins, holothurians, soft coral, sponge |
| Soft Substrate | Mud, sand, shell hash/gravel |
| Hard Substrate | Dead coral, rock |
| Algae | Fleshy algae, CCA, *Halimeda*, turf algae |
| Seagrass | Seagrass |
| Other | Rubble, no data, other |

---

## Requirements

### R Packages

```r
install.packages(c(
  "sf",
  "tidyverse",
  "gt",
  "leaflet",
  "leaflet.extras",
  "leafpop",
  "janitor"
))
```

### Software

- [R](https://www.r-project.org/) ≥ 4.2
- [Quarto](https://quarto.org/) ≥ 1.3

---

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/lugoga/inventory-digital.git
   cd inventory-digital
   ```

2. Place the required data files (listed above) in the project root directory.

3. Render the Quarto document:
   ```bash
   quarto render index.qmd
   ```
   This will produce a self-contained `index.html` interactive map.

4. Open `index.html` in a web browser.

---

## Map Navigation

| Action | How |
|---|---|
| Switch base layer | Use the layer control (top right) |
| Show/hide overlays | Toggle "Station" and "Zones" in the layer control |
| View station details | Click a circle marker |
| Search for a station | Use the search box on the map |
| Measure distance/area | Use the ruler tool (bottom left) |
| Draw on the map | Use the draw toolbar (left side) |
| Export drawn shapes | Click the download button (💾) |
| Reset view | Click the 🌐 button |
| Centre on your location | Click the ⊕ button |

---

## Study Area

The primary study area covers the coastal waters of **Tanzania**, centred around **Zanzibar** and the adjacent mainland coast (approximately 6.5°S, 39.3°E). This includes:

- Unguja (Zanzibar) — northern benthic survey sites
- Pemba Island — CFMA/CMG zones
- Tanzania mainland coast — landing sites and CAS monitoring network

---

## License

This project is developed for conservation and fisheries management purposes. Please contact the project maintainers or The Nature Conservancy for data use and licensing inquiries.

---

## Contact

For questions about data, methodology, or collaboration, please open an issue or contact the repository maintainer via GitHub.
