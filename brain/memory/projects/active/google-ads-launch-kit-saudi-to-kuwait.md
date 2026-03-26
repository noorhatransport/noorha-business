# Google Ads Launch Kit — Saudi Arabia to Kuwait
**Status**: Ready to Launch
**Date**: March 8, 2026
**Budget**: SAR 3,000–5,000/month
**Goal**: WhatsApp leads at SAR 5–15 CPA
**Conversion event**: `whatsapp_click` (fired by Navbar, Footer, StickyMobileCTA on all pages)

---

## Tracking Audit

| Check | Status | Notes |
|-------|--------|-------|
| GA4 fires on Kuwait pages | PASS | `service_page_view` via `PageAnalytics` on all 4 pages |
| `whatsapp_click` fires | PASS | Fires from StickyMobileCTA, Navbar, Footer — present on all pages |
| UTM capture | PASS | `captureUTM()` stores params in sessionStorage, appended to conversion events |
| GA4 Measurement ID | PASS | `G-66YWZ8TF3Q` in Vercel env |

**No tracking fixes needed.** `whatsapp_click` fires from layout components on every page visit.

---

## Campaign Structure

```
Campaign: KWT-Routes [Search]
├── Ad Group 1: Dammam-to-Kuwait       [60% budget — SAR 1,800–3,000/mo]
├── Ad Group 2: Riyadh-to-Kuwait       [15% budget — SAR 450–750/mo]
├── Ad Group 3: Khobar-to-Kuwait       [10% budget — SAR 300–500/mo]
├── Ad Group 4: Saudi-to-Kuwait-Generic [5% budget — SAR 150–250/mo]
└── Ad Group 5: Flight-Alternative     [10% budget — SAR 300–500/mo]
```

**Network**: Search only (no Display, no Search Partners initially)
**Devices**: All, with +20% mobile bid adjustment
**Location**: Saudi Arabia + Kuwait (people IN or INTERESTED in these locations)
**Language**: English + Arabic
**Start date**: Immediately
**Bid strategy**: Manual CPC → switch to Target CPA after 50 conversions

---

## Ad Group 1: Dammam to Kuwait

### Keywords (Exact + Phrase match)
```
[dammam to kuwait taxi]
[taxi from dammam to kuwait]
[dammam to kuwait by car]
[dammam kuwait transport]
[private car dammam to kuwait]
[dammam to kuwait transfer]
[dammam kuwait private driver]
"dammam to kuwait taxi"
"dammam to kuwait transfer"
"dammam kuwait transport"
"private car dammam kuwait"
```

### RSA Ad — Dammam to Kuwait
**Final URL**: `https://noorhatransport.com/services/dammam-to-kuwait-taxi?utm_source=google&utm_medium=cpc&utm_campaign=kwt-routes&utm_content=dammam-kwt&utm_term={keyword}`

**Headlines** (pin H1 = route, H2 = urgency, rest unpinned):
| # | Headline | Chars |
|---|----------|-------|
| H1 | Dammam to Kuwait Taxi | 21 |
| H2 | Flights Suspended? We Run | 25 |
| H3 | Door-to-Door in 4-5 Hours | 25 |
| H4 | First Class SAR 4,500 | 21 |
| H5 | Economy from SAR 3,500 | 22 |
| H6 | Private Car. Fixed Price. | 25 |
| H7 | Khafji Border Handled | 21 |
| H8 | Book via WhatsApp Today | 23 |
| H9 | Cadillac Escalade or Sedan | 26 |
| H10 | Eastern Province Specialists | 28 |
| H11 | 20+ Years Cross-Border | 22 |
| H12 | Available Today or Tomorrow | 27 |
| H13 | No Hidden Fees, Fixed Rate | 26 |
| H14 | Family Vehicles Available | 25 |
| H15 | WhatsApp Quote in 2 Minutes | 27 |

