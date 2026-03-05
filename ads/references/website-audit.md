# Website Audit Reference

Scoring thresholds, category weights, and checklists for full website audits.
Used by: audit-website-seo, audit-website-performance, audit-website-ux, audit-website-technical

---

## Website Health Score Algorithm

### Category Weights (Aggregate)

| Category | Weight | Agent |
|----------|--------|-------|
| SEO | 30% | audit-website-seo |
| Performance | 30% | audit-website-performance |
| UX / Conversion | 25% | audit-website-ux |
| Technical / Security | 15% | audit-website-technical |

### Severity Multipliers

| Severity | Multiplier | Description |
|----------|-----------|-------------|
| Critical | 5.0x | Fundamental issue blocking visibility/conversion |
| High | 3.0x | Significant negative impact |
| Medium | 1.5x | Optimization opportunity |
| Low | 0.5x | Best practice, minor impact |

### Grading Scale

| Grade | Score | Status |
|-------|-------|--------|
| A | 90-100 | Excellent — minor optimizations only |
| B | 75-89 | Good — some improvement areas |
| C | 60-74 | Average — notable issues need attention |
| D | 40-59 | Poor — significant problems present |
| F | <40 | Critical — urgent intervention required |

---

## SEO Thresholds

### Title Tags
- **Pass**: 50-60 characters, primary keyword near start, unique per page
- **Warning**: <50 or 61-70 characters, keyword present but not front-loaded
- **Fail**: >70 characters (truncated in SERP), missing, duplicate across pages

### Meta Descriptions
- **Pass**: 120-158 characters, includes primary keyword, has CTA, unique
- **Warning**: <120 or >158 characters, generic copy
- **Fail**: Missing or duplicate

### Core Web Vitals (as SEO ranking signals)
- LCP: Pass <2.5s, Warning 2.5-4.0s, Fail >4.0s
- CLS: Pass <0.1, Warning 0.1-0.25, Fail >0.25
- INP: Pass <200ms, Warning 200-500ms, Fail >500ms

### Image Alt Text Coverage
- Pass: 100% of informative images have descriptive alt text
- Warning: 80-99% coverage
- Fail: <80% coverage

---

## Performance Thresholds

### Core Web Vitals
| Metric | Pass | Warning | Fail | Source |
|--------|------|---------|------|--------|
| LCP | <2.5s | 2.5-4.0s | >4.0s | Google CWV |
| INP | <200ms | 200-500ms | >500ms | Google CWV |
| CLS | <0.1 | 0.1-0.25 | >0.25 | Google CWV |
| FCP | <1.8s | 1.8-3.0s | >3.0s | Google |
| TTFB | <600ms | 600-1800ms | >1800ms | Google |

### Page Weight
- Pass: <2MB total page weight
- Warning: 2-5MB
- Fail: >5MB

### HTTP Requests
- Pass: <50 requests
- Warning: 50-100 requests
- Fail: >100 requests

### Third-Party Scripts Impact
- Pass: <3 third-party domains, <500ms added load
- Warning: 3-6 domains or 500-1000ms
- Fail: >6 domains or >1000ms added load

---

## UX / Conversion Thresholds

### CTA Visibility
- Pass: Primary CTA visible above fold without scrolling (mobile and desktop)
- Warning: CTA visible after 1 scroll
- Fail: CTA only in footer or missing

### Trust Signal Scoring
- Pass: 3+ trust elements above fold (reviews, ratings, client logos, certifications)
- Warning: 1-2 trust elements above fold
- Fail: Trust signals missing or below fold only

### Form Length vs. CVR Impact
| Fields | CVR Impact | Use Case |
|--------|-----------|----------|
| 1-3 | Highest | Top-of-funnel, free offer |
| 4-5 | Moderate | Mid-funnel, lead gen |
| 6-8 | Lower | Bottom-funnel, qualified leads |
| 9+ | Lowest | Only for very high-value offers |

### Color Contrast (WCAG 2.1 AA)
- Body text: ≥4.5:1 contrast ratio
- Large text (≥18px or ≥14px bold): ≥3:1 contrast ratio
- UI components and graphical objects: ≥3:1

---

## Technical Thresholds

### HTTPS & Security
- Pass: HTTPS with valid cert, HTTP→HTTPS 301 redirect, no mixed content
- Warning: HTTPS but mixed passive content (images over HTTP)
- Fail: No HTTPS, expired cert, mixed active content (scripts over HTTP)

### Cookie Consent (GDPR/PECR)
- Pass: Consent banner on first visit, pixels fire only post-consent, granular controls
- Warning: Banner present but all pixels fire on load
- Fail: No banner on EU-accessible site

### Analytics Coverage
- Pass: GA4 + GTM + conversion events configured
- Warning: GA4 present but only pageviews tracked
- Fail: No analytics, or only Universal Analytics (UA deprecated 2023)

### Ad Pixel Health
- Pass: All active ad platform pixels detected, firing on conversion pages
- Warning: Some pixels missing, or firing without consent gating
- Fail: No conversion tracking pixels, or all pixels missing

---

## Quick Wins Definition

```
IF severity == "Critical" OR severity == "High"
AND estimated_fix_time < 30 minutes
THEN flag as Quick Win
SORT BY (severity_multiplier × estimated_impact) DESC
```

### Examples by Category

**SEO Quick Wins:**
- Add/fix missing meta descriptions (5 min per page)
- Add alt text to images (10 min)
- Fix duplicate H1 tags (5 min)

**Performance Quick Wins:**
- Enable GZIP compression (server config, 5 min)
- Add `loading="lazy"` to below-fold images (10 min)
- Add `defer` to non-critical scripts (10 min)

**UX Quick Wins:**
- Make phone number a `tel:` link (5 min)
- Change submit button text from "Submit" to specific action (2 min)
- Add Google Review rating to homepage (15 min)

**Technical Quick Wins:**
- Install GA4 via GTM (15 min)
- Add Meta Pixel via GTM (15 min)
- Add Consent Mode v2 to GTM (30 min)
