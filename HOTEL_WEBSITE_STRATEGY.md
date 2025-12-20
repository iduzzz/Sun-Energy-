# Hotel Website Strategy & Documentation
**Premium Boutique Hotel - Skopje Old Bazaar**
**60 Rooms | 4-5 Star | Direct Booking Focus**

---

## 📋 1. MVP SCOPE DEFINITION

### ✅ MUST-HAVE (Phase 1 - MVP)

#### Core Pages
- **Home Page** - Hero, USPs, rooms preview, location highlight, CTA
- **Rooms Page** - Room types, gallery, amenities, pricing info (no live rates)
- **Location Page** - Interactive map, walkability highlights, nearby attractions
- **Contact Page** - Phone, email, address, contact form
- **Booking Integration** - CTA buttons linking to D-EDGE (link-out)

#### Core Features
- **Multi-language Support** - EN / MK / SQ with proper hreflang
- **Mobile-First Responsive Design** - Perfect on all devices
- **Sticky "Book Now" CTA** - Always visible header button
- **D-EDGE Link-Out** - Opens in new tab with proper tracking
- **Performance Optimized** - Core Web Vitals green scores
- **Image Optimization** - WebP, lazy loading, responsive images
- **SEO Foundation** - Meta tags, Schema.org, sitemap.xml
- **Analytics Setup** - GA4 with custom event tracking
- **Contact Form** - Simple email capture (EmailJS or similar)

#### Key Content Sections
- Hero with booking CTA
- Location USP (Old Bazaar, walkable city)
- Free parking highlight
- Breakfast included highlight
- Modern rooms showcase
- Image gallery
- Trust signals (reviews placeholder)
- Footer with policies

### 🎯 NICE-TO-HAVE (Post-MVP)

- **Special Offers Page** - Seasonal deals, packages
- **Gallery Page** - Dedicated photo gallery with filtering
- **About Page** - Hotel story, team, philosophy
- **Blog / Local Guide** - Skopje attractions, tips
- **Reviews Integration** - Google Reviews, TripAdvisor widget
- **Live Availability Widget** - D-EDGE embedded calendar (if API available)
- **Virtual Tour** - 360° room previews
- **Multilingual Blog Content** - SEO-driven local content
- **Newsletter Signup** - Email marketing integration
- **Loyalty Program Info** - Repeat guest benefits
- **Accessibility Features** - WCAG 2.1 AA compliance
- **Chatbot Integration** - Customer support automation

### 🚫 OUT-OF-SCOPE (Never)

- ❌ Custom PMS integration
- ❌ Internal booking engine
- ❌ Payment processing
- ❌ Reservation management system
- ❌ Channel manager integration
- ❌ Rate management tools
- ❌ Inventory management
- ❌ Guest portal/login system
- ❌ Admin dashboard for reservations
- ❌ Custom CRM features

---

## 🗂️ 2. SITEMAP STRUCTURE

```
Home (/)
│
├── Rooms (/rooms)
│   ├── Deluxe Room (/rooms/deluxe)
│   ├── Superior Room (/rooms/superior)
│   └── Suite (/rooms/suite)
│
├── Location (/location)
│   └── Nearby Attractions
│
├── Contact (/contact)
│
└── Policies (/policies)
    ├── Privacy Policy
    ├── Terms & Conditions
    ├── Cancellation Policy
    └── Cookie Policy

External:
└── Book Now → https://www.secure-hotel-booking.com/Hotel-De-KOKA/2DGL/en-US?hotelId=15117
    (Opens in new tab)
```

### URL Structure (Multi-language)

**English (Default)**
- `/` - Home
- `/rooms` - Rooms
- `/location` - Location
- `/contact` - Contact
- `/policies` - Policies

**Macedonian**
- `/mk` - Дома
- `/mk/sobi` - Соби
- `/mk/lokacija` - Локација
- `/mk/kontakt` - Контакт
- `/mk/politiki` - Политики

**Albanian**
- `/sq` - Ballina
- `/sq/dhomat` - Dhomat
- `/sq/vendndodhja` - Vendndodhja
- `/sq/kontakti` - Kontakti
- `/sq/politikat` - Politikat

---

## 🏠 3. HOME PAGE STRUCTURE (Section-by-Section)

### Section 1: **Hero Section**
**Goal:** Immediate impact + clear CTA

**Components:**
- Full-screen hero image/video (Old Bazaar view or modern room)
- Headline (see Copy section)
- Subheadline emphasizing USP
- Primary CTA: "Book Now" → D-EDGE
- Secondary CTA: "Explore Rooms" → Scroll/navigate
- Language switcher (EN / MK / SQ)

