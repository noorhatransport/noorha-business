# PROMPT: Saudi Arabia to Kuwait Taxi Service — Paid Ads & Landing Pages

> Copy this entire prompt and paste it into a new Claude Code window.
> Working directory should be: /Users/zulfanhameed/noorha-transport
> Website codebase is at: /Users/zulfanhameed/noorhatransport

---

## CONTEXT

I run Noorha Transport — a premium transportation service in Saudi Arabia. Website: noorhatransport.com (Next.js app at /Users/zulfanhameed/noorhatransport).

We're launching a new service: **Saudi Arabia to Kuwait taxi/private transfer**. This is a HIGH-DEMAND route right now because **air traffic between Saudi and Kuwait is currently shut down due to the Iran situation**. Only a few drivers can actually make this trip, giving us a significant competitive advantage.

### Business Model (Two-Tier)

**First Class — Door-to-Door Direct**:
- Vehicles: Cadillac Escalade (AED 9,000), GMC Yukon/Tahoe (AED 7,500)
- Single premium vehicle, one driver, entire journey
- Professional border handling at Khafji border crossing

**Economy — Multi-Leg Managed Transfer**:
- Vehicles: Toyota sedans (AED 6,500)
- Leg 1: Saudi city → Khafji (Saudi-Kuwait border)
- Leg 2: Khafji border crossing
- Leg 3: Kuwait side → Kuwait City/destination
- Fully managed end-to-end

**NOTE**: Pricing above is for Dubai-to-KSA routes. You'll need to ASK ME for Saudi-to-Kuwait specific pricing before building pages. Use placeholder [PRICE] until I confirm.

### Key Context
- Air traffic is SHUT DOWN — this is the ONLY reliable way to travel between Saudi and Kuwait right now
- Very few operators can do this route — we have a competitive moat
- Border crossing is at Khafji (Saudi side) → Nuwaiseeb (Kuwait side)
- Primary routes: Dammam→Kuwait, Riyadh→Kuwait, Khobar→Kuwait, Jubail→Kuwait
- Buyers: stranded travelers, business travelers, families, workers returning to Kuwait

---

## TASK 1: Research & Planning

Before building anything, research the following in parallel:

1. **Keyword research**: Search Google for "saudi to kuwait taxi", "dammam to kuwait taxi", "riyadh to kuwait taxi", "how to travel saudi to kuwait now", "saudi kuwait border crossing taxi" etc. Understand what people are searching for given the flight shutdown.

2. **Competitive landscape**: Find who else offers this service. Check ghtrips.com, gettransfer.com, chachataxi.com and any Saudi/Kuwait taxi services.

3. **Route details**: Research distances and travel times for each route:
   - Dammam to Kuwait City
   - Khobar to Kuwait City
   - Riyadh to Kuwait City
   - Jubail to Kuwait City
   - Dhahran to Kuwait City

4. **Current situation context**: Search for latest news on Saudi-Kuwait flight status, border crossing rules, and travel requirements.

5. **Existing website structure**: Read these files to understand the codebase patterns:
   - `/Users/zulfanhameed/noorhatransport/src/app/services/dubai-to-riyadh-taxi/page.tsx` (reference page — FOLLOW THIS PATTERN EXACTLY)
   - `/Users/zulfanhameed/noorhatransport/src/app/sitemap.ts`
   - `/Users/zulfanhameed/noorhatransport/src/config/contact.ts`
   - `/Users/zulfanhameed/noorhatransport/CLAUDE.md` (analytics rules — MUST follow)

Create a detailed plan at: `/Users/zulfanhameed/noorha-transport/memory/projects/active/paid-ads-saudi-to-kuwait-mar2026.md`

---

## TASK 2: Build Landing Pages (Run agents in parallel)

Create SEPARATE focused landing pages for each route. Each page should follow the EXACT same structure as `/Users/zulfanhameed/noorhatransport/src/app/services/dubai-to-riyadh-taxi/page.tsx`:

### Pages to Create (launch parallel agents for each):

**Page 1: Dammam to Kuwait** `/services/dammam-to-kuwait-taxi/page.tsx`
- Buyer: Eastern Province residents, workers, stranded travelers
- Noorha's HOME TERRITORY — emphasize local expertise
- Shortest Saudi→Kuwait route
- Keywords: dammam to kuwait taxi, dammam to kuwait by car, taxi from dammam to kuwait

**Page 2: Riyadh to Kuwait** `/services/riyadh-to-kuwait-taxi/page.tsx`
- Buyer: Capital city business travelers, families, workers
- Longer route but high demand
- Keywords: riyadh to kuwait taxi, riyadh to kuwait by car, riyadh to kuwait transport

