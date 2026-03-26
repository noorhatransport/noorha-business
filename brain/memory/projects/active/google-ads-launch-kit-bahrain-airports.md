# Google Ads Launch Kit — Bahrain Airport Transfers (FINAL)
**Status**: Ready to Launch
**Updated**: March 13, 2026
**Campaign**: `GOOG_Search_BHR-Airport_WhatsApp_Mar26`
**Budget**: SAR 3,000–5,000/month
**Goal**: WhatsApp leads at SAR 5–10 CPA
**Conversion event**: `whatsapp_click` (fires from Navbar, Footer, StickyMobileCTA on all pages)
**Messaging angle**: Sell the TRANSPORT, not the airport. Customers already know where they're flying from.

---

## Tracking Audit

| Check | Status | Notes |
|-------|--------|-------|
| GA4 fires on Bahrain airport pages | PASS | `service_page_view` via `PageAnalytics` on all 3 pages |
| `whatsapp_click` fires | PASS | Fires from StickyMobileCTA, Navbar, Footer on all pages |
| UTM capture | PASS | `captureUTM()` stores params in sessionStorage, appended to conversion events |
| GA4 Measurement ID | PASS | `G-66YWZ8TF3Q` in Vercel env |

**No tracking fixes needed.** `whatsapp_click` fires from layout components on every page visit.

---

## Campaign Structure

```
Campaign: GOOG_Search_BHR-Airport_WhatsApp_Mar26
├── Ad Group 1: BHR-to-DMM              [40% budget]
├── Ad Group 2: BHR-to-RUH              [15% budget]
├── Ad Group 3: DMM-to-BHR (reverse)    [10% budget]
├── Ad Group 4: RUH-to-BHR (reverse)    [5% budget]
├── Ad Group 5: Flight-Alternative       [20% budget]  ← HIGHEST INTENT
└── Ad Group 6: Generic-BHR-Airport      [10% budget]
```

**Network**: Search only (no Display, no Search Partners)
**Devices**: All, with +25% mobile bid adjustment
**Location**: Bahrain + Saudi Arabia (Eastern Province + Riyadh Region)
**Language**: English + Arabic
**Start date**: Immediately
**Bid strategy**: Manual CPC → switch to Target CPA after 50 conversions
**Ad schedule**: All day (24/7 — travelers book at all hours, flights depart early morning)

---

## Ad Extensions (Campaign Level)

### Sitelink Extensions
| Sitelink | Final URL | Description Line 1 | Description Line 2 |
|----------|-----------|--------------------|--------------------|
| Dammam Airport Taxi | /services/bahrain-to-dammam-airport-taxi | Fixed SAR 650 Economy | Just 2 hours from Bahrain |
| Riyadh Airport Taxi | /services/bahrain-to-riyadh-airport-taxi | Fixed SAR 1,700 Economy | Door to terminal service |
| Book Online | /book | Easy online booking | Instant confirmation |
| WhatsApp Us | wa.me/966562471583 | Get a quote in 2 minutes | Available 24/7 |

### Callout Extensions
- Fixed Pricing
- Embassy Recommended
- 20+ Years Experience
- No Hidden Fees
- Both Directions
- Causeway Experts
- Economy & Executive SUVs
- Same-Day Booking

### Structured Snippet Extensions
| Header | Values |
|--------|--------|
| Types | Economy SUV, Executive SUV |
| Destinations | Dammam Airport (DMM), Riyadh Airport (RUH) |
| Brands | Toyota Sequoia, Toyota Prado, GMC Yukon, Chevrolet Tahoe |

### Call Extension
- Phone: +966 56 247 1583
- Show during: All hours

### Location Extension (if applicable)
- Link Google Business Profile if available

---

## Ad Group 1: Bahrain to Dammam Airport [40% budget]