**Design Notes:**
- Overlay gradient for text readability
- Subtle animation on load
- Mobile: Simplified, taller hero (60vh)

---

### Section 2: **USP Highlights (3-Column)**
**Goal:** Quick value proposition

**Content:**
1. **📍 Prime Location**
   - Icon: Location pin
   - Title: "Old Bazaar Steps Away"
   - Text: "Walk to Skopje's historic heart in 2 minutes"

2. **🅿️ Free Parking**
   - Icon: Parking symbol
   - Title: "Free Parking Included"
   - Text: "Complimentary secure parking for all guests"

3. **🍳 Breakfast Included**
   - Icon: Coffee/breakfast
   - Title: "Daily Breakfast"
   - Text: "Start your day with complimentary breakfast"

**Design Notes:**
- Clean icons, minimal text
- Subtle hover effects
- Mobile: Stack vertically

---

### Section 3: **Rooms Preview**
**Goal:** Showcase room types, drive to Rooms page

**Components:**
- Section title: "Modern Comfort Awaits"
- 2-3 room cards with:
  - High-quality image
  - Room name
  - Key features (2-3 bullet points)
  - "View Details" link → Rooms page
- CTA: "See All Rooms" → /rooms

**Design Notes:**
- Carousel on mobile
- Grid on desktop (2-3 columns)
- Lazy-loaded images

---

### Section 4: **Location Spotlight**
**Goal:** Emphasize walkability and Old Bazaar proximity

**Components:**
- Split layout:
  - **Left:** Map (Google Maps embed or image)
  - **Right:** Text content
    - Title: "Explore Skopje on Foot"
    - Description highlighting:
      - Old Bazaar (2 min walk)
      - Stone Bridge (5 min)
      - Macedonia Square (8 min)
      - Kale Fortress (10 min)
    - CTA: "View Location" → /location

**Design Notes:**
- Interactive map (optional)
- Mobile: Stack vertically

---

### Section 5: **Breakfast & Parking Details**
**Goal:** Reinforce free value-adds

**Components:**
- Two-column layout or accordion
- **Breakfast:**
  - Image of breakfast spread
  - Description: "Complimentary buffet breakfast with local and international options"
- **Parking:**
  - Image of parking area (or icon-based)
  - Description: "Free on-site parking available to all guests"

**Design Notes:**
- Visual emphasis on "FREE"
- Mobile-friendly images

---

### Section 6: **Gallery Teaser**
**Goal:** Visual storytelling

**Components:**
- Masonry/grid of 6-9 images
- Mix of: rooms, breakfast, location, facade, amenities
- Hover effect with subtle zoom
- Optional: "View Full Gallery" link (post-MVP)

**Design Notes:**
- Lazy loading critical
- WebP format
- Proper aspect ratios

---

### Section 7: **Reviews/Trust Signals**
**Goal:** Build credibility

**Components (MVP - Placeholder):**
- Section title: "What Our Guests Say"
- 2-3 static testimonial cards:
  - Quote
  - Guest name + country
  - Star rating
- Note: Post-MVP integrate Google Reviews API

**Design Notes:**
- Subtle background color differentiation
- Carousel on mobile

---

### Section 8: **Final CTA**
**Goal:** Drive conversions

**Components:**
- Bold headline: "Ready to Experience Skopje?"
- Large "Book Now" button → D-EDGE
- Subtext: "Best rates guaranteed when you book direct"

**Design Notes:**
- High contrast background
- Large touch-friendly button
- Mobile: Full-width CTA

---

### Section 9: **Footer**
**Goal:** Navigation, legal, contact

**Components:**
- **Column 1:** Logo, tagline, social links
- **Column 2:** Quick Links (Rooms, Location, Contact)
- **Column 3:** Policies (Privacy, Terms, Cancellation)
- **Column 4:** Contact info (phone, email, address)
- Bottom bar: Copyright, language switcher

**Design Notes:**
- Dark background, light text
- Mobile: Accordion-style sections

---

## ✍️ 4. MARKETING COPY (3 Languages)

### 🇬🇧 ENGLISH (EN)

#### Hero Section
**Headline:**
"Your Gateway to Skopje's Historic Heart"

**Subheadline:**
"Modern comfort meets centuries-old charm. 60 stylish rooms, free parking, and the Old Bazaar at your doorstep."

**CTA Button:**
"Book Your Stay"

---

