# Pre-Publish Compliance Checklist

**This calculator displays loan figures (loan amount, down payment, funding fee, cash to close).** Under the CFPB MAP Rule (12 CFR 1014), Regulation Z §1026.24, the Fair Housing Act, VA advertising rules (38 USC §3709), and most state mortgage advertising statutes, you **cannot publish it to consumers** without the items below.

---

## Mandatory before publishing (do not skip)

- [ ] **Title tag** (`index.html` line ~6): replace with your branded title
- [ ] **`<meta name="robots">`** (line ~8): change from `noindex, nofollow` to `index, follow` only after items below are complete
- [ ] **DEMO INSTANCE banner** (line ~1085): remove the red banner once page is branded and compliance-reviewed
- [ ] **VA non-affiliation banner** under top nav (line ~1090): keep — required clear-and-conspicuous placement
- [ ] **Top-nav brand** (line ~1100): replace "VA Entitlement Calculator" with your company name / logo
- [ ] **Hero label "Estimated zero-down loan capacity"** (line ~1330): keep — do NOT revert to "Maximum zero-down loan" or "Guaranteed zero down" wording (MAP Rule §1014.3(d))
- [ ] **Status pill "Zero down may be possible"** (line ~1700): keep — do NOT revert to "Zero Down Available" or "Approved" wording
- [ ] **Result labels** ("Estimated total financed amount", "Estimated cash needed at closing"): keep — these are deliberately reframed away from credit-offer language per Reg Z trigger-term defense
- [ ] **Regulation Z disclaimer block** (after calculation steps, inside results panel): keep
- [ ] **Funding fee schedule** (line ~1391): verify percentages against the current VA schedule at va.gov before each annual republish; update the "effective 2026" string accordingly
- [ ] **County loan limits** (line ~1416): regenerate `COUNTY_DATA` from the current year's FHFA HERA-based dataset each November
- [ ] **Footer Equal Housing Opportunity logo** (line ~1414): keep; do NOT remove the SVG (HUD 24 CFR 109.30 — text-only treatment is insufficient for interactive tools)
- [ ] **Footer "Advertisement / Informational Tool" identifier**: keep
- [ ] **Footer NMLS identification block**: ADD your name + NMLS#, your company's legal name + NMLS#, branch street address, phone, and a link to nmlsconsumeraccess.org (see COMPLIANCE-TEMPLATE.md)
- [ ] **State licensing block**: ADD a list of all states you/your firm are licensed in, plus any state-specific required language. Examples:
  - California: DFPI/RMLA notice ("Licensed by the Department of Financial Protection and Innovation under the California Residential Mortgage Lending Act")
  - New York: DFS Registered Mortgage Broker notice
  - Texas: SML Recovery Fund Notice
  - Massachusetts, Illinois, Washington, Oregon, Colorado: state-specific bullets
  - Confirm with your compliance team for every state on your license list

## Strongly recommended

- [ ] If you add a **"Pre-qualify" or "Apply" CTA** to the top nav or after the results panel, do NOT use the words "pre-approval" without your compliance team's specific approved disclaimer. The terms "pre-approval" and "pre-qualification" are regulated under MAP Rule §1014.3(c) and TRID interpretive rules
- [ ] If you market the tool with the word **"free"**, append "with no obligation to apply" (FTC 16 CFR 251, Use of the Word "Free")
- [ ] If you add **rate or APR information** anywhere on the page, add the full Reg Z §1026.24(d)(2) companion disclosures (APR, repayment terms, balloon payment statement)
- [ ] Add a **`Last reviewed: YYYY-MM-DD`** stamp near the footer so you can audit when the page was last compliance-reviewed
- [ ] Configure **analytics that capture only first-party data** — third-party pixels on mortgage tools have triggered enforcement actions under state UDAP statutes and the FTC's "Health Breach Notification Rule" (which has been interpreted broadly)

## Before you go live

- [ ] **Have a licensed mortgage compliance attorney** (preferably one familiar with CFPB MAP Rule and multistate licensing) review the final branded page. Disclosure templates in this repo are starting points only — they are not legal advice and they will not anticipate every state or every change in federal rules
- [ ] **Re-run the audit annually** at minimum: funding fee schedule, county loan limits, state licensing list, NMLS status
- [ ] **Set up monitoring** for any CFPB enforcement actions citing MAP Rule §1014.3 or Reg Z §1026.24 against VA-focused lenders

---

**This checklist is informational only and not legal advice.**
