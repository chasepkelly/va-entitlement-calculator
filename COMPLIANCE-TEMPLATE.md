# Compliance Template

Verbatim disclosure language for hosting LOs. **Have your compliance attorney review before publishing.** Bracketed placeholders must be filled in.

---

## 1. Branded footer block (replace footer in `index.html` ~ line 1402)

```html
<footer style="background:var(--navy-deepest);color:rgba(250,246,238,0.7);padding:40px 32px 32px;font-family:'Inter',system-ui,sans-serif;">
  <div style="max-width:1180px;margin:0 auto;">

    <!-- Equal Housing Opportunity mark -->
    <div style="display:flex;flex-direction:column;align-items:center;gap:8px;margin-bottom:24px;">
      <svg width="36" height="36" viewBox="0 0 64 64" aria-label="Equal Housing Opportunity" role="img" style="opacity:0.85;">
        <path d="M32 6 L58 28 L52 28 L52 58 L12 58 L12 28 L6 28 Z" fill="none" stroke="rgba(250,246,238,0.85)" stroke-width="3" stroke-linejoin="round"/>
        <rect x="22" y="38" width="6" height="3" fill="rgba(250,246,238,0.85)"/>
        <rect x="36" y="38" width="6" height="3" fill="rgba(250,246,238,0.85)"/>
        <rect x="22" y="44" width="6" height="3" fill="rgba(250,246,238,0.85)"/>
        <rect x="36" y="44" width="6" height="3" fill="rgba(250,246,238,0.85)"/>
      </svg>
      <span style="font-size:10px;letter-spacing:0.12em;text-transform:uppercase;color:rgba(250,246,238,0.75);font-weight:600;">Equal Housing Opportunity</span>
    </div>

    <div style="text-align:center;font-size:12px;line-height:1.7;color:rgba(250,246,238,0.75);max-width:880px;margin:0 auto;">
      <strong style="color:#fff;">[YOUR NAME]</strong> · NMLS# [YOUR NMLS#]<br>
      <strong style="color:#fff;">[YOUR COMPANY LEGAL NAME]</strong> · NMLS# [COMPANY NMLS#]<br>
      [BRANCH STREET ADDRESS, CITY, STATE, ZIP] · [PHONE]<br>
      <a href="https://www.nmlsconsumeraccess.org" target="_blank" rel="noopener" style="color:rgba(250,246,238,0.85);">nmlsconsumeraccess.org</a><br><br>

      <strong>Licensed in:</strong> [STATE LIST — e.g. AL, AZ, CA, CO, FL, GA, NV, NM, OK, TN, TX, UT].<br>
      [STATE-SPECIFIC DISCLOSURES — see Section 4 below for examples].<br><br>

      <span style="font-size:11px;color:rgba(250,246,238,0.65);">
        <strong style="color:rgba(250,246,238,0.85);text-transform:uppercase;letter-spacing:0.08em;font-size:10px;">Advertisement.</strong>
        This calculator is an informational tool only. It is not a loan commitment, pre-approval, rate lock, or offer of credit. Figures shown are estimates of VA entitlement math under VA Pamphlet 26-7 (Chapters 3 and 7) and Circular 26-19-30 and do not include the Annual Percentage Rate (APR), monthly payment, taxes, insurance, escrow, or total finance charges. All loans are subject to credit approval, income verification, residual-income analysis, appraisal, lender overlays, and applicable VA underwriting standards. Rates, fees, funding-fee schedules, and county loan limits are subject to change without notice.<br><br>

        This calculator is not provided by, affiliated with, or endorsed by the U.S. Department of Veterans Affairs (VA) or any other government agency. VA loan benefits are determined by the VA based on the borrower's Certificate of Eligibility.<br><br>

        © [YEAR] [YOUR COMPANY LEGAL NAME]. All rights reserved.
      </span>
    </div>
  </div>
</footer>
```

---

## 2. Top-nav CTA — if you add "Pre-qualify" or "Apply"

