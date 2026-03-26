# Noorha Transport Website — Complete Knowledge Base

**Live URL**: https://noorhatransport.com
**Codebase**: `/Users/zulfanhameed/noorhatransport`
**Hosting**: Vercel (continuous deployment)
**Status**: Live in production as of February 2026
**Last Studied**: 2026-03-07

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | Next.js 16.1.6 (App Router) |
| Language | TypeScript 5 (strict mode) |
| Styling | Tailwind CSS 4 + Montserrat font |
| Database | Supabase (PostgreSQL) |
| Auth | Supabase Auth (email + password) |
| Email | Resend 6.9.1 |
| Validation | Zod 4.3.6 |
| Editor | Tiptap 3.19.0 (rich text) |
| Maps | Google Maps API (KSA + Bahrain) |
| Analytics | Google Analytics 4 + Microsoft Clarity |
| Performance | Vercel Analytics |
| Testing | Vitest 4.0.18 |

---

## Site Architecture — All Pages

### Public Pages

| Route | Purpose |
|-------|---------|
| `/` | Homepage — hero, booking form, stats, services, testimonials, FAQ |
| `/book/` | 4-step booking flow |
| `/services/` | Services overview |
| `/about-us/` | Company information |
| `/contact-us/` | Contact form + location |
| `/faq/` | Frequently asked questions |
| `/privacy-policy/` | Privacy policy |
| `/terms-and-conditions/` | Terms and conditions |
| `/blog/` | Blog listing |
| `/blog/[slug]/` | Individual blog posts |

### Service Pages
- `/services/bahrain-taxi/`
- `/services/dammam-to-bahrain-taxi/`
- `/services/khobar-to-bahrain-taxi/`
- `/services/makkah-to-madinah-taxi/`
- `/services/intercity-taxi/`

### Airport Transfer Pages
- `/airport-transfer/`
- `/airport-transfer/dammam-airport-taxi/`
- `/airport-transfer/riyadh-airport-taxi/`
- `/airport-transfer/al-ahsa-airport-taxi/`

### Location-Specific SEO Pages
- `/dammam/online-taxi-dammam/`
- `/dammam/online-taxi-service-in-dammam/`
- `/khobar/taxi-service-in-khobar/`
- `/dhahran/taxi-service-in-dhahran/`
- `/jubail/taxi-service-in-jubail/`
- `/al-ahsa/taxi-service-in-al-ahsa/`
- `/online-taxi-service-in-saudi-arabia/`

### Travel Guide Pages
- `/travel-guide/tourist-places-in-dammam-and-khobar/`
- `/travel-guide/best-tourist-places-in-eastern-province/`
- `/travel-guide/al-midra-tower/`

### Admin Panel (Protected — Supabase Auth)
| Route | Purpose |
|-------|---------|
| `/admin/login/` | Authentication |
| `/admin/` | Dashboard with KPIs and upcoming trips |
| `/admin/bookings/` | Booking management |
| `/admin/quotes/` | Quote request processing |
| `/admin/blog/` | Blog post list |
| `/admin/blog/editor/` | Rich text editor |
| `/admin/blog/categories/` | Category management |
| `/admin/settings/` | Admin settings |

**Admin Login**: `noorhatransportbooking@gmail.com`

---

## Lead Capture System

### 4 Capture Channels

1. **Booking Form** (`/book/`) — Primary channel
   - 4-step progressive flow
   - Captures: Name, email, phone, pickup/dropoff, date/time, passengers, luggage, vehicle
   - Stores to `bookings` table in Supabase
   - Triggers email to customer + admin
   - Generates WhatsApp confirmation message

2. **Quote Request Form** — Simpler inquiry form
   - Stores to `quote_requests` table
   - Admin processes and sends pricing back

3. **Contact Form** (`/contact-us/`) — General inquiries
   - Rate limited: 5 requests/IP/hour
   - Email only (no database storage)

4. **Sticky WhatsApp CTA** — Always visible on mobile
   - Direct link to `wa.me/966562471583`

