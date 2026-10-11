# mileage-calculator-data

Data files for the Chilometrico mileage reimbursement app.

The app reads `manifest.json` on `master`. It lists every data file with its URL, size, SHA-256 and
revision. Each URL is pinned to a tag or commit, so its bytes never change. A changed file gets a
new revision and a new URL, and the app verifies the SHA-256 before using it.

## Layout
| Folder | Content | Updated |
|---|---|---|
| `vehicle-rates/` | `vehicle-rates-<year>.json`: per-vehicle €/km rates for the year | once a year, plus corrections |
| `fuel-prices/` | `fuel-prices-weekly-<year>.json`: national weekly average fuel prices (MASE) | weekly, automatically |
| `energy-index/` | `energy-index-monthly-<year>.json`: monthly energy cost index | monthly |
| `interest-rate/` | `interest-rate-monthly-<year>.json`: monthly financing rate | monthly |

Each row of a weekly or monthly file applies from its date (`date` / `effective_from`) until the next row.
A lookup early in January may need the last row of the previous year's file.