Default position: avoid `pre-approval` / `pre-qualification` language entirely on the calculator page. If your compliance team approves it, use this disclaimer in close proximity to the CTA:

```
"Pre-qualification is not a commitment to lend, a rate lock, or a final loan approval. Final approval is subject to underwriting, credit, income, asset, and appraisal review. Conditions apply."
```

---

## 3. "Free" wording qualifier (FTC 16 CFR 251)

If your landing copy says "free" for the **tool**, that's generally fine. If "free" is attached to a downstream paid service (e.g. "free pre-qualification", "free rate quote"), append:

```
"…with no obligation to apply, and you may decline any subsequent loan offer at any time."
```

---

## 4. State-specific disclosure language (examples — NOT exhaustive)

### California (DFPI / RMLA)
```
Licensed by the Department of Financial Protection and Innovation under the California Residential Mortgage Lending Act, License No. [#].
```

### New York (DFS)
```
Registered Mortgage Broker — NYS Department of Financial Services. Loans arranged through third-party providers.
```

### Texas (SML Recovery Fund Notice)
```
Consumers wishing to file a complaint against a company or a residential mortgage loan originator should complete and send a complaint form to the Texas Department of Savings and Mortgage Lending, 2601 N. Lamar Suite 201, Austin, TX 78705. Complaint forms and instructions may be obtained from the department's website at www.sml.texas.gov. A toll-free consumer hotline is available at 1-877-276-5550.

The department maintains a recovery fund to make payments of certain actual out-of-pocket damages sustained by borrowers caused by acts of licensed residential mortgage loan originators. A written application for reimbursement from the recovery fund must be filed with and investigated by the department prior to the payment of a claim. For more information about the recovery fund, please consult the department's website at www.sml.texas.gov.
```

### Massachusetts
```
MA Mortgage Lender License #[#] / MA Mortgage Broker License #[#].
```

### Illinois (IDFPR)
```
Illinois Residential Mortgage Licensee No. [#] — Illinois Department of Financial and Professional Regulation, Division of Banking.
```

### Washington
```
WA Consumer Loan Company License CL-[#].
```

### Florida
```
Florida Mortgage Lender License #MLD[#].
```

### Colorado
```
Regulated by the Division of Real Estate.
```

**Do not copy-paste this list as-is.** Every state has its own current required wording — confirm with your state regulator or compliance team. Several states (NY, NJ, MA, IL, CA) periodically update required boilerplate. Your compliance team should maintain a master template and update annually.

---

## 5. Privacy / cookie disclosure (if you add analytics)

If you add Google Analytics, Meta Pixel, or any third-party tracking pixel, you need a privacy policy link in the footer and (in some states) an opt-in cookie banner. State-specific (CCPA / CPRA in California, CDPA in Virginia, CPA in Colorado, CTDPA in Connecticut, etc.):

```html
<a href="/privacy" style="color:rgba(250,246,238,0.5);">Privacy Policy</a> · <a href="/do-not-sell" style="color:rgba(250,246,238,0.5);">Do Not Sell or Share My Personal Information</a>
```

The CFPB has signaled enforcement interest in mortgage websites that share form-input data with ad networks. Conservative posture: **do not pixel-track input fields on this calculator.**

---

## 6. Annual review reminders

Add to your calendar:
- **Every November:** new FHFA HERA-based county loan limits published; regenerate `COUNTY_DATA`
- **Annually (or when VA changes):** verify funding fee schedule at va.gov
- **Annually:** confirm state licensing list, NMLS status, and that your firm's licensed-states list still matches your footer
- **Quarterly:** check CFPB enforcement actions citing MAP Rule §1014.3 or Reg Z §1026.24 for any new interpretive risk

---

**This template is informational only and is not legal advice.** Disclosures vary by state, by company structure (broker vs lender vs bank), and by what other content sits next to this calculator. Have your compliance team review every word before publishing.
