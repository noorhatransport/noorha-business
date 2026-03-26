# Month 1 Execution Plan: Foundation & Eastern Province Lock-Down

**Period**: March 27 – April 30, 2026
**Target**: ~25 new pages + 17 optimized = 42 total pages touched
**Dev Workflow**: Multiple PRs by type (separate review per category)
**Branch naming**: `seo/month1-[category]` (e.g., `seo/month1-city-hubs`)

---

## Pre-Work: Baseline Data Collection

Before building, we need baseline metrics to measure Month 1 impact.

### Data to Pull
| Source | What We Need | How |
|--------|-------------|-----|
| GA4 | Organic sessions (last 90 days), top landing pages, bounce rate by page | Reports → Acquisition → Traffic acquisition → Filter: Organic |
| Search Console | Total impressions/clicks, top queries, top pages, avg position, indexed pages | Performance report (last 3 months) + Pages report |
| Search Console | Index coverage issues | Indexing → Pages report |
| GBP | Current reviews count, rating, impressions, actions | GBP dashboard → Insights |

### Baseline Snapshot (pulled Mar 27, 2026)
| Metric | Baseline Value | Date |
|--------|---------------|------|
| Organic clicks (3 months) | 965 | Dec 25 - Mar 25 |
| Organic impressions (3 months) | 43,366 | Dec 25 - Mar 25 |
| Average CTR | 2.2% | 3-month avg |
| Average position | 9.2 | 3-month avg |
| Total indexed pages | ~37 | Mar 27 |
| CWV Mobile | 0 poor, **16 need improvement**, 0 good | Mar 25 |
| CWV Desktop | Not enough data | Mar 25 |
| GBP reviews | TBD (pull manually) | |

### Top Queries (3 months)
| Query | Clicks | Impressions | CTR | Position |
|-------|--------|-------------|-----|----------|
| noorha transport (branded) | 62 | 283 | 21.9% | 3.0 |
| dammam to bahrain taxi | 21 | 496 | 4.2% | 5.9 |
| khobar to bahrain taxi | 13 | 191 | 6.8% | 4.5 |
| taxi from dammam to bahrain | 12 | 190 | 6.3% | 4.7 |
| al midra tower | 10 | 614 | 1.6% | 4.0 |
| khobar to bahrain | 10 | 391 | 2.6% | 6.6 |
| bahrain to khobar taxi | 9 | 165 | 5.5% | 5.2 |
| bahrain to dammam taxi | 7 | 531 | 1.3% | 7.9 |
| dammam to bahrain taxi cost | 6 | 280 | 2.1% | 4.3 |
| dammam taxi | 3 | 170 | 1.8% | 6.0 |

### Top Pages (3 months)
| Page | Clicks | Impressions | Position |
|------|--------|-------------|----------|
| Homepage | 187 | 6,863 | 8.0 |
| /services/dammam-to-bahrain-taxi (combined ±slash) | 334 | 13,575 | ~7.2 |
| /services/khobar-to-bahrain-taxi (combined ±slash) | 157 | 4,552 | ~7.5 |
| /services/bahrain-taxi (combined ±slash) | 75 | 1,734 | ~6.1 |
| /travel-guide/al-midra-tower (combined) | 47 | 6,174 | ~6.7 |
| /online-taxi-service-in-saudi-arabia (combined) | 37 | 2,942 | ~9.3 |
| /dammam/online-taxi-dammam (combined) | 48 | 4,843 | ~12.5 |
| /dammam/online-taxi-service-in-dammam (combined) | 19 | 2,701 | ~14.0 |
| /al-ahsa/taxi-service-in-al-ahsa (combined) | 25 | 346 | ~5.0 |
| /airport-transfer/al-ahsa-airport-taxi | 12 | 447 | 8.1 |
| /travel-guide/tourist-places-dammam-khobar | 14 | 1,464 | 18.7 |

### CRITICAL Issues Found
1. **Trailing slash duplication**: Pages appear twice in GSC (with/without trailing slash). Dammam-Bahrain splits 172+162 clicks between two URLs. Must fix with canonical + redirect.
2. **Two Dammam pages cannibalizing**: `/dammam/online-taxi-dammam` and `/dammam/online-taxi-service-in-dammam` compete for same queries. Combined 67 clicks but diluted.
3. **Zero EP internal route queries**: No traffic for "dammam to khobar taxi" etc. — massive untapped opportunity.
4. **CWV: 16 URLs need improvement on mobile** — must audit and fix.
5. **Bahrain corridor dominance**: ~80% of organic traffic from Bahrain-related keywords. EP routes are completely uncontested territory.

