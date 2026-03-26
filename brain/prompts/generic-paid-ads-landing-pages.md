# GENERIC PROMPT: Paid Ads Landing Pages for Noorha Transport

> **How to use**: Copy this entire prompt into a new Claude Code window. Fill in the variables marked with `{{VARIABLE}}` before pasting. Delete any sections that don't apply.
>
> Working directory: `/Users/zulfanhameed/noorha-transport`
> Website codebase: `/Users/zulfanhameed/noorhatransport`

---

## CONTEXT

I run **Noorha Transport** — a premium transportation service based in Saudi Arabia's Eastern Province. Website: noorhatransport.com (Next.js 16 app at `/Users/zulfanhameed/noorhatransport`).

I want to create paid ads landing pages for a **new route cluster**: `{{ROUTE_CLUSTER_NAME}}`

**Example route clusters we've done before:**
- Dubai → Saudi Arabia (Riyadh, Dammam, Makkah, Jeddah, Madinah)
- Saudi → Kuwait (Dammam, Riyadh, Khobar → Kuwait City)

---

## ROUTE DETAILS

### Routes to Build (one landing page per route)

| # | Route | Slug | Distance | Time | Priority |
|---|-------|------|----------|------|----------|
| 1 | {{ORIGIN_1}} to {{DEST_1}} | {{SLUG_1}} | {{DISTANCE_1}} | {{TIME_1}} | {{PRIORITY_1}} |
| 2 | {{ORIGIN_2}} to {{DEST_2}} | {{SLUG_2}} | {{DISTANCE_2}} | {{TIME_2}} | {{PRIORITY_2}} |
| 3 | {{ORIGIN_3}} to {{DEST_3}} | {{SLUG_3}} | {{DISTANCE_3}} | {{TIME_3}} | {{PRIORITY_3}} |
| 4 | Hub/Catch-All Page | {{HUB_SLUG}} | — | — | Medium |

> Add or remove rows as needed. Minimum: 2 route pages + 1 hub page.

### Border Crossing (if cross-border)
- **Border point**: {{BORDER_POINT_A}} → {{BORDER_POINT_B}}
- **Country A**: {{COUNTRY_A}}
- **Country B**: {{COUNTRY_B}}
- **Border notes**: {{BORDER_NOTES}}

> Delete this section if routes are domestic (within Saudi Arabia).

---

## PRICING

### First Class — Door-to-Door Direct
| Vehicle | Price | Currency |
|---------|-------|----------|
| Cadillac Escalade | {{PRICE_ESCALADE}} | {{CURRENCY}} |
| GMC Yukon / Tahoe (New) | {{PRICE_GMC}} | {{CURRENCY}} |

### Economy — Multi-Leg Managed Transfer
| Vehicle | Price | Currency |
|---------|-------|----------|
| Toyota Sedan Fleet | {{PRICE_ECONOMY}} | {{CURRENCY}} |

**Economy legs for this route cluster:**
- Leg 1: {{ECONOMY_LEG_1}}
- Leg 2: {{ECONOMY_LEG_2}}
- Leg 3: {{ECONOMY_LEG_3}}

> If pricing is NOT confirmed yet, use `[PRICE]` as placeholder and ASK ME before building pages.

---

## BUYER PERSONAS (per route)

| Route | Primary Buyer | Secondary Buyer | Messaging Angle |
|-------|--------------|-----------------|-----------------|
| {{ROUTE_1_NAME}} | {{BUYER_1_PRIMARY}} | {{BUYER_1_SECONDARY}} | {{ANGLE_1}} |
| {{ROUTE_2_NAME}} | {{BUYER_2_PRIMARY}} | {{BUYER_2_SECONDARY}} | {{ANGLE_2}} |
| {{ROUTE_3_NAME}} | {{BUYER_3_PRIMARY}} | {{BUYER_3_SECONDARY}} | {{ANGLE_3}} |

> Different routes attract different buyers. A Makkah route attracts Umrah pilgrims while a Riyadh route attracts business travelers. Tailor page content to the buyer.

