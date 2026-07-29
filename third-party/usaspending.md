# USAspending.gov - Data Agreement

## Provider
U.S. Department of the Treasury, Bureau of the Fiscal Service (Federal Spending Transparency)

## URL
https://api.usaspending.gov/api/v2/

## Terms of Service URL
https://github.com/fedspendingtransparency/usaspending-api/blob/master/LICENSE

## License
CC0 1.0 Universal (public domain dedication).

Two independent grounds, both verified 2026-07-28:

1. The project publishes its work under **CC0-1.0**, declared in the `LICENSE` of the
   official repository `fedspendingtransparency/usaspending-api` (confirmed via the GitHub
   licenses API: `spdx_id: CC0-1.0`).
2. The underlying records are works of the U.S. federal government, which are not subject
   to domestic copyright (17 U.S.C. sec. 105).

**Honest grain:** the CC0 file sits on the API's source repository. It is the project's own
published dedication and the citation everyone uses, but it is a repository-level LICENSE
file, not a per-response license header on the data payload. Ground 2 is what makes the
posture safe regardless.

### The one carve-out: Dun & Bradstreet fields
Some award records carry recipient-identification fields sourced from Dun & Bradstreet
("D&B Open Data"), which USAspending redistributes under D&B's own attribution notice
rather than under CC0. **Treat D&B-derived fields as attribution-bearing and everything
else as unrestricted.** Any ingest that pulls recipient-level or award-level records must
detect these fields and preserve the attribution through the refinery into the served row.

The agency-level endpoint we ingest today (`/v2/references/toptier_agencies/`) carries
**no D&B fields**, so this carve-out is not yet live for us. It becomes live the moment
recipient or award ingest lands.

## Data We Collect
Agency-level federal spending state via `GET /api/v2/references/toptier_agencies/`: for
each of ~111 toptier federal agencies, the active fiscal year and quarter, budget
authority, obligated amount, outlay amount, and share of government-wide budget authority.

Award-level and recipient-level ingest is **not** collected today. See the carve-out above
before adding it.

## How We Use It
Federal spending signal in DRM3 products. Ingested through the Open Signals collector,
refined in the lakehouse into an agency fiscal-state series with period-over-period deltas,
and served out through the metered, signed Data Extract API.

## Commercial Use
Yes. CC0 waives all copyright and related rights worldwide; US government works carry no
domestic copyright. No royalty, no field-of-use restriction.

## Redistribution
Yes, including as a paid derived product. CC0 permits redistribution and commercial reuse
without permission. Our served rows are our own refinement over public-domain inputs.

## Attribution Required
No, for the CC0/public-domain body of the data. CC0 explicitly waives attribution.
Best practice, which we follow: cite "USAspending.gov" as the source in provenance.

**Yes, for D&B-derived fields** if and when award/recipient ingest lands. See the carve-out.

## Rate Limits
- No API key required, no authentication
- No published per-key rate limit; reasonable-use expected
- Bulk endpoints (award search, bulk download) are heavy: ~10 GB per government fiscal
  year. Incremental sync only, never a one-shot full pull.

## Key Restrictions
- Do not misrepresent derived figures as official Treasury or agency reporting
- Amounts are restated as agencies submit; a fiscal quarter is not final when first published
- Reporting lag: the "active" fiscal quarter trails the calendar by roughly one quarter
- D&B fields (award/recipient level) carry their own attribution notice - see carve-out

## Last Reviewed
2026-07-28
