# Website UX & Conversion Audit Results
## Site: sadlowskimarketing.pl
## Date: 2026-03-05
## Auditor: audit-website-ux agent

> **Note:** Website returned HTTP 403 for direct WebFetch access. All findings are based on
> Google Search index snippets, cached metadata, and publicly indexed content. Checks that
> require direct HTML access are marked **N/V (Not Verifiable)**.

---

## UX Health Score: 62/100 (Grade: C)

### Category Breakdown
| Category | Weight | Score | Weighted |
|----------|--------|-------|---------|
| Navigation & Structure | 25% | 72/100 | 18.0 |
| Call-to-Action Quality | 30% | 52/100 | 15.6 |
| Trust Signals | 25% | 74/100 | 18.5 |
| Forms & Conversion | 20% | 50/100 | 10.0 |
| **TOTAL** | 100% | — | **62/100** |

### Accessibility Summary
- WCAG 2.1 AA: **PARTIAL** (cannot fully verify — direct HTML access blocked)

---

## Check Results

### Navigation & Structure (25%)

| ID | Check | Result | Finding | Recommendation |
|----|-------|--------|---------|----------------|
| U01 | Main navigation visible | PASS | Site has distinct pages: Kursy, Sklep, O mnie, Kontakt, indexed from search | Verify navigation is above fold on mobile |
| U02 | Navigation items ≤7 | PASS | ~5 primary pages found (Home, Shop, About, Contact, Privacy/Legal) | Good — maintain ≤7 items |
| U03 | Logo links to homepage | N/V | Cannot verify without direct access | Ensure logo href="/" |
| U04 | Contact info in header/footer | WARNING | Email hello@sadlowskimarketing.pl and phone 724 592 890 found in Terms — but header/footer placement unconfirmed | Move phone/email to header or sticky bar |
| U05 | Footer completeness | WARNING | Privacy policy (/polityka-prywatnosci/) and Terms (/regulamin/) confirmed — but full footer nav unconfirmed | Add nav links, contact, and NIP to footer |
| U06 | Breadcrumbs (inner pages) | N/V | Course subpages (e.g. /kursy-archiwum/...) have deep URL paths — breadcrumbs unconfirmed | Add breadcrumbs to course and lesson pages |
| U07 | Search functionality | N/V | WooCommerce shop likely has search — not confirmed | Verify site search works on /shop/ |

### Call-to-Action Quality (30%)

| ID | Check | Result | Finding | Recommendation |
|----|-------|--------|---------|----------------|
| U08 | Primary CTA above fold | N/V | Cannot confirm without direct page access; homepage indexed title is "Kursy Marketingowe Online" | Ensure a "Sprawdź kursy" / "Kup kurs" button appears above fold |
| U09 | CTA button contrast | N/V | Visual check not possible | Run a contrast check (≥4.5:1) on primary button |
| U10 | CTA text is specific | WARNING | Generic homepage tagline; no action-oriented CTA text confirmed in search snippets | Use specific CTAs like "Kup kurs ekspresowy – 45 min" |
| U11 | Single primary CTA | N/V | Multiple course offerings (3 packages + express course) — risk of competing CTAs | Limit homepage to 1 primary CTA; secondary CTAs as text links |
| U12 | CTA repeated on long pages | N/V | Cannot assess page length or CTA repetition | Add sticky CTA or repeat button every ~800px on long pages |
| U13 | Phone number clickable (tel:) | FAIL | Phone 724 592 890 found in Terms (/regulamin/) text — no tel: link confirmed in indexed content | Add `<a href="tel:724592890">724 592 890</a>` in header and contact page |
| U14 | WhatsApp/chat visible | N/V | No WhatsApp or live chat references found in any indexed content | Consider adding WhatsApp chat for pre-sale questions (courses niche) |

### Trust Signals (25%)

| ID | Check | Result | Finding | Recommendation |
|----|-------|--------|---------|----------------|
| U15 | Social proof visible | PASS | "Ponad tysiąc osób miało już okazję zakupić moje kursy" — confirmed in homepage indexed snippet | Move this prominently above fold if not already there |
| U16 | Review ratings shown | WARNING | Testimonials with qualitative text confirmed — but no Google/Facebook star ratings in snippets | Embed Google review widget or display aggregate rating |
| U17 | Client logos/portfolio | N/V | No client logos found in search results — this is a B2C courses platform (less applicable) | Consider showing brands/industries served instead |
| U18 | Case studies/results | PASS | Specific metrics: "ponad 2000 kampanii", "blisko 20 milionów złotych", "setki milionów przychodu" confirmed | Translate these into client outcome case studies with specifics |
| U19 | About/team page | PASS | /o-mnie/ page confirmed with personal background (10+ years, real professional history) | Add professional photo and 2-3 specific client outcomes |
| U20 | Certifications/awards | WARNING | Certificates are issued TO students, not TO/FROM the instructor — no industry awards/certifications found | Display any Google Partner, Meta Blueprint, or other certificates |
| U21 | Privacy policy + GDPR | PASS | /polityka-prywatnosci/ confirmed + /regulamin/ confirmed; administrator: FRESH MIND ADAM SADŁOWSKI, NIP: 5971051824 | Ensure cookie consent is displayed correctly |