---

## SPECIAL MARKET CONDITIONS (if any)

> Delete this section if there's no special angle. Fill it in if there's a unique market situation to exploit in ad copy.

**Condition**: {{MARKET_CONDITION}}
**Impact**: {{MARKET_IMPACT}}
**Ad angle**: {{AD_ANGLE}}

Examples:
- "Flights between Saudi and Kuwait are suspended due to Iran situation → only road travel available"
- "Hajj season 2026 → massive demand for Jeddah/Makkah transfers"
- "Aramco shutdown period → workers need transport between cities"

---

## EXECUTION INSTRUCTIONS

### Step 1: Read Reference Files (mandatory before building)

Read these files to understand the codebase patterns:
```
/Users/zulfanhameed/noorhatransport/src/app/services/dubai-to-riyadh-taxi/page.tsx  ← PRIMARY REFERENCE (follow this structure exactly)
/Users/zulfanhameed/noorhatransport/src/app/services/dubai-to-makkah-taxi/page.tsx  ← Religious travel reference (if Umrah/Hajj routes)
/Users/zulfanhameed/noorhatransport/src/app/services/dubai-to-dammam-taxi/page.tsx  ← Eastern Province reference (if Aramco/industrial routes)
/Users/zulfanhameed/noorhatransport/src/app/services/dubai-to-saudi-arabia-taxi/page.tsx  ← Hub page reference
/Users/zulfanhameed/noorhatransport/CLAUDE.md  ← Analytics rules (MUST follow)
/Users/zulfanhameed/noorhatransport/src/config/contact.ts  ← Contact config
/Users/zulfanhameed/noorhatransport/src/app/sitemap.ts  ← Update after building pages
```

### Step 2: Research (run in parallel)

1. **Keyword research** — Web search for "[origin] to [destination] taxi", "[origin] to [destination] by car", "[origin] to [destination] private car" for each route. Find what people actually search.
2. **Competitive analysis** — Search for competitors on these routes. Check gettransfer.com, ghtrips.com, chachataxi.com and local taxi services.
3. **Route details** — Verify distances, travel times, border crossing info for each route.
4. **Special conditions** — If there's a market event (flights shut down, Hajj season, etc.), research current news for ad copy angles.

### Step 3: Create Project Plan

Save to: `/Users/zulfanhameed/noorha-transport/memory/projects/active/paid-ads-{{CLUSTER_SLUG}}-{{MONTH}}{{YEAR}}.md`

Plan should include:
- All keyword groups per route (primary, long-tail, negative keywords)
- Google Ads campaign structure (campaign → ad groups → keywords → landing pages)
- Ad copy variations (3 per ad group: urgency angle, premium angle, value angle)
- Budget recommendation (phased: testing → optimization → scaling)
- Competitive advantages for this route cluster

### Step 4: Build Landing Pages (launch parallel agents)

**Launch one agent per page — all in parallel.** Each agent should:

1. `mkdir -p` the directory
2. Read the reference page (`dubai-to-riyadh-taxi/page.tsx`)
3. Create the page following the EXACT same structure

#### Page Structure (every page must have ALL of these sections):

```
1.  Hero Section
    - Image (use /images/hero-bg.png or /images/dest-{city}.png if available)
    - Breadcrumbs (variant="light")
    - Badge with route-specific tagline
    - H1 with vermilion accent span
    - Subhead with key selling points
    - WhatsApp CTA + Book Online CTA
    - Trust badges (price, time, border handling, unique selling point)

2.  Intro Section
    - H2 with underline decoration-vermilion
    - 2 paragraphs explaining the route and why road travel makes sense

3.  Two-Tier Pricing Cards (side by side)
    - First Class card (dark bg): Cadillac + GMC pricing, 5 bullet features
    - Economy card (white bg): Toyota pricing, 3 leg steps, 4 bullet features
    - Each card has its own WhatsApp CTA with pre-filled message

4.  Comparison Table (Private Car vs Alternative)
    - 6-7 rows comparing our service vs flying/bus/self-drive
    - Route-specific comparisons (e.g., Umrah routes compare luggage for Zamzam water)

5.  Ideal For Section (dark bg)
    - 4 buyer persona cards with icons
    - Route-specific personas (business, families, religious, workers, etc.)

6.  Route Details (3-column grid)
    - Distance, Travel Time, Border Crossing

7.  How It Works (3 steps)
    - Get a Quote → Choose Your Class → We Pick You Up

8.  Tips Section (amber bg)
    - 6 route-specific travel tips

9.  FAQ Section (6-8 questions)
    - Route-specific FAQs
    - Must include: cost, time, documents, class difference, return trip

10. CTA Banner (vermilion bg)
    - WhatsApp + Book Online

11. Sidebar (sticky, 1/3 width on desktop)
    - Quick pricing reference
    - WhatsApp + Call CTAs
    - Trust signals (4 items)
    - Related routes (4 links)
```