#### About Section (Short)
"Perfectly located in the heart of Skopje's Old Town, our boutique hotel offers 60 contemporary rooms designed for modern travelers who appreciate history. Wake up to complimentary breakfast, explore the iconic Old Bazaar just steps away, and return to secure free parking—all included in your stay."

---

#### Location Highlights
**Main Text:**
"Everything Skopje has to offer is within walking distance. Stroll to the ancient Old Bazaar in under 2 minutes, cross the historic Stone Bridge, or wander to Macedonia Square. No taxis, no stress—just authentic experiences at your pace."

**Key Attractions:**
- 🕌 Old Bazaar (Čaršija) – 2 min walk
- 🌉 Stone Bridge – 5 min walk
- 🏛️ Macedonia Square – 8 min walk
- 🏰 Kale Fortress – 10 min walk
- 🏛️ Museums & Galleries – 5-12 min walk

---

#### Amenities Copy
**Free Parking:**
"Forget the hassle of finding parking in the city. Our guests enjoy complimentary on-site parking throughout their stay."

**Breakfast Included:**
"Start each morning with a delicious buffet breakfast featuring local Macedonian specialties and international favorites. Included free with every reservation."

**Modern Rooms:**
"Each of our 60 rooms blends contemporary design with thoughtful amenities—comfortable beds, high-speed Wi-Fi, climate control, and stunning city or Old Town views."

---

#### Meta Description (SEO)
"Boutique hotel in Skopje Old Town with 60 modern rooms, free parking & breakfast. Steps from the Old Bazaar. Book direct for best rates."

---

### 🇲🇰 MACEDONIAN (MK)

#### Hero Section
**Headline:**
"Вашиот Премин кон Историското Срце на Скопје"

**Subheadline:**
"Модерен комфор среќава вековна шарм. 60 стилски соби, бесплатен паркинг и Старата Чаршија пред ваши врати."

**CTA Button:**
"Резервирајте Престој"

---

#### About Section (Short)
"Совршено лоцирани во срцето на Стариот Град на Скопје, нашиот бутик хотел нуди 60 современи соби дизајнирани за модерни патници кои ја ценат историјата. Разбудете се со бесплатен појадок, истражувајте ја иконичната Стара Чаршија само неколку чекори подалеку и вратете се на сигурен бесплатен паркинг—сè вклучено во вашиот престој."

---

#### Location Highlights
**Main Text:**
"Сè што Скопје нуди е на пешачка далечина. Прошетајте до древната Стара Чаршија за помалку од 2 минути, поминете го историскиот Камен Мост или прошетајте до Плоштад Македонија. Без такси, без стрес—само автентични доживувања на ваше темпо."

**Key Attractions:**
- 🕌 Стара Чаршија – 2 мин пешки
- 🌉 Камен Мост – 5 мин пешки
- 🏛️ Плоштад Македонија – 8 мин пешки
- 🏰 Кале Тврдина – 10 мин пешки
- 🏛️ Музеи и Галерии – 5-12 мин пешки

---

#### Amenities Copy
**Free Parking:**
"Заборавете на проблемот со наоѓање паркинг во градот. Нашите гости уживаат во бесплатен паркинг на лице место во текот на нивниот престој."

**Breakfast Included:**
"Започнете секое утро со вкусен бифе појадок со локални македонски специјалитети и меѓународни омилени јадења. Вклучено бесплатно со секоја резервација."

**Modern Rooms:**
"Секоја од нашите 60 соби комбинира современ дизајн со внимателни удобности—удобни кревети, брз Wi-Fi, климатизација и прекрасен поглед на градот или Стариот Град."

---

#### Meta Description (SEO)
"Бутик хотел во Стариот Град на Скопје со 60 современи соби, бесплатен паркинг и појадок. Чекори од Старата Чаршија. Резервирајте директно за најдобри цени."

---

### 🇦🇱 ALBANIAN (SQ)

#### Hero Section
**Headline:**
"Porta Juaj drejt Zemrës Historike të Shkupit"

**Subheadline:**
"Komoditeti modern takon sharmin shekullor. 60 dhoma moderne, parking falas dhe Çarshia e Vjetër para derës tuaj."

**CTA Button:**
"Rezervo Qëndrimin"

---

#### About Section (Short)
"Vendosur në mënyrë perfekte në zemër të Qytetit të Vjetër të Shkupit, hoteli ynë butik ofron 60 dhoma bashkëkohore të dizajnuara për udhëtarë modernë që vlerësojnë historinë. Zgjohuni me mëngjes falas, eksploroni Çarshinë ikonike vetëm disa hapa larg dhe kthehuni në parking të sigurt falas—gjithçka e përfshirë në qëndrimin tuaj."