### Keywords (Exact + Phrase match)
```
-- EXACT MATCH --
[bahrain to dammam airport taxi]
[taxi from bahrain to dammam airport]
[bahrain to dmm airport transfer]
[bahrain to dammam airport by car]
[bahrain dammam airport transport]
[king fahd causeway to dammam airport]
[manama to dammam airport taxi]
[bahrain to dmm taxi]
[taxi bahrain dammam airport]
[bahrain airport transfer dammam]
[bahrain to king fahd airport taxi]
[ride from bahrain to dammam airport]
[car from bahrain to dammam airport]
[bahrain to dammam airport drop]
[private car bahrain to dammam airport]
[bahrain to dammam airport service]

-- PHRASE MATCH --
"bahrain to dammam airport taxi"
"bahrain dammam airport transfer"
"manama to dammam airport"
"bahrain to dmm taxi"
"taxi from bahrain to dammam"
"bahrain causeway dammam airport"
"bahrain to dammam airport"
"ride to dammam airport from bahrain"
"car to dammam airport from bahrain"
"bahrain to king fahd airport"
```

### RSA Ad — Bahrain to Dammam Airport
**Final URL**: `https://noorhatransport.com/services/bahrain-to-dammam-airport-taxi?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=bhr-dmm&utm_term={keyword}`

**Headlines** (pin H1 to position 1, H2 to position 2):
| # | Pin | Headline | Chars |
|---|-----|----------|-------|
| H1 | Pos 1 | Bahrain to Dammam Airport Taxi | 30 |
| H2 | Pos 2 | Fixed SAR 650. Door to Terminal | 30 |
| H3 | - | We Pick You Up From Bahrain | 27 |
| H4 | - | Executive SUV SAR 800 | 21 |
| H5 | - | Embassy Recommended Service | 27 |
| H6 | - | King Fahd Causeway Experts | 26 |
| H7 | - | No Overcharging. Fair Price | 27 |
| H8 | - | Book via WhatsApp Today | 23 |
| H9 | - | GMC Yukon or Toyota Sequoia | 27 |
| H10 | - | At Your Terminal in ~2 Hours | 28 |
| H11 | - | 20+ Years Cross-Border | 22 |
| H12 | - | Available Today or Tomorrow | 27 |
| H13 | - | Trusted by European Embassies | 30 |
| H14 | - | We Handle the Causeway | 22 |
| H15 | - | WhatsApp Quote in 2 Minutes | 27 |

**Descriptions** (under 90 chars):
| # | Description | Chars |
|---|-------------|-------|
| D1 | Got a flight from DMM? We pick you up from Bahrain and drive you to your terminal. | 82 |
| D2 | Economy SUV SAR 650 or Executive GMC Yukon SAR 800. No surprises. Embassy recommended. | 87 |
| D3 | We handle the causeway crossing. Door-to-terminal in about 2 hours. Book on WhatsApp. | 86 |
| D4 | Fair fixed pricing while others overcharge. No hidden fees. Same-day booking available. | 87 |

---

## Ad Group 2: Bahrain to Riyadh Airport [15% budget]

### Keywords (Exact + Phrase match)
```
-- EXACT MATCH --
[bahrain to riyadh airport taxi]
[taxi from bahrain to riyadh airport]
[bahrain to ruh airport transfer]
[bahrain to riyadh airport by car]
[manama to riyadh airport taxi]
[bahrain to riyadh airport transport]
[bahrain ruh taxi]
[ride from bahrain to riyadh airport]
[car from bahrain to riyadh airport]
[private car bahrain to riyadh airport]
[bahrain to riyadh airport drop]
[bahrain to king khalid airport taxi]
[bahrain to riyadh airport service]

-- PHRASE MATCH --
"bahrain to riyadh airport taxi"
"bahrain riyadh airport transfer"
"manama to riyadh airport"
"bahrain to ruh taxi"
"taxi bahrain riyadh airport"
"ride to riyadh airport from bahrain"
"car to riyadh airport from bahrain"
"bahrain to king khalid airport"
```

### RSA Ad — Bahrain to Riyadh Airport
**Final URL**: `https://noorhatransport.com/services/bahrain-to-riyadh-airport-taxi?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=bhr-ruh&utm_term={keyword}`

