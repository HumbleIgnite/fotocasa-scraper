[Fotocasa Scraper](https://apify.com/gio21/fotocasa-scraper?fpr=data)

# Fotocasa Scraper 🏠

Scrape property listings from **Fotocasa** (fotocasa.es) — Spain's leading real-estate portal.

## What it does

Search listings by operation (buy/rent) + location, get structured property data:

- **Title**, **price**, **price per m²**
- **Area** (m²), **rooms**, **bathrooms**, **floor**
- **Property type** (flat, house, studio, duplex, penthouse…)
- **Location**: city, neighborhood
- **Features** (terrace, parking, lift, AC, pool, furnished, garden…)
- **Energy certificate**
- **Agency / owner** and contact
- **Images**, **description**, **reference code**
- **URL** and **listingId**

## Input

| Field | Type | Default | Description |
| --- | --- | --- | --- |
| `operation` | string | `comprar` | `comprar` (sale), `alquiler` (rent), `alquiler-habitacion` (shared), `alquiler-vacacional` (vacation) |
| `propertyType` | string | `viviendas` | `viviendas`, `oficinas`, `locales`, `naves`, `garajes`, `trasteros`, `terrenos` |
| `location` | string | `madrid-capital` | Fotocasa location slug |
| `startUrl` | string | — | Optional direct URL (overrides all filters) |
| `maxItems` | integer | `50` | Max listings (cap 500) |
| `maxPages` | integer | `5` | Max search pages |

## Output

```
{
  "listingId": "178987654",
  "title": "Piso en venta en Calle Gran Vía",
  "propertyType": "Piso",
  "operation": "comprar",
  "price": 450000,
  "currency": "EUR",
  "pricePerSqm": 5625,
  "area": 80,
  "rooms": 2,
  "bathrooms": 1,
  "location": "Madrid Capital",
  "neighborhood": "Centro",
  "features": ["Ascensor", "Aire acondicionado", "Terraza"],
  "agency": "Inmobiliaria XYZ",
  "images": ["https://static.fotocasa.es/..."],
  "url": "https://www.fotocasa.es/es/comprar/vivienda/madrid-capital/..."
}
```

## Pricing

Pay-per-event: **$0.005 per listing** ($5 per 1,000).

Free users: up to 15 listings per run.

## Use cases

- PropTech / real-estate SaaS — property feeds for CRMs and price-comparison tools
- Investment research — yield analysis by district
- Relocation services — build client shortlists for Spain moves
- Competitive intel — agency market share by neighborhood