---

#### Location Highlights
**Main Text:**
"Gjithçka që Shkupi ofron është në distancë këmbësh. Ecni deri në Çarshinë e Lashtë në më pak se 2 minuta, kaloni Urën e Gurit historike ose shëtisni në Sheshin Maqedonia. Pa taksi, pa stres—vetëm përvojë autentike në ritmin tuaj."

**Key Attractions:**
- 🕌 Çarshia e Vjetër – 2 min në këmbë
- 🌉 Ura e Gurit – 5 min në këmbë
- 🏛️ Sheshi Maqedonia – 8 min në këmbë
- 🏰 Kalaja Kale – 10 min në këmbë
- 🏛️ Muzetë dhe Galeritë – 5-12 min në këmbë

---

#### Amenities Copy
**Free Parking:**
"Harroni problemin e gjetjes së parkingut në qytet. Mysafirët tanë gëzojnë parking falas në vendndodhje gjatë gjithë qëndrimit të tyre."

**Breakfast Included:**
"Filloni çdo mëngjes me një mëngjes bufet të shijshëm me specialitete lokale maqedonase dhe të preferuara ndërkombëtare. I përfshirë falas me çdo rezervim."

**Modern Rooms:**
"Secila nga 60 dhomat tona kombinon dizajnin bashkëkohor me komoditet të kujdesshëm—shtretër të rehatshëm, Wi-Fi të shpejtë, klimatizim dhe pamje mahnitëse të qytetit ose Qytetit të Vjetër."

---

#### Meta Description (SEO)
"Hotel butik në Qytetin e Vjetër të Shkupit me 60 dhoma moderne, parking dhe mëngjes falas. Hapa nga Çarshia e Vjetër. Rezervoni direkt për tarifat më të mira."

---

## 🔄 5. UX FLOW - BOOKING JOURNEY

### User Journey: First Visit → Booking

```
1. ARRIVAL
   ├─ User lands on Home page
   ├─ Hero loads with CTA "Book Now" visible
   └─ Language auto-detected (browser) or manual switch

2. DISCOVERY
   ├─ User scrolls through USP highlights
   ├─ Views room previews
   ├─ Reads location benefits
   └─ Sees trust signals (reviews)

3. INTENT
   ├─ User clicks "Book Now" (sticky header OR section CTA)
   └─ OR navigates to /rooms for more details

4. ROOM EXPLORATION (if applicable)
   ├─ User views room types
   ├─ Sees images, amenities, descriptions
   └─ Clicks "Book This Room" CTA

5. HANDOFF TO D-EDGE
   ├─ onClick event triggers:
   │  ├─ GA4 event: click_book_now
   │  ├─ Data layer push with room type (if applicable)
   │  └─ Opens D-EDGE URL in new tab
   │
   ├─ D-EDGE URL structure:
   │  https://www.secure-hotel-booking.com/Hotel-De-KOKA/2DGL/{lang}?hotelId=15117&roomType={roomType}
   │  └─ {lang} = en-US / mk-MK / sq-AL (map from site language)
   │
   └─ User completes booking on D-EDGE

6. POST-BOOKING (Outside our scope)
   └─ D-EDGE handles confirmation, payment, emails
```

---

### Technical Implementation: "Book Now" CTA

**HTML Structure:**
```html
<a href="https://www.secure-hotel-booking.com/Hotel-De-KOKA/2DGL/en-US?hotelId=15117"
   target="_blank"
   rel="noopener noreferrer"
   class="btn-book-now"
   data-room-type="deluxe"
   onclick="trackBookingClick(this)">
   Book Now
</a>
```

**JavaScript Tracking:**
```javascript
function trackBookingClick(element) {
  const roomType = element.getAttribute('data-room-type') || 'general';
  const language = document.documentElement.lang;

  // GA4 Event
  gtag('event', 'click_book_now', {
    'event_category': 'Booking',
    'event_label': roomType,
    'language': language,
    'value': 1
  });

  // Optional: Track outbound link
  gtag('event', 'outbound_booking_engine', {
    'destination': 'D-EDGE',
    'room_type': roomType
  });
}
```

**Language Mapping for D-EDGE:**
- EN → `/en-US`
- MK → `/mk-MK` (ASSUMPTION: confirm with D-EDGE docs)
- SQ → `/sq-AL` (ASSUMPTION: confirm with D-EDGE docs)

**Fallback:** If D-EDGE doesn't support MK/SQ, default to `/en-US`