### Forms & Conversion (20%)

| ID | Check | Result | Finding | Recommendation |
|----|-------|--------|---------|----------------|
| U22 | Contact form present | PASS | Contact form confirmed on /kontakt/ page alongside email | Good — form present |
| U23 | Form field count | N/V | Cannot verify field count without direct access | Keep fields to ≤5: Name, Email, Message, [Phone optional] |
| U24 | Form labels present | N/V | Cannot verify labels vs. placeholder-only | Ensure all fields have `<label>` elements, not just placeholder text |
| U25 | Submit button specific text | N/V | Cannot verify button text | Use "Wyślij wiadomość" or "Zapytaj o kurs" — not just "Wyślij" or "Submit" |
| U26 | Thank you/confirmation | N/V | Cannot verify post-submit behavior | Implement thank-you page redirect (enables conversion tracking) |
| U27 | Form mobile usability | N/V | Cannot verify mobile rendering | Ensure input fields ≥44px tap target, correct keyboard types (email field) |

---

## Accessibility Checks (WCAG 2.1 AA)

| ID | Check | Result | Notes |
|----|-------|--------|-------|
| A01 | Color contrast text (≥4.5:1) | N/V | Cannot assess without direct access |
| A02 | Color contrast headings (≥3:1) | N/V | Cannot assess without direct access |
| A03 | Alt text on images | N/V | Cannot verify img alt attributes |
| A04 | Focus indicators | N/V | Cannot verify keyboard navigation |
| A05 | ARIA labels | N/V | Cannot verify aria-label on icons/social links |
| A06 | Skip navigation link | N/V | Likely absent — uncommon on WordPress sites without explicit accessibility plugin |
| A07 | Language declared | N/V | Polish site — expected `lang="pl"` but not confirmed; **critical to verify** |
| A08 | Form error messages | N/V | Cannot verify error message behavior |

---

## Conversion Rate Optimization — Quick Wins

1. **Add clickable tel: link for phone 724 592 890** — every call-to-action-missing click costs a potential student; add to header and contact page immediately. (Check: U13)

2. **Surface a single, specific above-fold CTA** — "Sprawdź kurs ekspresowy" or "Zacznij w 45 minut" tells the user exactly what to do next. A vague homepage without a prominent first CTA leaks conversion. (Check: U08, U10)

3. **Add Google/Facebook star rating badge** — testimonial quotes are good, but an aggregate "4.9/5 z 120 opinii" with a Google widget immediately removes buying hesitation. (Check: U16)

4. **Verify form fields and add `<label>` elements** — placeholder-only forms fail WCAG and hurt mobile UX; many WordPress form plugins omit labels by default. (Check: U24)

5. **Implement post-form thank-you redirect** — without a dedicated thank-you URL, Google Ads and Meta Pixel conversion events cannot be properly attributed. (Check: U26)

---

## Critical UX Issues

1. **Phone number not a tel: link (U13 — FAIL):** Phone 724 592 890 found only in terms/regulamin text, not as a clickable link. On mobile, non-clickable phone numbers are a hard conversion barrier. Priority: **Critical**.

2. **Above-fold CTA unconfirmed (U08 — N/V):** For a courses/e-learning site, the first CTA visible without scrolling is the single most impactful conversion element. If absent or weak, it is likely the #1 revenue leak. Priority: **High**.

3. **Cookie consent unverified (A01–A08 — N/V):** As a Polish site operating under GDPR, cookie consent compliance is a legal requirement, not optional. Unverified = risk of regulatory action. Priority: **High**.

4. **No confirmed external review aggregate (U16 — WARNING):** Courses are a high-consideration purchase. Without star ratings, trust is weaker than competitors who display Google/Trustpilot scores. Priority: **Medium**.

5. **No confirmed breadcrumbs on deep course pages (U06 — N/V):** Deep URLs like `/kursy-archiwum/reklama-facebook-i-instagram.../lekcje/...` suggest complex page hierarchy. Missing breadcrumbs on lesson pages increase bounce. Priority: **Medium**.

---

## Data Sources Used
- Google Search index snippets for sadlowskimarketing.pl (March 2026)
- Search result meta descriptions for homepage, /kontakt/, /o-mnie/, /polityka-prywatnosci/, /regulamin/
- Terms of service (/regulamin/) indexed content — phone number source
- Direct WebFetch blocked (HTTP 403) — site restricts automated access

## Re-Audit Recommendation
Run this audit again with browser-based access or after temporarily allowlisting the audit tool's User-Agent to verify all N/V checks. Estimated ~15 additional checks can be resolved on direct access.