---

## PR #1: City Hub Pages (6 pages)

**Branch**: `seo/month1-city-hubs`
**Priority**: HIGHEST — These are the parent pages for all location content

### Pages to Create

| # | City | URL Path | Hub or New? | Template |
|---|------|----------|-------------|----------|
| 1 | Dammam | `/dammam/` (hub `page.tsx`) | NEW hub — existing sub-pages at `/dammam/online-taxi-*` | `LocationHubTemplate` |
| 2 | Khobar | `/khobar/` (hub `page.tsx`) | NEW hub — existing sub-page at `/khobar/taxi-service-in-khobar` | `LocationHubTemplate` |
| 3 | Jubail | `/jubail/` (hub `page.tsx`) | NEW hub — existing sub-page at `/jubail/taxi-service-in-jubail` | `LocationHubTemplate` |
| 4 | Dhahran | `/dhahran/` (hub `page.tsx`) | NEW hub — existing sub-page at `/dhahran/taxi-service-in-dhahran` | `LocationHubTemplate` |
| 5 | Al Ahsa | `/al-ahsa/` (hub `page.tsx`) | NEW hub — existing sub-page at `/al-ahsa/taxi-service-in-al-ahsa` | `LocationHubTemplate` |
| 6 | Al Qatif | `/al-qatif/` (new directory + hub) | BRAND NEW — no existing pages | `LocationHubTemplate` |

### Per-Page Requirements
- **Metadata**: Unique title (60 char), description (155 char), canonical URL, OG tags
- **Schema**: `LocalBusiness` + `Service` + `FAQPage` JSON-LD
- **Analytics**: `<PageAnalytics type="location" name="city_slug" />`
- **Content sections**:
  - Hero with city-specific image and H1
  - Service cards linking to sub-pages (taxi service, airport transfer, routes)
  - "Why Choose Noorha in [City]" section (4-6 benefits)
  - Popular routes from this city (internal links to route pages)
  - Area coverage / neighborhoods served
  - Booking CTA with `fireWhatsAppClick('city_hub_cta')`
  - FAQ section (5-8 city-specific questions)
  - Breadcrumbs: Home → Locations → [City]
- **Internal linking**: Each hub links to its sub-pages + cross-links to other city hubs
- **Word count target**: 1,200-1,800 words per hub page

### Al Qatif — Special Notes
Al Qatif is the company's registered address (2326 Al Awamiya Street). This page should emphasize the "local to Al Qatif" angle and connect to the Bahrain corridor (Al Qatif is close to the Causeway).

### Sitemap Updates
Add all 6 hub URLs to `src/app/sitemap.ts`.

---

## PR #2: Eastern Province Route Pages (10 pages)

**Branch**: `seo/month1-route-pages`

### Pages to Create

| # | Route | URL Path | Primary Keywords |
|---|-------|----------|-----------------|
| 1 | Dammam → Khobar | `/routes/dammam-to-khobar/` | taxi dammam to khobar, dammam khobar taxi |
| 2 | Khobar → Dammam | `/routes/khobar-to-dammam/` | taxi khobar to dammam, khobar dammam cab |
| 3 | Dammam → Jubail | `/routes/dammam-to-jubail/` | taxi dammam to jubail, dammam jubail transport |
| 4 | Khobar → Jubail | `/routes/khobar-to-jubail/` | taxi khobar to jubail |
| 5 | Dammam → Dhahran | `/routes/dammam-to-dhahran/` | taxi dammam to dhahran, dammam dhahran taxi |
| 6 | Khobar → Dhahran | `/routes/khobar-to-dhahran/` | taxi khobar to dhahran |
| 7 | Jubail → Dhahran | `/routes/jubail-to-dhahran/` | taxi jubail to dhahran |
| 8 | Dammam → Al Ahsa | `/routes/dammam-to-al-ahsa/` | taxi dammam to al ahsa, dammam hofuf taxi |
| 9 | Khobar → Al Ahsa | `/routes/khobar-to-al-ahsa/` | taxi khobar to al ahsa |
| 10 | Dammam → Al Qatif | `/routes/dammam-to-al-qatif/` | taxi dammam to qatif |