### Lead Flow
```
Visitor → Form → Validation → Supabase → Email (admin + customer) →
WhatsApp confirmation → Admin Dashboard → Quote Processing
```

---

## Fleet & Pricing

| Vehicle | Passengers | Luggage | SAR/km | SAR/hour | Base Price |
|---------|-----------|---------|--------|---------|-----------|
| Business Sedan (Toyota Camry-class) | 3 | 2 | 3.50 | 100 | 150 |
| Family SUV (GMC Yukon-class) | 7 | 5 | 5.00 | 200 | 250 |
| Luxury Van (Hyundai Staria-class) | 7 | 7 | 6.00 | 250 | 300 |

---

## Contact Configuration

```
Phone: +966 56 247 1583
WhatsApp: 966562471583
Booking Email: booking@noorhatransport.com
Info Email: info@noorhatransport.com
Address: 2326 Al Awamiya Street, Ath Thuraya District, Al Qatif, Eastern Province 32645
Hours: 24/7
```

**Config file**: `src/config/contact.ts` — single source of truth for all contact info.

---

## Database Schema (Supabase)

### `bookings` table
Key fields: `customer_name`, `customer_email`, `customer_phone`, `service_type`, `trip_type`, `vehicle_type`, `pickup_location`, `dropoff_location`, `pickup_date`, `pickup_time`, `passengers`, `luggage`, `status`, `booking_source`, `total_price`

**Status values**: `requested` → `quoted` → `confirmed` → `partially_completed` → `completed` | `cancelled` | `rejected`

**Booking ID format**: `NTC-B-{id}`

### `booking_legs` table
One-to-many with bookings. Handles multi-leg journeys.

### `quote_requests` table
Key fields: `first_name`, `last_name`, `email`, `phone`, `service_type`, `pickup_location`, `dropoff_location`, `message`, `status`, `quoted_price`

### `posts` table (Blog)
Key fields: `title`, `slug`, `excerpt`, `content` (HTML), `image_url`, `author_name`, `category_id`, `published`, `published_at`

### `categories` table
For blog categorization.

---

## Integrations

### WhatsApp
- Method: `wa.me` links (no API needed)
- Business number: `966562471583`
- Pre-formatted booking confirmation messages generated automatically
- Admin can click one button to send WhatsApp from dashboard

### Email (Resend)
- Booking confirmation (customer + admin)
- Quote request confirmation
- Contact form auto-response
- Quote price notification (when admin sends price)
- Templates in: `src/lib/email-templates.ts`

### Google Maps
- Places Autocomplete (restricted to KSA + Bahrain)
- Directions API (route visualization in booking form)
- API key: `NEXT_PUBLIC_GOOGLE_MAPS_API_KEY`

### Analytics
- **GA4**: Custom events for full booking funnel, UTM persistence
- **Microsoft Clarity** (ID: `vf2hecs5th`): Heatmaps, session recording
- **Vercel Analytics**: Web vitals, performance

---

## SEO Setup

### Schema Markup
- `TaxiService` schema
- `LocalBusiness` + `TransportationBusiness`
- `Organization` with social links
- `FAQ` schema on homepage
- Coordinates: 26.5600°N, 49.9900°E

### Root Metadata
- **Title**: "Transportation Service in Saudi Arabia | Noorha Transport"
- **Keywords**: transportation service saudi arabia, taxi dammam, taxi khobar, taxi jubail, bahrain taxi, noorha transport
- **OG Image**: 1200x630

### Target Keywords (from project plan)
- "Taxi Bahrain to Dammam"
- "Aramco contractor transportation"
- "Airport transfer Dammam"
- "VIP transport Saudi Arabia"

### Technical SEO
- Trailing slashes on all URLs
- Dynamic XML sitemap (`sitemap.ts`)
- Dynamic robots.txt (`robots.ts`)
- Canonical tags (self-referential)
- Breadcrumb navigation
- Image alt text throughout

---

## Brand Identity

### Colors
- **Primary (Vermilion)**: `#2563EB` (blue-based)
  - Darker: `#1d4ed8`, Lighter: `#3b82f6`
