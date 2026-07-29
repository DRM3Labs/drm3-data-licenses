# Venice AI Model Catalog - Data Agreement

## Provider
Venice AI (venice.ai)

## URL
https://api.venice.ai/api/v1/models

## Terms of Service URL
https://venice.ai/legal/tos

## License
API Terms of Service. The catalog payload itself is factual metadata about Venice's own
public model offering: model identifiers, names, types, context limits, capability flags,
and published per-token prices. Facts are not copyrightable; the compilation is Venice's,
and we collect it as published, unmodified, with lineage.

## Data We Collect
The public model catalog via `GET /api/v1/models?type=all` (~286 models across 9 types as of
2026-07-29): id, type, name, description, context length, completion limits, capability
flags (reasoning, vision, function calling, web search), quantization, privacy class,
offline flag, traits, and published USD pricing per input/output token where the model is
priced that way.

**No API key is used or required.** Verified 2026-07-29: the endpoint serves anonymous
requests. We fetch it like any public catalog page.

## How We Use It
AI-market signal in DRM3 products. Snapshotted daily through the Open Signals collector;
the states engine turns catalog additions, removals, and price changes into state changes.
Feeds the Decentralized AI news desk (which previously fetched this endpoint directly) and,
downstream, the fact layer.

## Commercial Use
Yes, as factual market metadata about a public offering. We do not resell Venice's service,
proxy their API, or misrepresent their models as ours.

## Redistribution
Derived form only: we serve our own signed observations of the catalog state and its
changes over time, each row carrying its provenance receipt. We do not republish their API
as a mirror.

## Attribution Required
Not stated for catalog metadata. Best practice, which we follow: rows carry
`source=venice_catalog` and name Venice as the origin wherever the data surfaces.

## Rate Limits
- No key, no documented limit for this endpoint; we call it once per day
- Single request returns the full catalog (~430 KB)

## Key Restrictions
- Do not present Venice's models or pricing as DRM3's offering
- Prices are Venice's published rates at fetch time; they change without notice, which is
  exactly the change signal we record
- DRM3 is also a Venice API CUSTOMER (inference, image generation) under the same ToS;
  this catalog scan is separate from and does not depend on that paid usage

## Last Reviewed
2026-07-29