**Headlines** (pin H1 to position 1, H2 to position 2):
| # | Pin | Headline | Chars |
|---|-----|----------|-------|
| H1 | Pos 1 | Bahrain to Riyadh Airport Taxi | 30 |
| H2 | Pos 2 | Fixed SAR 1,700. Door to RUH | 28 |
| H3 | - | We Drive You to Your Flight | 27 |
| H4 | - | Executive SUV SAR 2,500 | 23 |
| H5 | - | Embassy Recommended Service | 27 |
| H6 | - | Causeway + Highway Handled | 27 |
| H7 | - | No Overcharging. Fixed Rate | 27 |
| H8 | - | Book via WhatsApp Now | 21 |
| H9 | - | GMC Yukon or Toyota Sequoia | 27 |
| H10 | - | Straight to Your Terminal | 25 |
| H11 | - | 20+ Years Cross-Border | 22 |
| H12 | - | We Pick You Up From Bahrain | 27 |
| H13 | - | Trusted by Embassies | 20 |
| H14 | - | Causeway + Highway Experts | 26 |
| H15 | - | WhatsApp Quote in 2 Minutes | 27 |

**Descriptions** (under 90 chars):
| # | Description | Chars |
|---|-------------|-------|
| D1 | Got a flight from Riyadh Airport? We pick you up from Bahrain. Fixed SAR 1,700. | 80 |
| D2 | Economy SUV SAR 1,700 or Executive SAR 2,500. Fair pricing. Embassy recommended. | 81 |
| D3 | We handle the causeway and full highway drive. Straight to your terminal at RUH. | 81 |
| D4 | Fixed price covers everything. No hidden fees. WhatsApp us for same-day booking. | 80 |

---

## Ad Group 3: Dammam Airport to Bahrain (Reverse) [10% budget]

### Keywords
```
-- EXACT MATCH --
[dammam airport to bahrain taxi]
[dmm to bahrain transfer]
[dammam airport to manama taxi]
[taxi from dammam airport to bahrain]
[dammam airport bahrain causeway taxi]
[pickup from dammam airport to bahrain]
[dammam airport to bahrain car]
[dmm airport to manama]
[arriving at dammam airport need taxi to bahrain]

-- PHRASE MATCH --
"dammam airport to bahrain taxi"
"dmm airport bahrain transfer"
"dammam airport to manama"
"taxi from dammam airport to bahrain"
"pickup from dammam airport"
"dammam airport to bahrain"
```

### RSA Ad — DMM to Bahrain
**Final URL**: `https://noorhatransport.com/services/bahrain-to-dammam-airport-taxi?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=dmm-bhr&utm_term={keyword}`

**Headlines** (pin H1 to position 1, H2 to position 2):
| # | Pin | Headline | Chars |
|---|-----|----------|-------|
| H1 | Pos 1 | Dammam Airport to Bahrain Taxi | 30 |
| H2 | Pos 2 | We Meet You at DMM Terminal | 27 |
| H3 | - | Fixed Price SAR 650 Economy | 27 |
| H4 | - | Executive SUV SAR 800 | 21 |
| H5 | - | Causeway Crossing Handled | 25 |
| H6 | - | In Bahrain in About 2 Hours | 28 |
| H7 | - | No Surge Pricing | 17 |
| H8 | - | Book via WhatsApp Now | 21 |
| H9 | - | Embassy Recommended | 19 |
| H10 | - | 20+ Years Causeway Experience | 30 |
| H11 | - | Available 24/7 | 14 |
| H12 | - | Meet and Greet at Terminal | 26 |
| H13 | - | Trusted by European Embassies | 30 |
| H14 | - | GMC Yukon or Toyota Sequoia | 27 |
| H15 | - | Fixed Rate, No Surprises | 24 |

**Descriptions** (under 90 chars):
| # | Description | Chars |
|---|-------------|-------|
| D1 | Landing at Dammam Airport? We meet you at your terminal and drive you to Bahrain. | 82 |
| D2 | Meet and greet at DMM. Economy SAR 650, Executive SAR 800. No hidden fees. | 74 |
| D3 | We handle the causeway crossing. Door-to-door to Manama or anywhere in Bahrain. | 80 |
| D4 | Fixed pricing, no surge. 20+ years Causeway experience. WhatsApp for instant quote. | 84 |

---

## Ad Group 4: Riyadh Airport to Bahrain (Reverse) [5% budget]