#### Technical Requirements per Page:

```tsx
// Required imports
import PageAnalytics from "@/components/analytics/PageAnalytics";
import { CONTACT, buildWhatsAppUrl } from "@/config/contact";
import FAQSection from "@/components/ui/FAQSection";
import Breadcrumbs from "@/components/layout/Breadcrumbs";
import StickyMobileCTA from "@/components/layout/StickyMobileCTA";
import Navbar from "@/components/layout/Navbar";
import Footer from "@/components/layout/Footer";

// Required structured data
const faqJsonLd = { ... };      // FAQPage schema
const serviceJsonLd = { ... };  // Service schema with pricing

// Required component
<PageAnalytics type="service" name="{{route_slug}}" />

// Required WhatsApp pre-fill
const WHATSAPP_MSG = "Hi, I'd like to book a {{origin}} to {{destination}} taxi. Can I get a quote?";

// Required metadata
export const metadata: Metadata = {
    title: "...",
    description: "...",
    keywords: [...],
    alternates: { canonical: "https://noorhatransport.com/services/{{slug}}" },
};
```

#### Hub Page (lighter structure):
- Hero → Route Cards Grid (link to each individual page) → Two-Tier Overview → Why Noorha (4 cards) → How It Works → CTA Banner
- NO sidebar, NO FAQ section, NO comparison table
- `<StickyMobileCTA />` with NO props

### Step 5: Update Sitemap

Add all new routes to `/Users/zulfanhameed/noorhatransport/src/app/sitemap.ts`

### Step 6: Verify Build

```bash
cd /Users/zulfanhameed/noorhatransport && npx tsc --noEmit
```

Filter out pre-existing test file errors — only fix errors in NEW files.

### Step 7: Update Google Ads Setup Guide

Append new ad groups to `/Users/zulfanhameed/noorhatransport/docs/google-ads-setup-guide.md`

---

## NAMING CONVENTIONS

| Item | Pattern | Example |
|------|---------|---------|
| Page directory | `/services/{origin}-to-{dest}-taxi/` | `/services/dammam-to-kuwait-taxi/` |
| PageAnalytics name | `{origin}_to_{dest}_taxi` | `dammam_to_kuwait_taxi` |
| Canonical URL | `https://noorhatransport.com/services/{slug}` | `.../services/dammam-to-kuwait-taxi` |
| WhatsApp msg | `"Hi, I'd like to book a {Origin} to {Dest} taxi..."` | |
| Project plan file | `paid-ads-{cluster}-{monthyear}.md` | `paid-ads-saudi-to-kuwait-mar2026.md` |
| Sitemap entry | `'/services/{origin}-to-{dest}-taxi'` | |

---

## STYLING REFERENCE

- **Primary color**: vermilion (red-orange, used for CTAs, accents, badges)
- **Dark sections**: bg-zinc-900 text-white
- **Light sections**: bg-zinc-50 or bg-white
- **Tips section**: bg-amber-50 with amber-900 text
- **CTA banner**: bg-vermilion
- **Cards**: rounded-3xl with border border-zinc-100 shadow-sm
- **Fonts**: font-black italic tracking-tight for headings
- **Icons**: lucide-react (CheckCircle2, Clock, MapPin, Globe, ShieldCheck, MessageCircle, Star, Users, Luggage, etc.)