**Descriptions**:
| # | Description | Chars |
|---|-------------|-------|
| D1 | Flights cancelled? Noorha Transport runs daily Dammam-Kuwait private transfers. Khafji border handled. | 99 |
| D2 | First Class (SAR 4,500) or Economy (SAR 3,500). Cadillac Escalade or Toyota sedan. Book on WhatsApp. | 99 |
| D3 | Professional cross-border driver from Dammam, Khobar, or Jubail. Fixed rate includes all border fees. | 99 |
| D4 | 4-5 hours direct, door-to-door. 20+ years on this route. WhatsApp for instant quote and same-day booking. | 104 |

> Note: D1, D2, D3 are 99 chars — trim if Google rejects (limit is 90). Shortened versions below:
> - D1 short: `Flights cancelled? Noorha runs daily Dammam-Kuwait transfers. Khafji border handled.` (83)
> - D2 short: `First Class SAR 4,500 or Economy SAR 3,500. Cadillac or Toyota. Book on WhatsApp.` (81)
> - D3 short: `Fixed-rate private transfer from Dammam, Khobar, or Jubail. All border fees included.` (84)
> - D4 short: `4-5 hours direct, door-to-door. 20+ years on this route. WhatsApp for same-day booking.` (88)

---

## Ad Group 2: Riyadh to Kuwait

### Keywords
```
[riyadh to kuwait taxi]
[riyadh to kuwait by car]
[riyadh to kuwait transport]
[private car riyadh to kuwait]
[taxi riyadh kuwait city]
"riyadh to kuwait taxi"
"riyadh kuwait private transfer"
"riyadh to kuwait by road"
```

### RSA Ad — Riyadh to Kuwait
**Final URL**: `https://noorhatransport.com/services/riyadh-to-kuwait-taxi?utm_source=google&utm_medium=cpc&utm_campaign=kwt-routes&utm_content=riyadh-kwt&utm_term={keyword}`

**Headlines**:
| # | Headline | Chars |
|---|----------|-------|
| H1 | Riyadh to Kuwait Taxi | 21 |
| H2 | Flights Suspended? Road Open | 28 |
| H3 | Direct in 7-8 Hours | 19 |
| H4 | First Class SAR 7,000 | 21 |
| H5 | Economy from SAR 3,500 | 22 |
| H6 | Private Door-to-Door Car | 24 |
| H7 | Khafji Border Handled | 21 |
| H8 | Book via WhatsApp Now | 21 |
| H9 | Cadillac Escalade or Sedan | 26 |
| H10 | Licensed Cross-Border Driver | 28 |
| H11 | Riyadh Pickup Available | 23 |
| H12 | Fixed Rate, No Surprises | 24 |
| H13 | Family Vehicles Available | 25 |
| H14 | Same-Day Departures | 19 |
| H15 | WhatsApp Quote in 2 Minutes | 27 |

**Descriptions**:
| # | Description | Chars |
|---|-------------|-------|
| D1 | Flights grounded between KSA and Kuwait? Noorha Transport runs Riyadh-Kuwait transfers daily. | 91 |
| D2 | First Class SAR 7,000 or Economy SAR 3,500. Pickup from Riyadh. Door-to-door to Kuwait City. | 91 |
| D3 | Licensed cross-border drivers with Khafji border expertise. Fixed rate, no hidden fees. | 87 |
| D4 | 7-8 hours direct. Cadillac Escalade or sedan. WhatsApp us for instant quote and booking. | 88 |

---

## Ad Group 3: Khobar to Kuwait

### Keywords
```
[khobar to kuwait taxi]
[al khobar to kuwait by car]
[khobar kuwait taxi service]
[khobar to kuwait transfer]
[khobar kuwait private driver]
"khobar to kuwait taxi"
"khobar to kuwait transfer"
"al khobar kuwait transport"
```

### RSA Ad — Khobar to Kuwait
**Final URL**: `https://noorhatransport.com/services/khobar-to-kuwait-taxi?utm_source=google&utm_medium=cpc&utm_campaign=kwt-routes&utm_content=khobar-kwt&utm_term={keyword}`