---

### Edge Cases & Handling

**1. Popup Blockers:**
- Use `target="_blank"` (not window.open)
- Provide inline message: "If booking doesn't open, click here"

**2. Mobile Behavior:**
- Same `target="_blank"` approach
- Ensure proper return to site (back button works)

**3. Session Continuity:**
- No session needed on our side
- D-EDGE handles all booking state

**4. Tracking Failed Opens:**
```javascript
window.addEventListener('blur', function() {
  // Triggered if new tab opens successfully
});
```

---

## 🚀 6. SEO & PERFORMANCE RECOMMENDATIONS

### A. Core Web Vitals Targets

| Metric | Target | Strategy |
|--------|--------|----------|
| **LCP** (Largest Contentful Paint) | < 2.5s | - Optimize hero image (WebP, srcset)<br>- Preload critical images<br>- CDN for assets |
| **FID** (First Input Delay) | < 100ms | - Minimize JS<br>- Defer non-critical scripts<br>- Code splitting |
| **CLS** (Cumulative Layout Shift) | < 0.1 | - Set image dimensions<br>- Reserve space for dynamic content<br>- Avoid layout shifts |
| **INP** (Interaction to Next Paint) | < 200ms | - Optimize event handlers<br>- Debounce scroll events |
| **TTFB** (Time to First Byte) | < 600ms | - Server-side caching<br>- Edge caching (Cloudflare/Vercel) |

---

### B. Image Optimization Strategy

**Format:**
- Primary: **WebP** with JPEG fallback
- Use `<picture>` element for responsive images

**Sizes:**
- Hero: 1920x1080 (desktop), 768x1024 (mobile)
- Room cards: 600x400
- Gallery: 800x600
- Thumbnails: 300x200

**Implementation:**
```html
<picture>
  <source srcset="/images/hero-mobile.webp" media="(max-width: 768px)" type="image/webp">
  <source srcset="/images/hero-desktop.webp" media="(min-width: 769px)" type="image/webp">
  <img src="/images/hero-desktop.jpg" alt="Hotel lobby" loading="lazy" width="1920" height="1080">
</picture>
```

**Tools:**
- ImageOptim / Squoosh for compression
- Cloudinary / Imgix for CDN + transformation (optional)

**Lazy Loading:**
- Native `loading="lazy"` for below-fold images
- Eager load hero image only

---

### C. Metadata & On-Page SEO

**Homepage `<head>` (English Example):**
```html
<title>Boutique Hotel in Skopje Old Town | Free Parking & Breakfast | Hotel De KOKA</title>
<meta name="description" content="Experience Skopje from our 60-room boutique hotel steps from the Old Bazaar. Modern rooms, free parking, breakfast included. Book direct for best rates.">

<!-- Open Graph -->
<meta property="og:title" content="Hotel De KOKA - Skopje Old Bazaar">
<meta property="og:description" content="Modern boutique hotel in the heart of Skopje's historic Old Town.">
<meta property="og:image" content="https://yourdomain.com/og-image.jpg">
<meta property="og:url" content="https://yourdomain.com">
<meta property="og:type" content="website">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Hotel De KOKA - Skopje Old Bazaar">
<meta name="twitter:description" content="Modern boutique hotel in the heart of Skopje's historic Old Town.">
<meta name="twitter:image" content="https://yourdomain.com/twitter-image.jpg">

<!-- Canonical -->
<link rel="canonical" href="https://yourdomain.com/">
```

---

### D. Hreflang for Multi-language SEO

**Implementation:**
```html
<link rel="alternate" hreflang="en" href="https://yourdomain.com/" />
<link rel="alternate" hreflang="mk" href="https://yourdomain.com/mk/" />
<link rel="alternate" hreflang="sq" href="https://yourdomain.com/sq/" />
<link rel="alternate" hreflang="x-default" href="https://yourdomain.com/" />
```

**Sitemap.xml (Multi-language):**
```xml
<url>
  <loc>https://yourdomain.com/</loc>
  <xhtml:link rel="alternate" hreflang="en" href="https://yourdomain.com/" />
  <xhtml:link rel="alternate" hreflang="mk" href="https://yourdomain.com/mk/" />
  <xhtml:link rel="alternate" hreflang="sq" href="https://yourdomain.com/sq/" />
</url>
```

---

### E. Schema.org Structured Data (JSON-LD)

