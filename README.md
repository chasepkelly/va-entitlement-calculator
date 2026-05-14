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

Edit `index.html` directly:

1. **`<title>`** — line ~6, swap "VA Entitlement Calculator" for your brand
2. **Top nav** — line ~1080, add company name as `topnav-brand`, optionally add a "Pre-qualify" CTA linking to your contact form / scheduler
3. **Footer disclaimer** — line ~1380, swap in your firm's approved compliance text including your NMLS# and your sponsoring lender's NMLS#
4. **Hero copy** (`<header class="masthead">`) — adjust subtitle if you want to position the tool differently
5. **Optional** — uncomment / add a contact card after the results panel for direct pre-qualification

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