**Headlines**:
| # | Headline | Chars |
|---|----------|-------|
| H1 | Khobar to Kuwait Taxi | 21 |
| H2 | Flights Suspended? We Run | 25 |
| H3 | Door-to-Door in 4-5 Hours | 25 |
| H4 | First Class SAR 4,500 | 21 |
| H5 | Economy from SAR 3,500 | 22 |
| H6 | Al Khobar Pickup Available | 26 |
| H7 | Khafji Border Handled | 21 |
| H8 | Book via WhatsApp Now | 21 |
| H9 | Cadillac Escalade or Sedan | 26 |
| H10 | Eastern Province Experts | 24 |
| H11 | Fixed Price, No Surprises | 25 |
| H12 | Available Today | 15 |
| H13 | 20+ Years on This Route | 23 |
| H14 | Family Vehicles Available | 25 |
| H15 | WhatsApp Quote in 2 Minutes | 27 |

**Descriptions**:
| # | Description | Chars |
|---|-------------|-------|
| D1 | Flights cancelled? Noorha Transport runs daily Khobar-Kuwait private transfers via Khafji. | 90 |
| D2 | First Class SAR 4,500 or Economy SAR 3,500. Cadillac or Toyota. Book on WhatsApp instantly. | 91 |
| D3 | Pickup from Al Khobar. Fixed rate includes Khafji border crossing. No hidden fees. | 82 |
| D4 | 4-5 hours direct to Kuwait City. Family vehicles. WhatsApp for same-day booking. | 80 |

> D2 is 91 chars — trim: `First Class SAR 4,500 or Economy SAR 3,500. Cadillac or Toyota sedan. Book via WhatsApp.` (88)

---

## Ad Group 4: Saudi to Kuwait Generic

### Keywords
```
[saudi to kuwait taxi]
[saudi arabia to kuwait by car]
[ksa to kuwait transport]
[saudi kuwait private transfer]
[cross border taxi saudi kuwait]
"saudi to kuwait taxi"
"saudi arabia to kuwait"
"ksa kuwait transfer"
"travel saudi to kuwait"
```

### RSA Ad — Saudi to Kuwait
**Final URL**: `https://noorhatransport.com/services/saudi-to-kuwait-taxi?utm_source=google&utm_medium=cpc&utm_campaign=kwt-routes&utm_content=saudi-kwt-generic&utm_term={keyword}`

**Headlines**:
| # | Headline | Chars |
|---|----------|-------|
| H1 | Saudi to Kuwait Private Taxi | 28 |
| H2 | Flights Suspended? Road Open | 28 |
| H3 | From Dammam, Khobar, Riyadh | 27 |
| H4 | First Class or Economy | 22 |
| H5 | From SAR 3,500 All-In | 21 |
| H6 | Khafji Border Specialists | 25 |
| H7 | Book via WhatsApp Today | 23 |
| H8 | Cadillac or Economy Sedan | 25 |
| H9 | Door-to-Door Service | 20 |
| H10 | Fixed Rate, No Hidden Fees | 26 |
| H11 | Licensed Cross-Border Driver | 28 |
| H12 | Eastern Province Based | 22 |
| H13 | 20+ Years Cross-Border | 22 |
| H14 | Same-Day Departures | 19 |
| H15 | WhatsApp Quote in 2 Minutes | 27 |

**Descriptions**:
| # | Description | Chars |
|---|-------------|-------|
| D1 | Noorha Transport runs daily private car transfers from Saudi Arabia to Kuwait City. | 83 |
| D2 | Pickup from Dammam, Khobar, Jubail, or Riyadh. Economy SAR 3,500. First Class from SAR 4,500. | 92 |
| D3 | Khafji-Nuwaiseeb border handled by licensed drivers. Fixed rate, no surprises. | 78 |
| D4 | Flights grounded? Road transfers available daily. WhatsApp us for instant quote and booking. | 91 |

> D2 trim: `Dammam, Khobar, Jubail, or Riyadh pickup. Economy SAR 3,500. First Class from SAR 4,500.` (88)
> D4 trim: `Flights grounded? Road transfers available daily. WhatsApp for instant quote and booking.` (89)

---

## Ad Group 5: Flight Alternative (Highest Intent)

