# Luma Events Scraper: Lu Scraper API for Python & Node.js (2026)

Scrape Luma (lu.ma) events by city or category: dates, venues, guest counts, ticket prices, hosts and their socials. No login needed. Export JSON, CSV, Excel.

**[▶ Try the Luma Events Scraper free on Scrapely](https://scrape.ly/store/echofield/luma-events-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Lu data with the [Luma Events Scraper](https://scrape.ly/store/echofield/luma-events-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the lu scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Lu scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/echofield/luma-events-scraper) or from your code with the SDK.
- **Structured lu data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $0.06 per 1,000 event results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Lu changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Lu data can you extract?

Scrape Luma (lu.ma) events by city or category: dates, venues, guest counts, ticket prices, hosts and their socials. No login needed. Export JSON, CSV, Excel.

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('echofield/luma-events-scraper').call({"cities": ["San Francisco"], "categories": ["ai"], "maxResults": 20, "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('echofield/luma-events-scraper').call(run_input={ "cities": [ "San Francisco" ], "categories": [ "ai" ], "maxResults": 20, "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/echofield~luma-events-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "cities": [
    "San Francisco"
  ],
  "categories": [
    "ai"
  ],
  "maxResults": 20,
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [Luma Events Scraper page](https://scrape.ly/store/echofield/luma-events-scraper).

## Pricing

**$0.06 per 1,000 event results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/echofield/luma-events-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Lu with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Lu with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a lu scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/echofield~luma-events-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Lu legal?** This scraper collects publicly available data. Check Lu's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** luma events scraper, lu scraper, lu scraper api, lu scraper python, lu scraper node.js,
scrape lu, lu data extraction, lu crawler, lu api, export lu data to csv, luma-events-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/echofield/luma-events-scraper).
