# Vehicle import format

Use this format when pasting from Apple Notes or uploading a `.txt` / `.md` file in **Vehicles → Import**.

The importer matches an existing vehicle by **name** or **year + model** and updates it. Otherwise it adds a new vehicle. Duplicate maintenance rows (same date + description + mileage) are skipped.

## Template

```text
Name: My Civic
Make: Honda
Model: Civic
Year: 2020
Mileage: 45230
VIN: 1HGBH41JXMN109186
License Plate: ABC-1234

Maintenance:
2024-03-01 | Oil change | 45000
01/15/2024 - Tire rotation @ 44800 miles
Brake pads - 43000 miles - Nov 15 2023
```

## Vehicle fields

| Field | Required | Notes |
| --- | --- | --- |
| `Name` | Recommended | Display name. If omitted, built from Make + Model. |
| `Make` | Optional | e.g. `Honda`, `Harley Davidson` |
| `Model` | Recommended | e.g. `Civic`, `Sportster Custom 1200` |
| `Year` | Recommended | 4-digit year |
| `Mileage` | Optional | Commas allowed (`45,230`) |
| `VIN` | Optional | Also accepts `VIN Number`, `VIN #` |
| `License Plate` | Optional | Also accepts `Plate`, `Plate Number`, `Tag` |

You can also start with a single title line instead of separate fields:

```text
2020 Honda Civic
Mileage: 45230
```

## Maintenance section

Start the list with a line like `Maintenance:`, `Service:`, or `History:`.

Each following line is one record. Supported styles:

```text
YYYY-MM-DD | Description | mileage
MM/DD/YYYY - Description @ mileage miles
Description - mileage miles - Mon DD YYYY
```

Examples:

```text
2024-03-01 | Oil change | 45000
01/15/2024 - Tire rotation @ 44800 miles
Brake pads - 43000 miles - Nov 15 2023
```

| Part | Notes |
| --- | --- |
| Date | `YYYY-MM-DD`, `M/D/YYYY`, or `Nov 15 2023`. If missing, today’s date is used. |
| Description | Service name / notes |
| Mileage | Digits, optional commas, optional `miles` / `mi` / `@` |

## Full example (motorcycle)

```text
Name: Harley Davidson
Make: Harley Davidson
Model: Sportster Custom 1200
Year: 2004
Mileage: 28000
VIN: 1HD1CGP104K437881
License Plate: 30B79

Maintenance:
2023-06-10 | Oil change | 27500
05/01/2022 - New tires @ 26000 miles
```

## How to import

1. Copy the note (or save as `.txt`)
2. Open the app → **Vehicles** → upload icon
3. Paste or choose the file
4. Tap **Preview**, check VIN / plate, then import
