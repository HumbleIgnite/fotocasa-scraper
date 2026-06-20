[Fotocasa Scraper](https://apify.com/igolaizola/fotocasa-scraper?fpr=data)

# Fotocasa Scraper

## 🤖 What does Fotocasa Scraper do?

Fotocasa Scraper enables you to effortlessly extract property listings from [fotocasa.es](https://fotocasa.es) for personal use, analysis, or lead generation.

Fotocasa Scraper can collect:

- 🏠 Properties for sale (compra)
- 🏡 Properties for rent (alquiler)
- 🤝 Shared accommodations (share)
- 🔄 Rent-to-buy options (rentBuyOption)
- 🏢 Transfers

## 💡 Why scrape fotocasa.es?

[Fotocasa](https://fotocasa.es) is one of the leading real estate portals in Spain, featuring thousands of listings across all regions. By scraping Fotocasa, you can:

- 📈 Analyze price trends and market dynamics in specific cities or neighborhoods
- 👀 Monitor new listings and competitive pricing for agencies and investors
- 🎯 Generate high-quality leads for real estate services
- 📊 Evaluate rental yields and investment opportunities

## 🚀 How to scrape fotocasa.es

Using Fotocasa Scraper is straightforward:

1. **Try for free** – Sign in to Apify and add Fotocasa Scraper to your actor list.
2. **Configure inputs** – Set the maximum items, location, operation, property type, and any filters.
3. **Run the actor** – Click **Run** to start scraping.
4. **Retrieve results** – Once finished, preview or download your data from the **Dataset** tab.

## 💳 How much will it cost to scrape fotocasa.es?

Apify grants $5 of free usage credits each month on the [Free plan](https://apify.com/pricing). You can test Fotocasa Scraper at no charge within those limits.

For regular or large-scale data extraction, consider an Apify subscription:

- **Personal Plan ($49/month)**: Ideal for frequent scraping and higher quotas.
- **Business Plans**: Custom pricing for enterprise-grade needs.

## 📝 Input Parameters

Configure the actor by supplying the following inputs in JSON format:

| Parameter | Type | Default | Options / Description |
| --- | --- | --- | --- |
| `maxItems` | integer | `10` | Maximum number of items to scrape (minimum `1`). |
| `location` | string | `Madrid` | Location to search for properties (e.g., city name or region). |
| `operation` | string | `buy` | Operation type: `buy`, `rent`, `share`, `rentBuyOption`, `transfer`. |
| `rentalTypes` | array | `[]` | Rental duration (only for `operation=rent`): `longTerm`, `temporary`. |
| `propertyType` | string | `home` | Property category: `home`, `newHome`, `premises`, `garages`, `office`, `boxRoom`, `land`, `building`. |
| `minPrice` | integer | `0` | Minimum property price (set `0` for no minimum). |
| `maxPrice` | integer | `0` | Maximum property price (set `0` for no maximum). |
| `minSize` | integer | `0` | Minimum property area in m² (set `0` for no minimum). |
| `maxSize` | integer | `0` | Maximum property area in m² (set `0` for no maximum). |
| `publicationDate` | string | `""` | Filter by publication time: `""` (Any), `last48h`, `lastWeek`, `lastMonth`. |
| `sortBy` | string | `rating` | Sort order: `rating`, `latest`, `cheapest`, `mostExpensive`, `biggest`, `smallest`, `cheapestPerM2`. |
| `proxyConfiguration` | object | Apify Proxy | Proxy settings: use Apify Proxy (`useApifyProxy`: `true`), groups (e.g., `RESIDENTIAL`). |

Example input:

```
{
  "maxItems": 100,
  "location": "Madrid",
  "operation": "rent",
  "rentalTypes": ["longTerm"],
  "propertyType": "home",
  "minPrice": 500,
  "maxPrice": 3000,
  "minSize": 50,
  "maxSize": 120,
  "publicationDate": "lastWeek",
  "sortBy": "latest",
  "proxyConfiguration": {
    "useApifyProxy": true,
    "apifyProxyGroups": ["RESIDENTIAL"]
  }
}
```

## 📊 Output

The actor returns an array of property objects in JSON format. Each object contains fields such as `propertyId`, `transaction.type`, `price`, `surface`, `rooms`, `baths`, `address` details, `location` coordinates, `agency` info, `multimedia` (images, video), and more.

Sample output (truncated):

```
[
  {
    "propertyId": "187123129",
    "transaction": {
      "type": "SALE",
      "price": 120000
    },
    "surface": 57,
    "rooms": 3,
    "baths": 1,
    "street": "Calle de Benimamet",
    "number": "51",
    "floor": "10",
    "publicationDate": "2025-07-21T19:15:08.237",
    "location": {
      "latitude": "40.3443439",
      "longitude": "-3.6871201"
    },
    "agency": {
      "name": "OCASIONES INMOBILIARIAS DEL HENARES SL",
      "phone": "912170482"
    },
    "multimedia": [
      {
        "url": "https://static.fotocasa.es/images/ads/06cd3b85-dd58...",
        "classification": "exterior"
      },
      {
        "url": "https://static.fotocasa.es/images/ads/4085ad4c-5c34...",
        "classification": "bedroom"
      }
      // ... more media
    ]
  }
  // ... more properties
]
```

## 🌍 Proxy Configuration

Fotocasa Scraper supports Apify Proxy to ensure reliable scraping without IP blocks:

- **useApifyProxy**: Set to `true` to enable
- **apifyProxyGroups**: Array of proxy groups (e.g., `RESIDENTIAL`)

## ⚖️ Is it legal to scrape fotocasa.es?

Web scraping may be subject to legal restrictions (e.g., GDPR for personal data in the EU). Make sure you have a legitimate purpose and comply with Fotocasa's terms of service. When in doubt, consult your legal advisor.