### Keywords
```
[saudi to kuwait flights cancelled]
[saudi kuwait flights suspended]
[how to travel to kuwait from saudi]
[alternative to flying saudi to kuwait]
[saudi to kuwait by road]
[kuwait flights from dammam cancelled]
[saudi kuwait airspace closed]
"saudi kuwait flights cancelled"
"dammam kuwait flights suspended"
"how to get to kuwait without flying"
"saudi arabia kuwait land transfer"
"road trip saudi to kuwait"
```

### RSA Ad — Flight Alternative
**Final URL**: `https://noorhatransport.com/services/saudi-to-kuwait-taxi?utm_source=google&utm_medium=cpc&utm_campaign=kwt-routes&utm_content=flight-alt&utm_term={keyword}`

**Headlines**:
| # | Headline | Chars |
|---|----------|-------|
| H1 | Saudi-Kuwait Flights Cancelled? | 30 |
| H2 | Travel by Road — We're Running | 30 |
| H3 | Dammam to Kuwait in ~5 Hours | 28 |
| H4 | Road Is Open. Seats Available | 29 |
| H5 | From SAR 3,500 All-In | 21 |
| H6 | Book for Today or Tomorrow | 26 |
| H7 | Khafji Border Specialists | 25 |
| H8 | First Class or Economy | 22 |
| H9 | Door-to-Door Private Transfer | 29 |
| H10 | WhatsApp — Reply in Minutes | 27 |
| H11 | Only Land Option Running | 24 |
| H12 | Cadillac or Economy Sedan | 25 |
| H13 | No Flights? No Problem. | 23 |
| H14 | 20+ Years on This Route | 23 |
| H15 | Eastern Province Specialists | 28 |

**Descriptions**:
| # | Description | Chars |
|---|-------------|-------|
| D1 | Air traffic between Saudi and Kuwait is suspended. Noorha Transport runs road transfers daily. | 92 |
| D2 | First Class SAR 4,500 (Dammam) or SAR 7,000 (Riyadh). Economy SAR 3,500 all routes. | 84 |
| D3 | Khafji-Nuwaiseeb border handled by licensed drivers. Pickup from any Eastern Province city. | 90 |
| D4 | Don't get stranded. WhatsApp us now — depart today or tomorrow. Fixed price guaranteed. | 87 |

> D1 trim: `Flights between Saudi and Kuwait suspended. Noorha Transport runs daily road transfers.` (87)

---

## UTM-Tagged Destination URLs (Copy-Paste Ready)

| Ad Group | Landing Page URL with UTM |
|----------|--------------------------|
| Dammam → Kuwait | `https://noorhatransport.com/services/dammam-to-kuwait-taxi?utm_source=google&utm_medium=cpc&utm_campaign=kwt-routes&utm_content=dammam-kwt&utm_term={keyword}` |
| Riyadh → Kuwait | `https://noorhatransport.com/services/riyadh-to-kuwait-taxi?utm_source=google&utm_medium=cpc&utm_campaign=kwt-routes&utm_content=riyadh-kwt&utm_term={keyword}` |
| Khobar → Kuwait | `https://noorhatransport.com/services/khobar-to-kuwait-taxi?utm_source=google&utm_medium=cpc&utm_campaign=kwt-routes&utm_content=khobar-kwt&utm_term={keyword}` |
| Saudi → Kuwait Hub | `https://noorhatransport.com/services/saudi-to-kuwait-taxi?utm_source=google&utm_medium=cpc&utm_campaign=kwt-routes&utm_content=saudi-kwt-generic&utm_term={keyword}` |
| Flight Alternative | `https://noorhatransport.com/services/saudi-to-kuwait-taxi?utm_source=google&utm_medium=cpc&utm_campaign=kwt-routes&utm_content=flight-alt&utm_term={keyword}` |

> `{keyword}` is Google's ValueTrack parameter — automatically replaced with the search term that triggered the ad.

---

## Negative Keywords (Campaign Level)

Add these to prevent wasted spend:

```
jobs
hiring
driver job
salary
how much does a driver earn
bus
public bus
saptco
train
flight booking
book flight
cheap flights
airline ticket
kuwait airways
flynas
saudia airlines
flydubai
bahrain
dubai
oman
jordan
egypt
hotel
accommodation
visa apply
tourist visa
embassy
map
google maps
directions
free
cheap
rental car
rent a car
self drive
```

