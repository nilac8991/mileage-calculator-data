# mileage-calculator-data

Data files for the Chilometrico mileage reimbursement app.

The app reads `manifest.json` on `master`. It lists every data file with its URL, size, SHA-256 and
revision. Each file is pinned to a tag or commit, so its bytes never change. A correction gets a new
revision and a new URL.

## Layout
| Folder | Content | Updated |
|---|---|---|
| `vehicle-rates/` | `vehicle-rates-<year>.json`: per-vehicle €/km rates for the year | once a year, plus corrections |