### URL Structure Decision
**NEW `/routes/` directory** — separates EP internal routes from the existing `/services/` pages (which are cross-border/intercity). This creates a clean taxonomy:
- `/services/` = Cross-border & long-distance (Bahrain, Kuwait, Dubai)
- `/routes/` = Regional/EP routes (short-distance, high-frequency)

### Route Page Template (to be created)
Build a reusable `RoutePageTemplate` component:
```
Props: {
  from: { name, slug, lat, lng }
  to: { name, slug, lat, lng }
  distance: string
  duration: string
  pricing: { sedan, suv, van }
  highlights: string[]
  faqs: FAQ[]
}
```

### Per-Page Requirements
- **Metadata**: "[From] to [To] Taxi | Professional Transport | Noorha"
- **Schema**: `TaxiService` + `FAQPage` JSON-LD with `areaServed` for both cities
- **Analytics**: `<PageAnalytics type="service" name="from_to_route_slug" />`
- **Content sections**:
  - Hero: "Taxi from [From] to [To]"
  - Route overview (distance, typical duration, road conditions)
  - Pricing table by vehicle type (from `vehicles.ts` config)
  - What's included (pickup, AC, luggage, etc.)
  - Route highlights / points of interest along the way
  - How to book (3-step process)
  - WhatsApp CTA: `fireWhatsAppClick('route_from_to_cta')`
  - FAQ section (5-6 route-specific questions)
  - Related routes (cross-links)
  - Breadcrumbs: Home → Routes → [From] to [To]
- **Word count target**: 800-1,200 words per route page
- **Bidirectional linking**: Each route page links to its reverse (Dammam→Khobar links to Khobar→Dammam)

### Sitemap Updates
Add all 10 route URLs to `src/app/sitemap.ts`.

---

## PR #3: Fleet Section (3 vehicle category pages + fleet hub)

**Branch**: `seo/month1-fleet-pages`

### Pages to Create

| # | Page | URL Path |
|---|------|----------|
| 1 | Fleet Hub | `/fleet/` |
| 2 | Business Sedan | `/fleet/business-sedan/` |
| 3 | Family SUV | `/fleet/family-suv/` |
| 4 | Luxury Van | `/fleet/luxury-van/` |

### Fleet Hub Page
- Overview of all vehicle categories
- Image gallery grid
- Quick comparison table
- Links to each category page
- CTA: "Not sure which vehicle? Contact us on WhatsApp"

### Per Vehicle Category Page
- **Metadata**: "[Category] for Hire in Saudi Arabia | Noorha Transport"
- **Schema**: `Product` + `Vehicle` JSON-LD
- **Analytics**: `<PageAnalytics type="service" name="fleet_category_slug" />`
- **Content sections**:
  - Hero with vehicle image(s)
  - Vehicle specs (passengers, luggage, features)
  - Best for: (use cases — airport transfer, family trip, corporate, etc.)
  - Available models in this category
  - Pricing overview (reference `vehicles.ts`)
  - Photo gallery (use images from `assets/vehicles/`)
  - Booking CTA
  - FAQ (3-5 questions about the vehicle category)
  - Breadcrumbs: Home → Fleet → [Category]
- **Word count target**: 600-1,000 words per page

### Navigation Update
Add "Fleet" link to the main navigation in `Navbar.tsx`.

---

## PR #4: Blog Posts (4 articles)

**Branch**: `seo/month1-blog-posts`

### Articles to Write

| # | Title | Slug | Target Keywords | Word Count |
|---|-------|------|----------------|------------|
| 1 | Complete Guide to Transportation in Eastern Province Saudi Arabia | `eastern-province-transport-guide` | eastern province transport, EP taxi guide, transportation dammam khobar | 2,500+ |
| 2 | Dammam Airport (DMM) Complete Transfer Guide 2026 | `dammam-airport-transfer-guide` | dammam airport taxi, king fahd airport transfer, DMM airport transport | 2,000+ |
| 3 | King Fahd Causeway Guide: Everything You Need to Know for KSA-Bahrain Travel | `king-fahd-causeway-guide` | king fahd causeway, ksa bahrain border, causeway taxi | 2,500+ |
| 4 | Best Places to Visit in Eastern Province: A Travel & Transport Guide | `eastern-province-travel-guide` | eastern province tourist places, things to do eastern province, EP travel | 2,000+ |

