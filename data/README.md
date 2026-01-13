# Data Store

This directory contains structured data extracted from user-provided materials.

## Structure

```
data/
└── extracted/
    └── [purchase-name]/
        └── products.csv
```

## CSV Format

Extracted product CSVs follow this schema:

| Column | Description |
|--------|-------------|
| `product_name` | Full product name/model |
| `brand` | Manufacturer/brand name |
| `price` | Price as displayed (with currency symbol) |
| `price_numeric` | Numeric price value for sorting |
| `currency` | Currency code (ILS, USD, EUR, etc.) |
| `sku` | SKU/model number if visible |
| `source` | Source filename (screenshot/PDF name) |
| `page` | Page number if from multi-page PDF |
| `notes` | Any additional details extracted |

## Usage

- Products are extracted via `/extract` command
- CSVs can be referenced by `/research` and `/recommend` commands
- Multiple sources combine into single CSV per purchase