**Hotel Schema (Homepage):**
```json
{
  "@context": "https://schema.org",
  "@type": "Hotel",
  "name": "Hotel De KOKA",
  "description": "Boutique hotel in Skopje Old Town with 60 modern rooms, free parking, and breakfast included.",
  "image": "https://yourdomain.com/hotel-main.jpg",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[Your Street Address]",
    "addressLocality": "Skopje",
    "addressRegion": "Skopje",
    "postalCode": "[Postal Code]",
    "addressCountry": "MK"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 42.0000,
    "longitude": 21.0000
  },
  "telephone": "+389-XX-XXX-XXX",
  "email": "info@hotelname.com",
  "starRating": {
    "@type": "Rating",
    "ratingValue": "4"
  },
  "priceRange": "$$",
  "amenityFeature": [
    {
      "@type": "LocationFeatureSpecification",
      "name": "Free Parking",
      "value": true
    },
    {
      "@type": "LocationFeatureSpecification",
      "name": "Free Breakfast",
      "value": true
    },
    {
      "@type": "LocationFeatureSpecification",
      "name": "Free WiFi",
      "value": true
    }
  ],
  "url": "https://yourdomain.com"
}
```

---

### F. Technical SEO Checklist

- ✅ **Sitemap.xml** - Multi-language with hreflang
- ✅ **Robots.txt** - Allow all, block admin areas
- ✅ **SSL Certificate** - HTTPS only
- ✅ **Mobile-Friendly** - Pass Google Mobile-Friendly Test
- ✅ **Page Speed** - Target 90+ on PageSpeed Insights
- ✅ **Structured Data** - Validate with Google Rich Results Test
- ✅ **Canonical Tags** - Prevent duplicate content
- ✅ **XML Sitemap Submission** - Google Search Console + Bing Webmaster
- ✅ **404 Error Page** - Custom, helpful, with navigation
- ✅ **301 Redirects** - If migrating from old site

---

### G. Local SEO (Skopje)

**Google Business Profile:**
- Claim and verify listing
- Add photos, amenities, hours
- Encourage guest reviews
- Add hotel as "Hotel De KOKA" at exact address

**Local Keywords:**
- "hotel near Old Bazaar Skopje"
- "hotels in Skopje Old Town"
- "boutique hotel Skopje center"
- "Skopje accommodation with parking"
- "hotels near Čaršija Skopje"

**NAP Consistency:**
- Ensure Name, Address, Phone are identical across:
  - Google Business
  - Facebook
  - TripAdvisor
  - Booking.com (if listed)
  - Website footer

---

## 📊 7. EVENT TRACKING FOR ANALYTICS (GA4)

### A. Recommended GA4 Events

| Event Name | Trigger | Parameters | Purpose |
|------------|---------|------------|---------|
| **page_view** | Auto | `page_title`, `page_location`, `language` | Track page visits |
| **click_book_now** | CTA click | `event_category: 'Booking'`<br>`room_type: 'deluxe/suite/general'`<br>`location: 'header/hero/footer'`<br>`language: 'en/mk/sq'` | Measure booking intent |
| **outbound_booking_engine** | D-EDGE link | `destination: 'D-EDGE'`<br>`room_type`<br>`language` | Track handoff success |
| **view_rooms** | /rooms page | `room_type`<br>`source: 'homepage/navigation'` | Measure room interest |
| **form_submit** | Contact form | `form_type: 'contact'`<br>`language` | Lead generation |
| **language_switch** | Language change | `from_language`<br>`to_language` | User preferences |
| **scroll_depth** | 25%, 50%, 75%, 100% | `page_path`<br>`scroll_percentage` | Engagement metrics |
| **video_play** | If using video hero | `video_title`<br>`video_provider` | Content engagement |
| **gallery_view** | Gallery interaction | `image_position`<br>`gallery_type` | Visual engagement |
| **phone_click** | Click to call | `location: 'header/footer/contact'` | Offline conversion intent |

---

### B. Event Implementation Code

**1. Page View (Auto-tracked with Enhanced Measurement)**
```javascript
// Automatically tracked by GA4, but add custom dimension for language
gtag('set', 'user_properties', {
  'language': document.documentElement.lang
});
```

**2. Book Now Click**
```javascript
function trackBookingClick(element) {
  const roomType = element.getAttribute('data-room-type') || 'general';
  const location = element.getAttribute('data-location') || 'unknown';

  gtag('event', 'click_book_now', {
    'event_category': 'Booking',
    'event_label': roomType,
    'room_type': roomType,
    'cta_location': location,
    'language': document.documentElement.lang,
    'value': 1
  });
}
```