### Blog Infrastructure
The blog uses a CMS with dynamic `[slug]` routing and `BlogAnalytics` component. Posts should be:
- Created via the admin CMS OR as static pages under `/blog/[slug]/page.tsx`
- **Decision needed**: Does the blog CMS (Supabase-backed?) support direct content creation, or should we create static pages?

### Per-Article Requirements
- **Schema**: `Article` + `BreadcrumbList` JSON-LD
- **Analytics**: `<BlogAnalytics slug={slug} title={title} category={category} />`
- **Content**: Well-structured with H2/H3 headings, internal links to service/route/city pages
- **Images**: Relevant photos with descriptive alt text
- **Scroll depth markers**: `<div id="blog-depth-50" />` and `<div id="blog-depth-90" />` at 50% and 90% of content
- **CTAs**: WhatsApp booking CTAs embedded naturally within the content
- **Internal linking**: Each post links to 3-5 relevant service/city/route pages

---

## PR #5: Optimize Existing 17 Service Pages

**Branch**: `seo/month1-service-optimization`

### Existing Service Pages to Optimize

| # | Page | Current Title | Issues to Fix |
|---|------|--------------|---------------|
| 1 | `/services/dammam-to-bahrain-taxi` | Convenient Dammam to Bahrain Taxi | Add Service schema, expand content |
| 2 | `/services/khobar-to-bahrain-taxi` | (check) | Add Service schema, expand content |
| 3 | `/services/bahrain-taxi` | (check) | Add Service schema |
| 4 | `/services/intercity-taxi` | (check) | Expand content, add route links |
| 5 | `/services/makkah-to-madinah-taxi` | (check) | Add Service schema |
| 6-17 | Remaining 12 service pages | (audit needed) | Meta titles, descriptions, schema, content depth |

### Optimization Checklist (per page)
- [ ] Meta title: Under 60 chars, includes primary keyword + brand
- [ ] Meta description: Under 155 chars, includes CTA language
- [ ] Canonical URL: Correct and consistent
- [ ] Schema markup: Add `TaxiService` or `Service` schema (many only have `FAQPage`)
- [ ] Content depth: Minimum 800 words (many are thin)
- [ ] Internal links: Add links to related routes, city hubs, fleet pages
- [ ] WhatsApp CTA: Ensure `fireWhatsAppClick()` is on every CTA
- [ ] Image alt text: Descriptive, keyword-rich
- [ ] H1 tag: One per page, includes primary keyword
- [ ] FAQ section: At least 3 questions with `FAQPage` schema

---

## Technical SEO Tasks

### URL Restructure Plan
| Current | Proposed | Action |
|---------|----------|--------|
| `/dammam/online-taxi-dammam` | Keep (but add hub at `/dammam/`) | Add parent hub |
| `/dammam/online-taxi-service-in-dammam` | Consider consolidating with above | Evaluate canonical |
| No `/routes/` directory | Add `/routes/` for EP routes | New directory |
| No `/fleet/` directory | Add `/fleet/` for vehicle pages | New directory |
| No `/locations/` hub | Consider `/locations/` index page | Month 2 |

**Note**: Two Dammam pages exist (`online-taxi-dammam` and `online-taxi-service-in-dammam`). These may be cannibalizing. Evaluate during optimization whether to consolidate.

### Schema Enhancement
- Add `TaxiService` schema to all service pages (currently only `FAQPage` on most)
- Add `LocalBusiness` with `areaServed` to all city hubs
- Enhance root layout schema with `hasOfferCatalog` listing all services
- Add `BreadcrumbList` schema to all pages

### Sitemap Split Strategy
Currently one flat `sitemap.ts`. Plan for Month 2-3 when we have 100+ pages:
- `/sitemap.xml` → sitemap index
- `/sitemap-services.xml` → service pages
- `/sitemap-routes.xml` → route pages
- `/sitemap-locations.xml` → city/location pages
- `/sitemap-blog.xml` → blog posts
- `/sitemap-static.xml` → about, contact, FAQ, terms

