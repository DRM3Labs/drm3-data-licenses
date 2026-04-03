# Google Safe Browsing — Data Agreement

## Provider
Google LLC

## URL
https://safebrowsing.google.com/

## Terms of Service URL
https://developers.google.com/safe-browsing/v4/terms

## License
API ToS (Google APIs Terms of Service + Safe Browsing-specific additional terms)

## Data We Collect
Threat verdicts for domains and URLs via the Safe Browsing Lookup API v4. Responses indicate whether a URL is flagged as malware, social engineering, unwanted software, or potentially harmful application.

## How We Use It
Domain safety signal in DRM3's internet telemetry index. Safe Browsing verdicts are included in domain security profiles to warn users about potentially dangerous sites.

## Commercial Use
Yes, with strict conditions. The Safe Browsing API is free and may be used in commercial products, but the primary purpose MUST be to protect users from threats. Data cannot be used for purposes other than displaying warnings about unsafe sites.

## Redistribution
Restricted. Safe Browsing data must be used only to display warnings to end users. We may include a "flagged by Google Safe Browsing" indicator in domain profiles, but we cannot serve raw threat list data via our API or use it as a general-purpose reputation score.

## Attribution Required
Yes. When displaying warnings based on Safe Browsing data, must include Google Safe Browsing attribution. The specific required language and branding is documented in the API terms.

## Rate Limits
- Lookup API: 10,000 URLs per day (free quota)
- Update API: no per-request limit but designed for periodic syncing
- Quota increases available via Google Cloud Console

## Key Restrictions
- MUST display warnings to users for flagged sites -- cannot silently filter or score
- CANNOT use threat data to determine general "trustworthiness" or "reputation" -- only for safety warnings
- CANNOT build a competing safe browsing or URL reputation service
- CANNOT cache results longer than the API-specified duration
- MUST update local threat lists at the frequency Google specifies
- CANNOT use data for advertising targeting or user profiling
- MUST comply with Google APIs ToS and Safe Browsing Additional Terms

## Last Reviewed
2026-04-02