---

## PARALLEL AGENT INSTRUCTIONS

When building pages, launch ALL page agents simultaneously in a single message. Example for 4 pages:

```
Agent 1 (background): Build {Origin1} to {Dest1} page
Agent 2 (background): Build {Origin2} to {Dest2} page
Agent 3 (background): Build {Origin3} to {Dest3} page
Agent 4 (background): Build Hub page
```

Each agent prompt should include:
1. The exact file path to create
2. Route-specific details (distance, time, border, buyer persona)
3. Instruction to read the reference page first
4. All pricing info
5. Keywords for metadata
6. WhatsApp message text
7. Related routes for sidebar
8. FAQ topics to cover

---

## AD COPY TEMPLATES (per ad group)

Generate 3 ad variations per route:

**Variation 1 — Urgency/Availability**
```
Headline 1: {Origin} to {Dest} Taxi | Available Now
Headline 2: Door-to-Door in {{HOURS}} Hours
Headline 3: Book via WhatsApp — 24/7
Description: {Route-specific urgency copy}. First Class & Economy options. Professional border handling. Get your quote in 2 minutes.
```

**Variation 2 — Premium/Comfort**
```
Headline 1: {Origin} to {Dest} | Cadillac Escalade
Headline 2: Premium Door-to-Door Transfer
Headline 3: 20+ Years Cross-Border Expertise
Description: Travel in a Cadillac Escalade or GMC Yukon. {Route benefit}. Single vehicle, one driver, seamless journey. WhatsApp for instant quote.
```

**Variation 3 — Value/Price**
```
Headline 1: {Origin} to {Dest} from {{CURRENCY}} {{PRICE_ECONOMY}}
Headline 2: First Class & Economy Options
Headline 3: All-Inclusive — No Hidden Fees
Description: Premium & budget options available. {Comparison to flights}. Border handling included. Unlimited luggage. Book now via WhatsApp.
```

---

## CHECKLIST (verify before finishing)

- [ ] All route pages created and rendering
- [ ] Hub page links to all individual route pages
- [ ] All pages have PageAnalytics component
- [ ] All pages have FAQ + Service JSON-LD schema
- [ ] All WhatsApp CTAs use buildWhatsAppUrl() with pre-filled messages
- [ ] Sitemap.ts updated with all new routes
- [ ] TypeScript compiles clean (npx tsc --noEmit)
- [ ] Project plan saved to memory/projects/active/
- [ ] Ad copy document generated
- [ ] Google Ads guide updated with new ad groups
- [ ] Cross-linking between all new pages working
- [ ] Vehicle photos referenced where appropriate

---

## EXAMPLE: Filling in the Variables

For a "Saudi to Bahrain" route cluster:

```
{{ROUTE_CLUSTER_NAME}} = Saudi Arabia to Bahrain
{{CLUSTER_SLUG}} = saudi-to-bahrain
{{ORIGIN_1}} = Dammam     {{DEST_1}} = Bahrain     {{SLUG_1}} = dammam-to-bahrain-taxi
{{ORIGIN_2}} = Khobar     {{DEST_2}} = Bahrain     {{SLUG_2}} = khobar-to-bahrain-taxi
{{ORIGIN_3}} = Riyadh     {{DEST_3}} = Bahrain     {{SLUG_3}} = riyadh-to-bahrain-taxi
{{HUB_SLUG}} = saudi-to-bahrain-taxi
{{BORDER_POINT_A}} = King Fahd Causeway (Saudi)
{{BORDER_POINT_B}} = King Fahd Causeway (Bahrain)
{{PRICE_ESCALADE}} = 500   {{PRICE_GMC}} = 400   {{PRICE_ECONOMY}} = 250
{{CURRENCY}} = SAR
```

---

**Version**: 1.0
**Created**: 2026-03-07
**Based on**: Dubai-to-KSA route cluster (6 pages successfully built)
