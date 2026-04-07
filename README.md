# DRM3 Data Licenses

Data source licenses and terms of use for [Signals](https://signals.data.drm3.network), the DRM3 open data ingestor.

Every data source ingested by Signals is documented here with its license type, restrictions, and terms URL. All fetched data is provenance-signed with Ed25519 per-row receipts.

## Sources by Category

### Government (7 sources)

| Source | License | Key | Attribution | Terms |
|--------|---------|-----|-------------|-------|
| [Congress.gov](third-party/congress.md) | US Gov Public Domain | Yes | No | [api.congress.gov](https://api.congress.gov/) |
| [Federal Register](third-party/federal-register.md) | US Gov Public Domain | No | No | [federalregister.gov](https://www.federalregister.gov/developers) |
| [FRED](third-party/fred.md) | Free API | Yes | Yes | [fred.stlouisfed.org](https://fred.stlouisfed.org/docs/api/) |
| [GovInfo](third-party/govinfo.md) | US Gov Public Domain | Yes | No | [api.govinfo.gov](https://api.govinfo.gov/) |
| [GSA .gov](third-party/gsa-gov.md) | US Gov Public Domain | No | No | [gsa.gov](https://www.gsa.gov/technology/government-it-initiatives/digital-strategy) |
| [SEC EDGAR](third-party/sec-edgar.md) | US Gov Public Domain | No | No | [sec.gov/edgar](https://www.sec.gov/edgar/searchedgar/accessing-edgar-data.htm) |
| [US Census](third-party/census.md) | US Gov Public Domain | No | No | [census.gov/data](https://www.census.gov/data/developers.html) |

### Financial (4 sources)

| Source | License | Key | Attribution | Terms |
|--------|---------|-----|-------------|-------|
| [Binance](third-party/binance.md) | API ToS | No | Yes | [binance.com/terms](https://www.binance.com/en/terms) |
| [Etherscan](third-party/etherscan.md) | API ToS | Yes | Yes | [etherscan.io/terms](https://etherscan.io/terms) |
| [FDIC](third-party/fdic.md) | US Gov Public Domain | No | No | [fdic.gov](https://www.fdic.gov/policies/information/) |
| [NASDAQ](third-party/nasdaq.md) | FTP Public | No | No | [nasdaqtrader.com](https://www.nasdaqtrader.com/Trader.aspx?id=FTPdirectory) |

### Environmental (3 sources)

| Source | License | Key | Attribution | Terms |
|--------|---------|-----|-------------|-------|
| [Open-Meteo](third-party/open-meteo.md) | CC BY 4.0 | No | Yes | [open-meteo.com/terms](https://open-meteo.com/en/terms) |
| [USGS Earthquakes](third-party/usgs-earthquakes.md) | US Gov Public Domain | No | No | [earthquake.usgs.gov](https://earthquake.usgs.gov/fdsnws/event/1/) |
| [USGS Water](third-party/usgs-water.md) | US Gov Public Domain | No | No | [waterservices.usgs.gov](https://waterservices.usgs.gov/) |

### Social (3 sources)

| Source | License | Key | Attribution | Terms |
|--------|---------|-----|-------------|-------|
| [GDELT](third-party/gdelt.md) | Free / Academic | No | Yes | [gdeltproject.org](https://www.gdeltproject.org/) |
| [GitHub Activity](third-party/github-activity.md) | API ToS | No | Yes | [docs.github.com](https://docs.github.com/en/rest/overview/resources-in-the-rest-api) |
| [Reddit](third-party/reddit.md) | API ToS | No | Yes | [reddit.com/wiki/api-terms](https://www.reddit.com/wiki/api-terms) |

### Prediction (1 source)

| Source | License | Key | Attribution | Terms |
|--------|---------|-----|-------------|-------|
| [Polymarket](third-party/polymarket.md) | Free API | No | No | [polymarket.com/terms](https://polymarket.com/terms) |

### Security (5 sources)

| Source | License | Key | Attribution | Terms |
|--------|---------|-----|-------------|-------|
| [Cisco Umbrella](third-party/umbrella.md) | Free Top 1M | No | No | [umbrella.cisco.com](https://umbrella.cisco.com/) |
| [Google Safe Browsing](third-party/safe-browsing.md) | API ToS | Yes | Yes | [developers.google.com](https://developers.google.com/safe-browsing/v4/terms) |
| [Majestic](third-party/majestic.md) | Free Million CSV | No | Yes | [majestic.com/terms](https://majestic.com/terms-of-use) |
| [Mozilla Observatory](third-party/mozilla-observatory.md) | MPL 2.0 | No | No | [observatory.mozilla.org](https://observatory.mozilla.org/) |
| [Tranco](third-party/tranco.md) | Free / Academic | No | Yes | [tranco-list.eu](https://tranco-list.eu/) |

## License Types

- **US Gov Public Domain** - Federal government data, no restrictions
- **CC BY 4.0** - Free to use with attribution (Open-Meteo)
- **API ToS** - Proprietary terms, typically allows display but not raw resale
- **Free / Academic** - Open for non-commercial use, attribution expected
- **MPL 2.0** - Mozilla Public License, open source
- **FTP Public** - Publicly available FTP data (NASDAQ)
- **Free Top 1M / Free Million CSV** - Freely distributed ranking datasets

## How We Use This Data

All data is:
1. **Fetched** via public APIs on a scheduled cadence
2. **Signed** with Ed25519 per-row provenance receipts (row-level attestation)
3. **Rolled up** into Merkle trees per batch
4. **Stored** in D1 (7-day hot cache) and BigQuery (permanent archive)
5. **Served** via authenticated API with provenance verification

We do NOT resell raw data. All data is transformed via provenance signing and aggregation.

## Links

- [Signals Dashboard](https://signals.data.drm3.network)
- [API Playground](https://signals.data.drm3.network/api)
- [Signing Keys](https://signals.data.drm3.network/.well-known/signals-3p-keys.json)
- [Health](https://signals.data.drm3.network/health)
