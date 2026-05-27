# Chad Administrative Divisions / Tchad



## Overview

| Item | Details |
|------|---------|
| Province | 23 |
| Department | 70 |
| Sub-prefecture | 348 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-27 |
| Website | [openadmindata.org/td](https://openadmindata.org/td/) |
| API | [openadmindata.org/api/td](https://openadmindata.org/api/td/) |

## Browse by Province

| # | Province | Departments | Sub-prefectures | Link |
|---|----|----|----|------|
| 1 | BARH EL GAZEL | 3 | 3 | [Browse](divisions/barh-el-gazel-tcd19/) |
| 2 | BATHA | 3 | 15 | [Browse](divisions/batha-tcd01/) |
| 3 | BORKOU | 2 | 1 | [Browse](divisions/borkou-tcd02/) |
| 4 | CHARI BAGUIRMI | 3 | 11 | [Browse](divisions/chari-baguirmi-tcd03/) |
| 5 | ENNEDI EST | 2 | 1 | [Browse](divisions/ennedi-est-tcd20/) |
| 6 | ENNEDI OUEST | 2 | 1 | [Browse](divisions/ennedi-ouest-tcd23/) |
| 7 | GUÉRA | 4 | 21 | [Browse](divisions/gura-tcd04/) |
| 8 | HADJER LAMIS | 3 | 10 | [Browse](divisions/hadjer-lamis-tcd05/) |
| 9 | KANEM | 3 | 11 | [Browse](divisions/kanem-tcd06/) |
| 10 | LAC | 4 | 2 | [Browse](divisions/lac-tcd07/) |
| 11 | LOGONE OCCIDENTAL | 4 | 28 | [Browse](divisions/logone-occidental-tcd08/) |
| 12 | LOGONE ORIENTAL | 6 | 36 | [Browse](divisions/logone-oriental-tcd09/) |
| 13 | MANDOUL | 3 | 32 | [Browse](divisions/mandoul-tcd10/) |
| 14 | MAYO KEBBI EST | 4 | 28 | [Browse](divisions/mayo-kebbi-est-tcd11/) |
| 15 | MAYO KEBBI OUEST | 3 | 18 | [Browse](divisions/mayo-kebbi-ouest-tcd12/) |
| 16 | MOYEN CHARI | 3 | 24 | [Browse](divisions/moyen-chari-tcd13/) |
| 17 | N&#39;DJAMENA | 1 | 4 | [Browse](divisions/ndjamena-tcd18/) |
| 18 | OUADDAÏ | 3 | 22 | [Browse](divisions/ouadda-tcd14/) |
| 19 | SALAMAT | 3 | 16 | [Browse](divisions/salamat-tcd15/) |
| 20 | SILA | 2 | 9 | [Browse](divisions/sila-tcd21/) |
| 21 | TANDJILÉ | 3 | 27 | [Browse](divisions/tandjil-tcd16/) |
| 22 | TIBESTI | 2 | 1 | [Browse](divisions/tibesti-tcd22/) |
| 23 | WADI FIRA | 4 | 27 | [Browse](divisions/wadi-fira-tcd17/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 23 province records |
| [all-department.json](data/all-department.json) | JSON | All 70 department records |
| [all-sous_prefecture.json](data/all-sous_prefecture.json) | JSON | All 348 sub-prefecture records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-province.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['department']} departments")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-province.json", "utf-8"));
console.log(`Total: ${data.length} provinces`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=province, 2=department, 3=sub-prefecture |
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
divisions/{province-slug}/
divisions/{province-slug}/{department-slug}/
```

Sub-prefectures are listed inline in each department's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
Chad Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/chad-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