### Keywords
```
-- EXACT MATCH --
[riyadh airport to bahrain taxi]
[ruh to bahrain transfer]
[riyadh airport to manama taxi]
[taxi from riyadh airport to bahrain]
[pickup from riyadh airport to bahrain]
[ruh airport to bahrain car]
[arriving at riyadh airport need ride to bahrain]

-- PHRASE MATCH --
"riyadh airport to bahrain taxi"
"ruh airport bahrain transfer"
"riyadh airport to manama"
"taxi from riyadh airport to bahrain"
"pickup from riyadh airport"
```

### RSA Ad — RUH to Bahrain
**Final URL**: `https://noorhatransport.com/services/bahrain-to-riyadh-airport-taxi?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=ruh-bhr&utm_term={keyword}`

**Headlines** (pin H1 to position 1, H2 to position 2):
| # | Pin | Headline | Chars |
|---|-----|----------|-------|
| H1 | Pos 1 | Riyadh Airport to Bahrain Taxi | 30 |
| H2 | Pos 2 | We Meet You at RUH Terminal | 27 |
| H3 | - | Fixed Price SAR 1,700 Economy | 29 |
| H4 | - | Executive SUV SAR 2,500 | 23 |
| H5 | - | Causeway + Highway Handled | 27 |
| H6 | - | Door-to-Door to Bahrain | 23 |
| H7 | - | No Surge Pricing | 17 |
| H8 | - | Book via WhatsApp Now | 21 |
| H9 | - | Embassy Recommended | 19 |
| H10 | - | 20+ Years Experience | 21 |
| H11 | - | Available 24/7 | 14 |
| H12 | - | Meet and Greet at Terminal | 26 |
| H13 | - | Trusted by European Embassies | 30 |
| H14 | - | GMC Yukon or Toyota Sequoia | 27 |
| H15 | - | Fixed Rate, No Surprises | 24 |

**Descriptions** (under 90 chars):
| # | Description | Chars |
|---|-------------|-------|
| D1 | Landing at Riyadh Airport? We meet you at your terminal and drive you to Bahrain. | 82 |
| D2 | Economy SAR 1,700, Executive SAR 2,500. Fixed price. No surprises. Embassy recommended. | 88 |
| D3 | We handle the full highway drive and causeway crossing. Straight to your door. | 79 |
| D4 | Fixed pricing. 20+ years experience. WhatsApp us for instant booking. | 69 |

---

## Ad Group 5: Bahrain Flight Alternative (HIGHEST INTENT) [20% budget]

### Keywords
```
-- EXACT MATCH --
[bahrain flights cancelled]
[bahrain airport closed]
[bahrain flights suspended]
[how to fly from bahrain now]
[alternative to bahrain airport]
[nearest airport to bahrain open]
[can i fly from bahrain]
[bahrain airspace closed]
[where to fly from if bahrain closed]
[bahrain flight alternative]
[bahrain flights closed what to do]
[bahrain airport not working]
[bahrain international airport closed]
[is bahrain airport open]
[bahrain airport status]
[stuck in bahrain need to fly]
[bahrain flights cancelled today]
[bahrain airport news today]
[no flights from bahrain]
[bahrain airport shutdown]

-- PHRASE MATCH --
"bahrain flights cancelled"
"bahrain airport closed"
"how to travel from bahrain"
"alternative airport bahrain"
"nearest open airport to bahrain"
"bahrain flights suspended"
"can I fly from bahrain"
"bahrain flights closed"
"bahrain airport status"
"no flights from bahrain"
"bahrain airport news"
"stuck in bahrain"
```

### RSA Ad — Flight Alternative
**Final URL**: `https://noorhatransport.com/services/bahrain-airport-transfer?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=flight-alt&utm_term={keyword}`

**Headlines** (pin H1 to position 1, H3 to position 2):
| # | Pin | Headline | Chars |
|---|-----|----------|-------|
| H1 | Pos 1 | Bahrain Flights Cancelled? | 26 |
| H2 | - | We Drive You to the Airport | 27 |
| H3 | Pos 2 | Need a Ride? We Can Help | 24 |
| H4 | - | DMM Airport in About 2 Hours | 29 |
| H5 | - | From SAR 650 Fixed Rate | 23 |
| H6 | - | No Overcharging. Fair Prices | 28 |
| H7 | - | Embassy Recommended Service | 27 |
| H8 | - | Book via WhatsApp Now | 21 |
| H9 | - | Causeway Experts Since 2005 | 27 |
| H10 | - | Economy and Executive SUVs | 27 |
| H11 | - | Available Today | 15 |
| H12 | - | King Fahd Causeway Handled | 26 |
| H13 | - | Dammam or Riyadh Airport | 24 |
| H14 | - | Trusted by European Embassies | 30 |
| H15 | - | Same-Day Booking Available | 26 |