---

## GA4 → Google Ads Conversion Import (Step-by-Step)

### Step 1: Link GA4 to Google Ads
1. In Google Ads → **Tools & Settings** → **Linked accounts** → **Google Analytics**
2. Click **Details** next to your GA4 property → **Link**
3. Enable **Enable Google Signals** (for remarketing later)

### Step 2: Import `whatsapp_click` as Conversion
1. In Google Ads → **Tools & Settings** → **Conversions**
2. Click **+ New conversion action**
3. Select **Import** → **Google Analytics 4 properties** → **Continue**
4. Find `whatsapp_click` in the list → check the box → **Import and continue**
5. Settings:
   - **Category**: Lead
   - **Value**: SAR 10 (mid-point of your SAR 5–15 target — update after data)
   - **Count**: Every (each WhatsApp click counts)
   - **Conversion window**: 30 days
   - **Attribution**: Data-driven (or Last click if insufficient data)

### Step 3: Mark as Primary Conversion
- Set `whatsapp_click` as **Primary** conversion action (used for Smart Bidding)
- Set `service_page_view` as **Secondary** (observation only)

### Step 4: Verify Tracking is Live
- Go to a Kuwait landing page with `?utm_source=google&utm_medium=cpc` appended
- Click a WhatsApp link (Navbar or Footer)
- In GA4 → **Realtime** → confirm `whatsapp_click` appears
- In Google Ads → **Conversions** → status should show "Recording" within 24 hrs

---

## Bid Settings

| Setting | Value |
|---------|-------|
| Bid strategy (launch) | Manual CPC |
| Max CPC (Dammam group) | SAR 3.00 |
| Max CPC (Riyadh group) | SAR 3.50 |
| Max CPC (Khobar group) | SAR 2.50 |
| Max CPC (Generic group) | SAR 2.00 |
| Max CPC (Flight-alt group) | SAR 4.00 |
| Mobile bid adjustment | +20% |
| Switch to Target CPA when | 50+ conversions recorded |
| Target CPA (after switch) | SAR 10 |

---

## Budget Phasing

| Phase | When | Daily Budget |
|-------|------|-------------|
| Launch — max spend | Week 1–2 (flights still suspended) | SAR 167/day (~SAR 5,000/mo) |
| Normalize | Week 3+ | SAR 100–133/day (~SAR 3,000–4,000/mo) |
| Scale winning groups | After 50 conversions | Increase winners 20–30% |

**Launch with SAR 5,000/mo budget** — flights are still suspended and demand is peaking now. Pull back to 3,000 once situation normalizes.

---

## Campaign Naming Convention

```
Campaign:  GOOG_Search_KWT-Routes_WhatsApp_Mar26
Ad Group 1: DAM-to-KWT_Exact+Phrase
Ad Group 2: RYD-to-KWT_Exact+Phrase
Ad Group 3: KHO-to-KWT_Exact+Phrase
Ad Group 4: KSA-KWT-Generic_Exact+Phrase
Ad Group 5: Flight-Alternative_Exact+Phrase
```

---

## Launch Checklist

- [ ] GA4 linked to Google Ads account
- [ ] `whatsapp_click` imported as primary conversion (value: SAR 10)
- [ ] Campaign created: `GOOG_Search_KWT-Routes_WhatsApp_Mar26`
- [ ] All 5 ad groups created with keywords above
- [ ] RSA ads created in each group (min 3 headlines pinned: H1, H2, H3)
- [ ] UTM-tagged final URLs set in each ad group
- [ ] Negative keyword list added at campaign level
- [ ] Mobile bid adjustment +20% set
- [ ] Search Network only (no Display partners)
- [ ] Location: Saudi Arabia + Kuwait
- [ ] Language: English + Arabic
- [ ] Daily budget: SAR 167/day (SAR 5,000/mo)
- [ ] Manual CPC bids set per group (see table above)
- [ ] Verify: visit a page → click WhatsApp → confirm GA4 Realtime shows `whatsapp_click`
- [ ] Campaign goes live