**3. Outbound Link (D-EDGE)**
```javascript
document.querySelectorAll('a[href*="secure-hotel-booking.com"]').forEach(link => {
  link.addEventListener('click', function(e) {
    gtag('event', 'outbound_booking_engine', {
      'event_category': 'Outbound Link',
      'event_label': 'D-EDGE Booking Engine',
      'destination': 'D-EDGE',
      'room_type': this.getAttribute('data-room-type') || 'general',
      'language': document.documentElement.lang
    });
  });
});
```

**4. Scroll Depth**
```javascript
let scrollMarks = [25, 50, 75, 100];
let scrolled = [];

window.addEventListener('scroll', function() {
  const scrollPercent = (window.scrollY / (document.body.scrollHeight - window.innerHeight)) * 100;

  scrollMarks.forEach(mark => {
    if (scrollPercent >= mark && !scrolled.includes(mark)) {
      scrolled.push(mark);
      gtag('event', 'scroll_depth', {
        'event_category': 'Engagement',
        'event_label': mark + '%',
        'scroll_percentage': mark,
        'page_path': window.location.pathname
      });
    }
  });
});
```

**5. Form Submission**
```javascript
document.getElementById('contact-form').addEventListener('submit', function(e) {
  gtag('event', 'form_submit', {
    'event_category': 'Lead Generation',
    'event_label': 'Contact Form',
    'form_type': 'contact',
    'language': document.documentElement.lang
  });
});
```

---

### C. Google Tag Manager (GTM) Setup (Recommended)

**Why GTM:**
- Easier to manage tags without code changes
- Non-developers can add tracking
- Version control for tags

**Basic GTM Container Setup:**

**Tags:**
1. GA4 Configuration Tag
2. Book Now Click Tag (Event)
3. Outbound Link Tag (Event)
4. Form Submission Tag (Event)
5. Scroll Depth Tag (Event)

**Triggers:**
1. All Pages (pageview)
2. Click - Book Now buttons (CSS selector: `.btn-book-now`)
3. Click - Outbound D-EDGE (URL contains `secure-hotel-booking.com`)
4. Form Submission (CSS selector: `#contact-form`)
5. Scroll Depth (25%, 50%, 75%, 100%)

**Variables:**
1. Language (Custom JS: `document.documentElement.lang`)
2. Room Type (Data Layer Variable: `roomType`)
3. CTA Location (Click Element Attribute: `data-location`)

---

### D. Conversion Goals in GA4

**Primary Conversions:**
- `click_book_now` → Mark as Key Event
- `outbound_booking_engine` → Mark as Key Event

**Secondary Conversions:**
- `form_submit`
- `phone_click`

**Reporting:**
- Create custom report: "Booking Funnel"
  - Page views → Room views → Book Now clicks → D-EDGE handoff

---

## 🛠️ 8. TECH STACK RECOMMENDATION

### Option A: **Next.js (RECOMMENDED)**

**Why:**
- ✅ **Performance:** SSR/SSG for instant page loads
- ✅ **SEO:** Server-side rendering = perfect indexing
- ✅ **i18n Built-in:** Native multi-language support
- ✅ **Image Optimization:** Automatic WebP conversion, lazy loading
- ✅ **API Routes:** Contact form backend without separate server
- ✅ **Vercel Deployment:** One-click deploy, global CDN
- ✅ **Developer Experience:** Modern React, TypeScript support
- ✅ **Future-Proof:** Easy to add features (blog, offers, etc.)

**Stack:**
```
Framework: Next.js 14+ (App Router)
Language: TypeScript
Styling: Tailwind CSS
CMS (optional): Sanity.io / Contentful (for future blog)
Forms: React Hook Form + EmailJS
Analytics: GA4 via next/script
Deployment: Vercel (free tier perfect for this)
```

**Development Time:** 2-3 weeks

**Cost:**
- Hosting: $0 (Vercel free tier)
- Domain: ~$12/year
- EmailJS: $0 (free tier for contact forms)

**Code Example (Multi-language):**
```javascript
// next.config.js
module.exports = {
  i18n: {
    locales: ['en', 'mk', 'sq'],
    defaultLocale: 'en',
  },
}
```

---

### Option B: **Webflow**

**Why:**
- ✅ **No-Code:** Visual builder, fast iteration
- ✅ **Designer-Friendly:** Pixel-perfect control
- ✅ **Built-in CMS:** Easy content updates
- ✅ **Hosting Included:** Fast, reliable
- ✅ **Multi-language:** Via Weglot integration