**Page 3: Khobar to Kuwait** `/services/khobar-to-kuwait-taxi/page.tsx`
- Buyer: Similar to Dammam but Khobar-specific
- Keywords: khobar to kuwait taxi, al khobar to kuwait by car

**Page 4: Saudi to Kuwait Hub** `/services/saudi-to-kuwait-taxi/page.tsx`
- Catch-all hub page linking to all route-specific pages
- Keywords: saudi to kuwait taxi, saudi arabia to kuwait by car, ksa to kuwait transport

### CRITICAL for each page:
- Include `<PageAnalytics type="service" name="[route_slug]" />` as first child
- Add FAQ schema (faqJsonLd) + Service schema (serviceJsonLd)
- Use `buildWhatsAppUrl()` with route-specific pre-filled messages
- Include comparison table: Private Car vs Flight (emphasize flights are SHUT DOWN)
- The "Ideal For" section should prominently mention stranded travelers
- Tips section should cover border crossing documents, Khafji-Nuwaiseeb process
- Related routes should cross-link to all other Saudi→Kuwait pages
- Sidebar with pricing + WhatsApp CTA + trust signals

### URGENT MESSAGING angle for ads:
Since flights are shut down, the landing pages should prominently feature messaging like:
- "Flights Suspended? We've Got You Covered"
- "The Reliable Way Between Saudi & Kuwait — When Flights Can't Fly"
- "Door-to-Door Transfer While Air Traffic is Suspended"
This is the PRIMARY conversion hook — people are actively looking for alternatives NOW.

---

## TASK 3: Update Sitemap

After all pages are built, update `/Users/zulfanhameed/noorhatransport/src/app/sitemap.ts` to include all new routes.

---

## TASK 4: Google Ads Campaign Plan

Create a campaign plan section in the project file with:

### Campaign Structure
```
Campaign: Saudi-to-Kuwait Routes [Search]
├── Ad Group: Dammam → Kuwait (highest priority — home territory)
├── Ad Group: Riyadh → Kuwait
├── Ad Group: Khobar → Kuwait
├── Ad Group: Generic Saudi → Kuwait
└── Ad Group: Flight Alternative (NEW — capitalize on shutdown)
```

### Flight-Alternative Ad Group (UNIQUE opportunity)
Keywords:
- saudi to kuwait flights cancelled
- how to travel to kuwait from saudi
- saudi kuwait flights suspended
- alternative to flying saudi to kuwait
- saudi to kuwait by road

This ad group targets people searching because they CAN'T fly — extremely high intent, probably low competition since it's a new situation.

### Ad Copy Templates
Write 3 ad variations per ad group:
1. Urgency/availability angle ("Flights Suspended? Travel by Road")
2. Comfort/premium angle ("Door-to-Door in Cadillac Escalade")
3. Price/value angle ("From [PRICE] — All-Inclusive Border Handling")

### Budget
- Start with SAR 3,000-5,000/month
- Focus 60% on "flight alternative" keywords (lowest competition, highest intent)
- 40% on route-specific keywords

---

## TECHNICAL REQUIREMENTS

- Framework: Next.js (App Router) with TypeScript
- Styling: Tailwind CSS with zinc/vermilion color scheme
- Components to use: Navbar, Footer, StickyMobileCTA, Breadcrumbs, FAQSection, PageAnalytics
- Contact config: import { CONTACT, buildWhatsAppUrl } from '@/config/contact'
- Analytics: Follow CLAUDE.md rules exactly (PageAnalytics, fireWhatsAppClick, etc.)
- Images: Use existing `/images/hero-bg.png` or `/images/dest-*.png` for heroes
- Vehicle photos available at `/public/images/vehicle-*.jpeg`

---

## EXECUTION ORDER

1. Read reference files (dubai-to-riyadh-taxi page, CLAUDE.md, contact.ts, sitemap.ts)
2. Do keyword research and competitive analysis (web search)
3. Create project plan file
4. ASK ME for Saudi-to-Kuwait pricing before building pages
5. Launch parallel agents to build all 4 pages simultaneously
6. Update sitemap.ts
7. Run TypeScript check: `cd /Users/zulfanhameed/noorhatransport && npx tsc --noEmit`
8. Create ad copy document

---

## IMPORTANT NOTES

- NEVER push to main directly — create a feature branch and PR (per CLAUDE.md git rules)
- The flight shutdown situation makes this TIME-SENSITIVE — speed matters
- The "flights suspended" angle is our #1 competitive advantage in ads
- Dammam→Kuwait is the priority route (our home territory, shortest distance)
- Cross-link between all Saudi→Kuwait pages AND the existing Dubai→KSA pages
