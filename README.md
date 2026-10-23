# BYD Companion (unofficial) — offline map packages

Offline map packages for **BYD Companion (unofficial)** (ckb «یاوەری BYD», ar «مرافق BYD»), an unofficial Android app for BYD drivers in the Kurdistan Region of Iraq. Not affiliated with or endorsed by BYD.

The app downloads the newest package from this repository's **latest release** when the driver opens *Offline maps* and taps download:

`https://github.com/XAlandK/byd-companion-maps/releases/latest/download/catalog.json`

Every file is checked against the SHA-256 in `manifest.json` before it is installed. Nothing else is stored here.

## Current package: Kurdistan Region 2026.10.21

Area: 34.0–37.45° N, 41.4–46.5° E. Map data as of 2026-10-21. Download size 270.9 MB.

| File | Contents | Bytes | SHA-256 |
|---|---|---|---|
| `basemap.pmtiles` | Vector basemap (PMTiles) | 172782819 | `c49dd6267b9213b3418bf826cc8b15af4e6c93b456c68957d35abe94c92e9e0a` |
| `style-assets.zip` | Map fonts and icons | 6268464 | `3267087e3b73a0a0c5ea1ca20ee753456d00abab97b8a0855bec8be55d9e6421` |
| `routing.tar.gz` | Offline routing tiles (Valhalla) | 49459907 | `3278eee8408f0a8898967a79193147519b0e23b9036a97cae5df13982e1d8e70` |
| `elevation.zip` | Elevation grid and bridges/tunnels | 16287692 | `e1a5f606bc918f7154370ff8120fd5ffce3ea3d4db2fead1879d39cc02673743` |
| `search.sqlite` | Place search index (SQLite) | 26103808 | `cd9e3d3e4e4b0e068f5a7e52a250b62279ba1cc524daf41bade4d90567471148` |

`catalog.json` lists the package; `manifest.json` describes its files and sources; `sources.json` repeats the data sources and licences.

## Data sources, licences and attribution

The map, routing, search and bridge/tunnel data are derived from OpenStreetMap. **The routing tiles, the search index and the bridges and tunnels in the elevation component are derivative databases made available under the [Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/)**; this repository distributes them in full.

### OpenStreetMap

- Used for: basemap, routing, search, elevation
- Licence: ODbL-1.0
- Attribution: © OpenStreetMap contributors
- Source: <https://www.openstreetmap.org/copyright>
- Date: 2026-10-21T20:21:46Z
- Note: Geofabrik extract iraq-261021.osm.pbf clipped to 41.4,34.0,46.5,37.45. Routing tiles, the search index and the bridges and tunnels of the elevation component (structures.qpst) are derived databases under ODbL; the build scripts are in tool/pipeline/. Routing uses Valhalla 3.9.1 tiles (Valhalla and valhalla-mobile are MIT-licensed software).

### Protomaps Basemap

- Used for: basemap
- Licence: Data ODbL-1.0 (OpenStreetMap); schema and styles BSD-3-Clause / CC0
- Attribution: Protomaps © OpenStreetMap
- Source: <https://protomaps.com>
- Version: 4.15.2 (build 20261021)

### Copernicus DEM GLO-90

- Used for: elevation
- Licence: Copernicus DEM licence (free and open, attribution required)
- Attribution: produced using Copernicus WorldDEM-90 © DLR e.V. 2010-2014 and © Airbus Defence and Space GmbH 2014-2018 provided under COPERNICUS by the European Union and ESA; all rights reserved
- Source: <https://registry.opendata.aws/copernicus-dem/>
- Note: Digital surface model (includes buildings and vegetation); ~90 m grid; vertical accuracy < 4 m LE90.

### Noto Sans glyphs

- Used for: styleAssets
- Licence: SIL Open Font License 1.1
- Attribution: Noto Sans © The Noto Project Authors
- Source: <https://github.com/protomaps/basemaps-assets>

### Protomaps sprites

- Used for: styleAssets
- Licence: MIT
- Attribution: Derived from tangrams/icons, © 2017 Mapzen
- Source: <https://github.com/protomaps/basemaps-assets>
- Note: Licence text ships as sprites/LICENSE.md inside style-assets.zip.

### ESA WorldCover

- Used for: basemap
- Licence: CC BY 4.0
- Attribution: © ESA WorldCover project / Contains modified Copernicus Sentinel data processed by ESA WorldCover consortium
- Source: <https://esa-worldcover.org>
- Note: Landcover layer of the Protomaps basemap at low zoom levels.