**Descriptions** (under 90 chars):
| # | Description | Chars |
|---|-------------|-------|
| D1 | Bahrain airport closed? We drive you to Dammam or Riyadh airport. From SAR 650. | 80 |
| D2 | Fixed prices while others overcharge. DMM SAR 650, RUH SAR 1,700. No hidden fees. | 83 |
| D3 | Recommended by Italian and Spanish embassies. 20+ years Causeway experience. | 78 |
| D4 | Need to catch a flight? Dammam and Riyadh airports are open. Book via WhatsApp now. | 84 |

---

## Ad Group 6: Generic Bahrain Airport Transfer [10% budget]

### Keywords
```
-- EXACT MATCH --
[bahrain airport taxi to saudi]
[bahrain to saudi airport transfer]
[bahrain causeway taxi airport]
[cross border taxi bahrain airport]
[bahrain airport shuttle]
[bahrain to saudi airport]
[bahrain taxi to airport]
[bahrain airport transfer service]
[bahrain cross border taxi]
[taxi across causeway to airport]
[bahrain to saudi taxi airport transfer]

-- PHRASE MATCH --
"bahrain airport transfer"
"bahrain to saudi airport taxi"
"bahrain cross border taxi"
"bahrain to saudi airport"
"bahrain taxi to airport"
"causeway taxi to airport"
"bahrain airport taxi service"
```

### RSA Ad — Generic Bahrain Airport
**Final URL**: `https://noorhatransport.com/services/bahrain-airport-transfer?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=generic&utm_term={keyword}`

**Headlines** (pin H1 to position 1):
| # | Pin | Headline | Chars |
|---|-----|----------|-------|
| H1 | Pos 1 | Bahrain Airport Transfer | 24 |
| H2 | - | Cross-Border Taxi Service | 25 |
| H3 | - | From SAR 650 Fixed Rate | 23 |
| H4 | - | DMM and RUH Airports | 21 |
| H5 | - | Embassy Recommended | 19 |
| H6 | - | King Fahd Causeway Experts | 26 |
| H7 | - | Book via WhatsApp | 17 |
| H8 | - | No Surge Pricing | 17 |
| H9 | - | 20+ Years Cross-Border | 22 |
| H10 | - | GMC Yukon or Toyota Sequoia | 27 |
| H11 | - | Door-to-Terminal Service | 24 |
| H12 | - | Both Directions Available | 25 |
| H13 | - | Available 24/7 | 14 |
| H14 | - | Professional Licensed Drivers | 29 |
| H15 | - | Fixed Rate, No Surprises | 24 |

**Descriptions** (under 90 chars):
| # | Description | Chars |
|---|-------------|-------|
| D1 | Cross-border taxi from Bahrain to Saudi airports. Dammam or Riyadh. From SAR 650. | 82 |
| D2 | Embassy recommended. Fixed pricing. Economy and Executive SUVs. No hidden fees. | 80 |
| D3 | King Fahd Causeway specialists. Door-to-terminal. Both directions available. | 77 |
| D4 | Professional licensed drivers. 20+ years experience. WhatsApp for instant quote. | 81 |

---

## UTM-Tagged Destination URLs (Copy-Paste Ready)

| Ad Group | Landing Page URL with UTM |
|----------|--------------------------|
| BHR→DMM | `https://noorhatransport.com/services/bahrain-to-dammam-airport-taxi?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=bhr-dmm&utm_term={keyword}` |
| BHR→RUH | `https://noorhatransport.com/services/bahrain-to-riyadh-airport-taxi?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=bhr-ruh&utm_term={keyword}` |
| DMM→BHR | `https://noorhatransport.com/services/bahrain-to-dammam-airport-taxi?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=dmm-bhr&utm_term={keyword}` |
| RUH→BHR | `https://noorhatransport.com/services/bahrain-to-riyadh-airport-taxi?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=ruh-bhr&utm_term={keyword}` |
| Flight Alt | `https://noorhatransport.com/services/bahrain-airport-transfer?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=flight-alt&utm_term={keyword}` |
| Generic | `https://noorhatransport.com/services/bahrain-airport-transfer?utm_source=google&utm_medium=cpc&utm_campaign=bhr-airport&utm_content=generic&utm_term={keyword}` |

