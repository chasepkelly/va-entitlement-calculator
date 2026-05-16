# VA Entitlement Calculator — Generic Edition

Single-file static HTML calculator for VA loan officers. No build step. No backend. Drop on any web host (Railway, Netlify, Vercel, Cloudflare Pages, S3, plain nginx).

## What it does

- Calculates VA guaranty per the VA Entitlement Worksheet (Chapter 3 / Chapter 7, Pamphlet 26-7)
- Handles full entitlement, restored entitlement (Blue Water Navy Act), and partial entitlement
- Supports multi-loan COE entry — Active / PIF–Restored / PIF–Not Restored — with auto-25% charged calculation per loan and override
- Joint VA loan support (two veteran borrowers, pooled entitlement, capped at 25% × CLL per loan)
- 2026 FHFA HERA-based county loan limits for all 3,226 counties × 4 unit counts (1/2/3/4-unit)
- Funding fee tiers (first/subsequent use, exempt) with optional financing
- Live calculation steps panel showing the underlying worksheet math

## To brand for your firm

⚠️ **Before publishing under your brand, read [`CHECKLIST.md`](./CHECKLIST.md) and use [`COMPLIANCE-TEMPLATE.md`](./COMPLIANCE-TEMPLATE.md) for the verbatim disclosure language.** The default page ships with `noindex` and a DEMO banner because it is not safe to publish to consumers without an LO-specific NMLS block, state licensing list, and the Equal Housing Opportunity logo.

Quick-start edits to `index.html`:

1. **`<title>`** — line ~6, swap with your brand
2. **`<meta name="robots">`** — line ~8, change `noindex, nofollow` → `index, follow` only after all CHECKLIST items are complete
3. **DEMO banner** — line ~1085, remove the red banner once page is compliance-reviewed
4. **Top nav brand** — line ~1100, add company name as `topnav-brand`
5. **Footer** — line ~1402, replace with branded footer from `COMPLIANCE-TEMPLATE.md` §1 (includes EHO logo, NMLS block, state licensing, Advertisement identifier)
6. **State-specific language** — `COMPLIANCE-TEMPLATE.md` §4 has starter language for CA / NY / TX / MA / IL / WA / FL / CO; expand per your license list
7. **Have a compliance attorney review** the final page before going live

## To deploy

Any static host. Examples:

```bash
# Railway: drop index.html in a git repo with a Dockerfile or nixpacks
# Netlify / Vercel / Cloudflare Pages: drag-and-drop or git connect
# S3 + CloudFront: aws s3 sync . s3://your-bucket/
# Plain nginx: copy index.html into /usr/share/nginx/html/
```

No environment variables, no API keys, no cookies.

## Updating county limits

Each November the FHFA publishes new conforming loan limits. To update:

1. Download `fullcountyloanlimitlist{YEAR}_hera-based_final_flat.csv` from fhfa.gov
2. Regenerate the `COUNTY_DATA` object in `index.html` (line ~1400) — schema:
   ```js
   { meta: { baseline, ceiling, baselines:{1,2,3,4}, ceilings:{1,2,3,4} },
     states: { CODE: "Name", ... },
     counties: { CODE: [[name, l1|null, l2|null, l3|null, l4|null], ...] }
   }
   ```
3. Update the year string in `meta.year` and the footer disclaimer
4. `null` for any unit limit means "use the baseline for that unit count" (saves bytes for ~3000 baseline counties)

## Compliance notes

The default disclaimer is generic and must be reviewed by your firm's compliance team before publishing. The tool is informational only — not a loan commitment, pre-approval, or offer to lend. Always verify the live FHFA county limit table before underwriting any specific scenario.

## Source

Math sourced from:
- VA Pamphlet 26-7, Chapter 3 (Maximum Guaranty Table)
- VA Pamphlet 26-7, Chapter 7 (Joint Loans, section 1.i)
- VA Circular 26-19-30, Exhibit A (Adjustment of Loan Limit Examples)
- FHFA 2026 Conforming Loan Limit Values (HERA-based dataset)
