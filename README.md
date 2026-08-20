# Switzerland Administrative Divisions / Schweiz



## Overview

| Item | Details |
|------|---------|
| Canton | 26 |
| District | 148 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/ch](https://openadmindata.org/ch/) |
| API | [openadmindata.org/api/ch](https://openadmindata.org/api/ch/) |
| Flag | [PNG](https://onlygames.me/flags-png/ch/) · [SVG](https://onlygames.me/flags-svg/ch/) · [PDF](https://onlygames.me/flags-pdf/ch/) |
| National Anthem | [🎵 Listen & Download Switzerland National Anthem MP3](https://onlygames.me/national-anthems/ch/) |

## Browse by Canton

| # | Canton | Districts | Link |
|---|----|----|------|
| 1 | Glarus | 1 | [Browse](divisions/glarus-ch01/) |
| 2 | Graubünden (Graubunden) | 11 | [Browse](divisions/graubunden-ch02/) |
| 3 | Zug | 1 | [Browse](divisions/zug-ch03/) |
| 4 | Ticino | 8 | [Browse](divisions/ticino-ch04/) |
| 5 | Appenzell Innerrhoden | 1 | [Browse](divisions/appenzell-innerrhoden-ch05/) |
| 6 | Valais | 13 | [Browse](divisions/valais-ch06/) |
| 7 | Schaffhausen | 6 | [Browse](divisions/schaffhausen-ch07/) |
| 8 | Genève (Geneva) | 1 | [Browse](divisions/geneva-ch08/) |
| 9 | Basel-Stadt (Basel-City) | 1 | [Browse](divisions/basel-city-ch09/) |
| 10 | Fribourg | 7 | [Browse](divisions/fribourg-ch10/) |
| 11 | Schwyz | 6 | [Browse](divisions/schwyz-ch11/) |
| 12 | Zürich (Zurich) | 13 | [Browse](divisions/zurich-ch12/) |
| 13 | Nidwalden | 1 | [Browse](divisions/nidwalden-ch13/) |
| 14 | Luzern (Lucerne) | 6 | [Browse](divisions/lucerne-ch14/) |
| 15 | Vaud | 11 | [Browse](divisions/vaud-ch15/) |
| 16 | Aargau | 11 | [Browse](divisions/aargau-ch16/) |
| 17 | Thurgau | 6 | [Browse](divisions/thurgau-ch17/) |
| 18 | St. Gallen (Saint Gallen) | 9 | [Browse](divisions/saint-gallen-ch18/) |
| 19 | Jura | 3 | [Browse](divisions/jura-ch19/) |
| 20 | Appenzell Ausserrhoden | 3 | [Browse](divisions/appenzell-ausserrhoden-ch20/) |
| 21 | Neuchâtel (Neuchatel) | 1 | [Browse](divisions/neuchatel-ch21/) |
| 22 | Basel-Landschaft (Basel-Country) | 5 | [Browse](divisions/basel-country-ch22/) |
| 23 | Solothurn | 10 | [Browse](divisions/solothurn-ch23/) |
| 24 | Obwalden | 1 | [Browse](divisions/obwalden-ch24/) |
| 25 | Uri | 1 | [Browse](divisions/uri-ch25/) |
| 26 | Bern | 11 | [Browse](divisions/bern-ch26/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-canton.json](data/all-canton.json) | JSON | All 26 canton records |
| [all-district.json](data/all-district.json) | JSON | All 148 district records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-canton.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-canton.json", "utf-8"));
console.log(`Total: ${data.length} cantons`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=canton, 2=district |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{canton-slug}/
```

Districts are listed inline in each canton's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-canton links
- [Per-canton data](docs/llms-full/) — Full data by canton

## Citation

```
Switzerland Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/switzerland-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