> `{keyword}` is Google's ValueTrack parameter — automatically replaced with the search term that triggered the ad.

---

## Negative Keywords (Campaign Level)

```
-- Jobs / Employment --
jobs
hiring
driver job
salary
careers
work
employment
vacancy

-- Other Transport Modes --
bus
public bus
saptco
train
metro
ferry

-- Flights / Airlines --
flight booking
book flight
cheap flights
airline ticket
gulf air
bahrain air
flynas
saudia airlines
air arabia
flight status

-- Other Countries --
kuwait
dubai
oman
jordan
qatar
uae
abu dhabi

-- Hotels / Accommodation --
hotel
accommodation
booking.com
airbnb
resort

-- Visa / Embassy Admin --
visa apply
embassy appointment
embassy address
embassy phone number
embassy hours
visa requirements
passport renewal

-- Navigation --
map
google maps
directions
waze
route planner

-- Competitors / Alternatives --
free
rental car
rent a car
self drive
careem
uber
bolt
parking
parking at airport

-- Irrelevant --
weather
news
history
population
tourism
sightseeing
restaurant
shopping
```

---

## GA4 → Google Ads Conversion Import (Step-by-Step)

### Step 1: Link GA4 to Google Ads
1. In Google Ads → **Tools & Settings** → **Linked accounts** → **Google Analytics**
2. Click **Details** next to your GA4 property → **Link**
3. Enable **Google Signals** (for remarketing later)

### Step 2: Import `whatsapp_click` as Conversion
1. In Google Ads → **Tools & Settings** → **Conversions**
2. Click **+ New conversion action**
3. Select **Import** → **Google Analytics 4 properties** → **Continue**
4. Find `whatsapp_click` in the list → check the box → **Import and continue**
5. Settings:
   - **Category**: Lead
   - **Value**: SAR 8 (target CPA midpoint)
   - **Count**: Every
   - **Conversion window**: 30 days
   - **Attribution**: Data-driven (or Last click if not enough data)

### Step 3: Mark as Primary Conversion
- Set `whatsapp_click` as **Primary** (used for Smart Bidding)
- Set `service_page_view` as **Secondary** (observation only)

### Step 4: Verify Tracking
- Visit a Bahrain airport page with UTM params
- Click WhatsApp → confirm `whatsapp_click` in GA4 Realtime
- Google Ads Conversions → "Recording" within 24 hrs

---

## Bid Settings

| Setting | Value |
|---------|-------|
| Bid strategy (launch) | Manual CPC |
| Max CPC (BHR→DMM group) | SAR 2.50 |
| Max CPC (BHR→RUH group) | SAR 3.00 |
| Max CPC (DMM→BHR group) | SAR 2.00 |
| Max CPC (RUH→BHR group) | SAR 2.50 |
| Max CPC (Flight-alt group) | SAR 4.00 |
| Max CPC (Generic group) | SAR 2.00 |
| Mobile bid adjustment | +25% |
| Switch to Target CPA when | 50+ conversions recorded |
| Target CPA (after switch) | SAR 8 |

---

## Budget Phasing

| Phase | When | Daily Budget |
|-------|------|-------------|
| Launch (max spend) | Week 1–2 (flights still closed) | SAR 167/day (~SAR 5,000/mo) |
| Normalize | Week 3+ | SAR 100/day (~SAR 3,000/mo) |
| Scale winning groups | After 50 conversions | Increase winners 20–30% |

**Launch with SAR 5,000/mo budget.** Flights are closed and demand is peaking. Pull back to SAR 3,000 if situation normalizes.

---

## Week 1 Optimization Plan

