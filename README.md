# Rêga — offline map packages

Offline map packages for **Rêga** (ckb «ڕێگا»), an Android app with offline maps, routes and voice guidance for drivers in the Kurdistan Region of Iraq, and an unofficial companion for BYD cars (not affiliated with or endorsed by BYD). Up to version 1.2.3 the app was called BYD Companion and then Rêga under another application id; every version reads these packages.

The app downloads the newest package from this repository's **latest release** when the driver opens *Offline maps* and taps download:

`https://github.com/XAlandK/byd-companion-maps/releases/latest/download/catalog.json`

Every file is checked against the SHA-256 in `manifest.json` before it is installed. Nothing else is stored here.

## Current package: Kurdistan Region 2026.11.08

Area: 34.0–37.45° N, 41.4–46.5° E. Map data as of 2026-11-08. Download size 272.3 MB.

| File | Contents | Bytes | SHA-256 |
|---|---|---|---|
| `basemap.pmtiles` | Vector basemap (PMTiles) | 173216428 | `7524aeb3d42cc5a8efb987ab0a6ae8994d8db6df9c19f7748b180d7743898d7b` |
| `style-assets.zip` | Map fonts and icons | 6268464 | `7a2be99b64eab1f52c1bf9325248ac7d583690359404b66188c720f19a9d5170` |
| `routing.tar.gz` | Offline routing tiles (Valhalla) | 49511578 | `785a0f182d1ffb3a9be279f563f61da418a133154e797f181c3314ea301a20bb` |
| `elevation.zip` | Elevation grid and bridges/tunnels | 16287417 | `bc86decdcfc64973c90338117714a64c58b1f475fc40270864f1b63e64f8c5d5` |
| `search.sqlite` | Place search index (SQLite) | 27004928 | `31491ef4a4becfec6b9fe89a20b86b1c38202fb476583207fcb127983bc9e1e7` |

`catalog.json` lists the package; `manifest.json` describes its files and sources; `sources.json` repeats the data sources and licences; `LICENSE-Overture-CDLA-Permissive-2.0.txt` is the agreement under which the Overture places are shared (also stored inside `search.sqlite`).

## Data sources, licences and attribution

The map, routing, search and bridge/tunnel data are derived from OpenStreetMap. **The routing tiles, the search index and the bridges and tunnels in the elevation component are derivative databases made available under the [Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/)**; this repository distributes them in full. The search index also holds places from Overture Maps, shared under the [Community Data License Agreement – Permissive 2.0](https://cdla.dev/permissive-2-0/), whose text is included with the data as that agreement requires.

### OpenStreetMap

- Used for: basemap, routing, search, elevation
- Licence: ODbL-1.0
- Attribution: © OpenStreetMap contributors
- Source: <https://www.openstreetmap.org/copyright>
- Date: 2026-11-08T21:21:00Z
- Note: Geofabrik extract iraq-261108.osm.pbf clipped to 41.4,34.0,46.5,37.45. Routing tiles, the search index and the bridges and tunnels of the elevation component (structures.qpst) are derived databases under ODbL; the build scripts are in tool/pipeline/. Routing uses Valhalla 3.9.1 tiles (Valhalla and valhalla-mobile are MIT-licensed software).

### Overture Maps places

- Used for: search
- Licence: CDLA-Permissive-2.0 (AllThePlaces places: CC0-1.0)
- Attribution: © Overture Maps Foundation
- Source: <https://docs.overturemaps.org/attribution/>
- Version: 2026-10-21.0
- Note: Businesses and other places from Overture Maps (mostly Meta, also Microsoft and AllThePlaces) that OpenStreetMap does not have yet: only the categories the app searches, confidence 0.8 or more, no Foursquare (Apache-2.0) places, none within 50 m of an OpenStreetMap place of the same kind or 150 m of one with the same name (tool/pipeline/search/build_index.py). The text of CDLA-Permissive-2.0 travels with the data in search.sqlite (meta key overture_license_text); also at https://cdla.dev/permissive-2-0/

### Protomaps Basemap

- Used for: basemap
- Licence: Data ODbL-1.0 (OpenStreetMap); schema and styles BSD-3-Clause / CC0
- Attribution: Protomaps © OpenStreetMap
- Source: <https://protomaps.com>
- Version: 4.15.2 (build 20261108)

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