- **Secondary**: Black `#111111`
- **Background**: White
- **Admin theme**: Zinc dark palette (zinc-900/800/700)

### Typography
- **Font**: Montserrat (Google Fonts)
- **CSS Variable**: `--font-montserrat`
- **Heading weight**: 700 bold, letter-spacing -0.02em

### Tailwind CSS Classes
- `.text-vermilion` — primary color text
- `.bg-vermilion` — primary color background
- `.btn-gradient` — gradient button
- `.btn-primary` — primary button
- `.gradient-text` — text gradient

---

## Live Website — What Visitors See

### Hero
- **Headline**: "Transportation Service in Saudi Arabia"
- **Tagline**: "Reliable transfers from Dammam, Khobar & Jubail. Professional drivers & comfortable fleet."
- **CTAs**: WhatsApp button + "Book a Ride"

### Stats (Homepage)
- 500+ happy riders
- 15+ professional drivers
- 30+ routes

### 6 Value Propositions
1. Safe & Secure
2. On Time Service
3. Best Prices
4. All Over KSA
5. Luxury Fleet
6. Expert Support

### 4-Step Process Shown to Visitors
Book via web → Get matched with driver → Enjoy ride → Arrive safely

### Testimonials
9 customer reviews on the homepage

### Social Media
Facebook, Instagram, Twitter, LinkedIn accounts linked in footer

---

## Admin Dashboard KPIs

- Today's Trips (confirmed + completed)
- Requests to Quote (pending pipeline)
- Estimated Revenue (SAR total from completed legs)
- Total Requests (all statuses)
- Upcoming schedule: next 5 confirmed trips

---

## Missing / Future Phase Features

| Feature | Priority |
|---------|---------|
| Arabic language support | High — Saudi audience |
| Payment integration (Moyasar/Stripe) | High — removes friction |
| Advanced financial reporting | Medium |
| SMS fallback (beyond WhatsApp) | Medium |
| Driver app | Low |
| Customer booking cancellation | Low |
| Automatic invoice generation | Low |

---

## File Structure (Key Paths)

```
src/
├── app/                    # All pages (37 public + 9 admin)
├── components/
│   ├── layout/             # Navbar, Footer, StickyMobileCTA
│   ├── marketing/          # Hero, Services, Stats, Testimonials
│   ├── booking/            # BookingFormSimple, BookingSteps
│   ├── forms/              # ContactForm
│   ├── services/           # Service listings, areas, types
│   ├── admin/              # TiptapEditor, NewRequestDrawer
│   └── analytics/          # UTM tracking
├── config/
│   ├── contact.ts          # Phone, email, WhatsApp (single source)
│   └── vehicles.ts         # Fleet configuration & pricing
├── lib/
│   ├── supabase.ts         # DB client
│   ├── email.ts            # Resend service
│   ├── email-templates.ts  # HTML email templates
│   ├── validation.ts       # Zod schemas
│   ├── analytics.ts        # GA4 events
│   ├── whatsapp-booking-confirmation.ts
│   ├── booking-status.ts   # Status enums
│   ├── booking-legs.ts     # Multi-leg logic
│   ├── booking-lifecycle.ts
│   ├── rate-limit.ts       # API rate limiting
│   └── structured-data.ts  # Schema markup
├── types/
│   └── database.ts         # Supabase interfaces
└── middleware.ts            # Auth protection
```

---

## Environment Variables (Production)

```
NEXT_PUBLIC_SUPABASE_URL=https://obtshqtkyzdxtjjlalpn.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=[in Vercel]
RESEND_API_KEY=[in Vercel]
NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=[in Vercel]
ADMIN_USERNAME=noorhatransportbooking@gmail.com
ADMIN_PASSWORD=[secured in Vercel]
NEXT_PUBLIC_GA_MEASUREMENT_ID=[in Vercel]
```

---

**Overall Assessment**: Production-ready, well-architected, ~85% complete. Core booking and lead capture fully operational.