| Day | Action |
|-----|--------|
| Day 1 | Launch campaign. Verify conversions recording in Google Ads. |
| Day 2 | Check search terms report. Add irrelevant terms to negatives. |
| Day 3 | Check CTR by ad group. Pause any keyword below 1% CTR. |
| Day 5 | Check CPC vs budget. Adjust bids if spending too fast/slow. |
| Day 7 | Full review: CPA by ad group, top keywords, device breakdown. Shift budget from worst to best group. |

### Week 2+
- Review search terms report every 3 days. Add negatives.
- Check ad strength. If below "Good", test new headline/description combos.
- Monitor Quality Score. Low QS = landing page or ad relevance issue.
- After 50 conversions: switch to Target CPA at SAR 8.

---

## Remarketing Setup (Phase 2 — after 500+ page visitors)

Once you have enough visitor data:

1. **Create audience in GA4**: Users who visited Bahrain airport pages but did NOT click WhatsApp
2. **Import audience to Google Ads**
3. **Create Display remarketing campaign**: Show ads to people who visited but didn't convert
4. **Budget**: SAR 500/mo separate from search campaign
5. **Creative**: "Still need a ride to the airport? Fixed SAR 650. WhatsApp us."

---

## Launch Checklist

### Google Ads Account Setup
- [ ] GA4 (G-66YWZ8TF3Q) linked to Google Ads account
- [ ] `whatsapp_click` imported as primary conversion (value: SAR 8)
- [ ] `service_page_view` imported as secondary conversion

### Campaign Creation
- [ ] Campaign created: `GOOG_Search_BHR-Airport_WhatsApp_Mar26`
- [ ] Search Network only (no Display, no Search Partners)
- [ ] Location: Bahrain + Saudi Arabia (Eastern Province + Riyadh)
- [ ] Language: English + Arabic
- [ ] Daily budget: SAR 167/day (SAR 5,000/mo)
- [ ] Manual CPC selected as bid strategy

### Ad Groups
- [ ] Ad Group 1: BHR-to-DMM created with all keywords
- [ ] Ad Group 2: BHR-to-RUH created with all keywords
- [ ] Ad Group 3: DMM-to-BHR created with all keywords
- [ ] Ad Group 4: RUH-to-BHR created with all keywords
- [ ] Ad Group 5: Flight-Alternative created with all keywords
- [ ] Ad Group 6: Generic created with all keywords

### Ads
- [ ] RSA ad created in each ad group (H1 and H2 pinned)
- [ ] UTM-tagged final URLs set in each ad
- [ ] Ad strength showing "Good" or "Excellent" for each RSA

### Extensions
- [ ] 4 sitelink extensions added
- [ ] 8 callout extensions added
- [ ] 3 structured snippet extensions added
- [ ] Call extension added (+966 56 247 1583)

### Negatives & Bids
- [ ] Full negative keyword list added at campaign level
- [ ] Manual CPC bids set per ad group (see table above)
- [ ] Mobile bid adjustment +25% set

### Verification
- [ ] Visit landing page with UTM params → page loads correctly
- [ ] Click WhatsApp → GA4 Realtime shows `whatsapp_click`
- [ ] Google Ads shows conversions as "Recording" (may take 24h)
- [ ] Campaign goes LIVE

---

## Competitive Advantage Summary

| Advantage | How We Use It in Ads |
|-----------|---------------------|
| Embassy Recommendations | "Trusted by European Embassies" headline + description |
| Fixed Pricing | SAR amount in H2 (pinned). Clear, no ambiguity |
| No Overcharging | "Fair fixed pricing while others overcharge" |
| Causeway Expertise | "20+ Years Cross-Border" + "We Handle the Causeway" |
| Both Directions | Separate ad groups for each direction |
| Two Vehicle Classes | "Economy and Executive SUVs" in callouts |
| Transport-First Messaging | We sell the ride, not the airport. "We pick you up" |

---

## Campaign Naming Reference

```
Campaign:   GOOG_Search_BHR-Airport_WhatsApp_Mar26
Ad Group 1: BHR-to-DMM_Exact+Phrase
Ad Group 2: BHR-to-RUH_Exact+Phrase
Ad Group 3: DMM-to-BHR_Exact+Phrase
Ad Group 4: RUH-to-BHR_Exact+Phrase
Ad Group 5: Flight-Alternative_Exact+Phrase
Ad Group 6: BHR-Airport-Generic_Exact+Phrase
```