For now (Month 1): Keep single sitemap but organize entries by category with comments.

### Core Web Vitals Audit
- Run Lighthouse on top 5 pages (home, dammam, khobar, services, book)
- Check: LCP, INP, CLS scores
- Common issues to look for:
  - Large hero images (need WebP/AVIF + proper sizing)
  - Unoptimized Google Maps embed
  - Font loading (Montserrat via Google Fonts)
  - Third-party scripts (GA4, Clarity, Vercel Analytics)

---

## Local SEO Tasks

### GBP Optimization Plan
1. **Profile completeness**: Verify all fields filled (hours, services, attributes)
2. **Category optimization**: Primary = "Taxi Service", Secondary = "Airport Shuttle Service", "Limousine Service", "Transportation Service"
3. **Service descriptions**: Add all services with descriptions
4. **Photos**: Upload fleet photos from `assets/vehicles/`
5. **Posts**: Create weekly GBP posts (can be repurposed from blog content)
6. **Q&A**: Pre-populate with common questions

### Directory Submissions (Top 20)
Deliverable: Spreadsheet with directory name, URL, submission status, login credentials.

Categories:
- Saudi business directories (Daleeli, YellowPages.sa, etc.)
- Travel/transport directories (TripAdvisor, Viator, GetYourGuide)
- GCC directories
- Google Maps, Apple Maps, Bing Places, Waze

### Review Collection Strategy
1. Post-trip WhatsApp message template with direct GBP review link
2. QR code for vehicle dashboards
3. Email follow-up template
4. Target: 10-15 reviews in Month 1

---

## Internal Linking Strategy

### New Link Architecture
```
Homepage
├── /dammam/ (hub) → /dammam/online-taxi-*, /routes/dammam-to-*
├── /khobar/ (hub) → /khobar/taxi-service-*, /routes/khobar-to-*
├── /jubail/ (hub) → /jubail/taxi-service-*, /routes/jubail-to-*
├── /dhahran/ (hub) → /dhahran/taxi-service-*, /routes/dammam-to-dhahran
├── /al-ahsa/ (hub) → /al-ahsa/taxi-service-*, /routes/*-to-al-ahsa
├── /al-qatif/ (hub) → /routes/dammam-to-al-qatif
├── /fleet/ (hub) → /fleet/business-sedan, /fleet/family-suv, /fleet/luxury-van
├── /routes/ → All 10 EP route pages (cross-linked)
├── /services/ → Existing 17 cross-border/intercity pages
├── /blog/ → 4 new articles (link to relevant service/route/city pages)
└── /airport-transfer/ → Existing airport pages
```

### Cross-Linking Rules
- Every city hub links to every route originating from that city
- Every route page links to both origin and destination city hubs
- Every route page links to the reverse direction route
- Blog posts link to 3-5 relevant service/route/city pages
- Fleet pages link to booking and relevant services
- Footer: Add "Popular Routes" and "Locations" sections

---

## Execution Order

| Week | Tasks | PR |
|------|-------|----|
| Week 1 (Mar 27 - Apr 2) | Baseline data pull, city hub pages, RoutePageTemplate | PR #1 |
| Week 2 (Apr 3 - Apr 9) | Route pages, fleet section | PR #2, PR #3 |
| Week 3 (Apr 10 - Apr 16) | Blog posts, service page optimization begins | PR #4, PR #5 starts |
| Week 4 (Apr 17 - Apr 23) | Complete service optimization, technical SEO, local SEO | PR #5 complete |
| Week 5 (Apr 24 - Apr 30) | CWV audit, GBP optimization, directory submissions, review strategy | Deliverables |

---

## Success Metrics (End of Month 1)

| Metric | Target |
|--------|--------|
| New pages live | 23-25 |
| Service pages optimized | 17 |
| Total indexed pages | ~60 |
| Schema types deployed | 5+ (TaxiService, LocalBusiness, FAQPage, Service, Article) |
| Internal links added | 100+ new cross-links |
| Blog posts published | 4 |
| GBP optimized | Yes |
| Directory submissions | 20 |
| Reviews collected | 10-15 |

---

**Last Updated**: 2026-03-27
**Status**: READY FOR EXECUTION