**Cons:**
- ❌ **Cost:** $23/month (CMS plan) + Weglot $15/month = $38/month
- ❌ **Less Flexible:** Harder to customize complex logic
- ❌ **Vendor Lock-in:** Can't easily migrate

**Best For:** Non-technical teams, need to launch in 1 week

---

### Option C: **WordPress + Custom Theme**

**Why:**
- ✅ **Familiar:** Most developers know it
- ✅ **Plugins:** WPML for multi-language, Yoast for SEO
- ✅ **Mature Ecosystem:** Tons of resources

**Cons:**
- ❌ **Performance:** Slower than Next.js without heavy optimization
- ❌ **Security:** Requires maintenance, updates
- ❌ **Overkill:** Too complex for a simple site

**Best For:** If you already have WordPress hosting/expertise

---

### **FINAL RECOMMENDATION: Next.js + Vercel**

**Rationale:**
1. **Performance:** Core Web Vitals will be green out of the box
2. **SEO:** Perfect for multi-language + schema.org
3. **Cost:** Free hosting, minimal ongoing costs
4. **Scalability:** Easy to add booking widgets, blog, offers later
5. **Developer-Friendly:** Clean codebase, easy to maintain
6. **Modern:** Future-proof tech stack

**Deployment Flow:**
```
Code → GitHub → Vercel (auto-deploy on push)
```

**Estimated Budget:**
- Development: $0 (if DIY) or $2k-5k (agency)
- Hosting: $0/month (Vercel)
- Domain: $12/year
- Email: $0 (EmailJS free tier)
- **Total Year 1:** ~$12 + development cost

---

## 📦 DELIVERABLES SUMMARY

### Phase 1 - MVP (Week 1-3)

**Week 1:**
- [x] Finalize content (copy in 3 languages)
- [x] Design mockups (homepage, rooms, location, contact)
- [x] Set up Next.js project + i18n
- [x] Implement header with sticky "Book Now"

**Week 2:**
- [x] Build homepage (all sections)
- [x] Build rooms page
- [x] Build location page
- [x] Build contact page + form
- [x] Implement D-EDGE link-out with tracking

**Week 3:**
- [x] Add GA4 + event tracking
- [x] Optimize images (WebP, lazy loading)
- [x] Add Schema.org markup
- [x] Mobile testing + fixes
- [x] Performance testing (Lighthouse 90+)
- [x] Deploy to Vercel
- [x] Submit sitemap to Google

**Launch Checklist:**
- [ ] Domain connected + SSL
- [ ] All 3 languages live
- [ ] D-EDGE links tested (all languages)
- [ ] GA4 receiving data
- [ ] Forms sending emails
- [ ] Mobile responsive on iOS/Android
- [ ] Core Web Vitals green
- [ ] Google Search Console verified

---

## 🚨 ASSUMPTIONS & CONFIRMATIONS NEEDED

**D-EDGE Integration:**
- ❓ **ASSUMPTION:** D-EDGE supports MK/SQ language codes (`/mk-MK`, `/sq-AL`)
  - **Action:** Verify with D-EDGE documentation or support
  - **Fallback:** Default to `/en-US` if not supported

- ❓ **ASSUMPTION:** Room type can be passed via URL parameter (e.g., `&roomType=deluxe`)
  - **Action:** Check D-EDGE API docs for deep linking options
  - **Fallback:** Link to general booking page only

**Hotel Details:**
- ❓ **Confirmation Needed:**
  - Exact street address
  - GPS coordinates (for map + schema.org)
  - Phone number
  - Email address
  - Number of room types (Deluxe, Suite, Superior?)
  - Star rating (4 or 5?)
  - Check-in/check-out times

**Content:**
- ❓ **Confirmation Needed:**
  - Professional photography (will you provide, or need photoshoot?)
  - Logo files (SVG preferred)
  - Brand colors (hex codes)
  - Social media handles (Facebook, Instagram)

---

## ✅ NEXT STEPS

1. **Review this document** - Confirm scope, copy, and strategy
2. **Provide missing info** - Address assumptions above
3. **Approve design direction** - Share reference sites you like
4. **Kickoff development** - Set up Next.js project
5. **Content finalization** - Lock in copy for all 3 languages
6. **Design mockups** - Create Figma designs for approval
7. **Development sprint** - Build MVP in 2-3 weeks
8. **Launch** - Go live and start driving direct bookings!

---

**Document Version:** 1.0
**Last Updated:** 2024-12-20
**Contact:** [Your Contact Info]

---

**Ready to build a conversion-focused, lightning-fast hotel website that drives direct bookings. Let's make this happen! 🚀**
