# 🏨 Hotel De KOKA - Premium Website Project

**Modern Boutique Hotel in Skopje Old Bazaar**
**MVP Phase: Direct Booking Focus | 60 Rooms | 4-5 Star**

---

## 📋 Project Overview

This repository contains comprehensive documentation for building a premium, conversion-focused hotel website for Hotel De KOKA, a 60-room boutique hotel located in the historic Old Bazaar district of Skopje, North Macedonia.

### Key Objectives
- ✅ **Direct Bookings:** Drive reservations through D-EDGE booking engine
- ✅ **Mobile-First:** Lightning-fast, responsive experience
- ✅ **Multi-Language:** English, Macedonian, Albanian
- ✅ **SEO Optimized:** Rank for local Skopje hotel searches
- ✅ **Premium Design:** Luxury boutique hotel aesthetic

---

## 📂 Documentation Files

### 1. **HOTEL_WEBSITE_STRATEGY.md** (Main Strategy Document)
**What it contains:**
- ✅ MVP scope definition (Must-have, Nice-to-have, Out-of-scope)
- ✅ Complete sitemap with multi-language URL structure
- ✅ Homepage structure (9 sections, detailed breakdown)
- ✅ Marketing copy in 3 languages (EN / MK / SQ)
- ✅ UX flow for booking journey (arrival → D-EDGE handoff)
- ✅ SEO & Performance recommendations (Core Web Vitals, Schema.org, hreflang)
- ✅ GA4 event tracking strategy (10+ custom events)
- ✅ Tech stack recommendation (Next.js + Vercel)
- ✅ Deliverables timeline (3-week sprint)

**Read this first** to understand the business strategy and content approach.

---

### 2. **TECHNICAL_IMPLEMENTATION.md** (Developer Guide)
**What it contains:**
- ✅ Complete Next.js project structure
- ✅ Setup & installation instructions
- ✅ Multi-language configuration (next-intl)
- ✅ Translation files (JSON) for all 3 languages
- ✅ Tailwind CSS configuration
- ✅ React component code (Header, Hero, USP, BookNow, etc.)
- ✅ Google Analytics (GA4) integration code
- ✅ Contact form implementation (React Hook Form + API route)
- ✅ SEO implementation (metadata, Schema.org, hreflang)
- ✅ Deployment guide (Vercel)
- ✅ Pre-launch checklist

**Use this** if you're a developer building the website.

---

### 3. **DESIGN_GUIDELINES.md** (Visual Design Specs)
**What it contains:**
- ✅ Brand identity & positioning
- ✅ Color palette (Luxury Gold, Navy, Cream)
- ✅ Typography scale (Playfair Display + Inter)
- ✅ Imagery guidelines (photography style, specs)
- ✅ UI component specifications (buttons, cards, forms)
- ✅ Spacing & layout system
- ✅ Animations & interactions
- ✅ Mobile-first approach
- ✅ Accessibility guidelines (WCAG 2.1 AA)
- ✅ Homepage design breakdown
- ✅ Design tools & workflow

**Use this** if you're a designer creating mockups or a developer implementing styles.

---

## 🎯 Quick Start Guide

### For Project Managers
1. Read **HOTEL_WEBSITE_STRATEGY.md** sections 1-3 for scope and sitemap
2. Review timeline in section 10 (Deliverables Summary)
3. Check "Assumptions & Confirmations Needed" section
4. Gather required information from hotel client

### For Designers
1. Read **DESIGN_GUIDELINES.md** cover-to-cover
2. Set up Figma with color palette and typography
3. Review reference websites for inspiration
4. Follow design workflow (Wireframes → Visual Design → Prototype)
5. Use homepage design breakdown for section-by-section layout

### For Developers
1. Read **TECHNICAL_IMPLEMENTATION.md** setup section
2. Clone/fork this repository structure
3. Install dependencies: `npm install`
4. Copy component code from documentation
5. Configure environment variables (.env.local)
6. Follow pre-launch checklist before deployment

### For Copywriters
1. Read **HOTEL_WEBSITE_STRATEGY.md** section 4 (Marketing Copy)
2. Use provided copy as baseline for EN / MK / SQ
3. Adapt tone based on brand personality (sophisticated, welcoming, local)
4. Ensure copy highlights USPs: Old Bazaar, free parking, breakfast included

---

## 🏗️ Project Structure (Recommended)

```
hotel-de-koka-website/
│
├── docs/                           # This repository
│   ├── HOTEL_WEBSITE_STRATEGY.md
│   ├── TECHNICAL_IMPLEMENTATION.md
│   ├── DESIGN_GUIDELINES.md
│   └── PROJECT_README.md
│
├── design/                         # Figma files, assets
│   ├── wireframes/
│   ├── mockups/
│   ├── prototypes/
│   └── assets/
│       ├── logos/
│       ├── icons/
│       └── images/
│
└── website/                        # Next.js codebase
    ├── public/
    ├── src/
    ├── package.json
    └── next.config.js
```

---

## 🚀 Tech Stack (Recommended)

| Layer | Technology | Why |
|-------|-----------|-----|
| **Framework** | Next.js 14+ | SSR/SSG, perfect SEO, Image optimization |
| **Language** | TypeScript | Type safety, better DX |
| **Styling** | Tailwind CSS | Rapid development, mobile-first |
| **i18n** | next-intl | Best Next.js multi-language solution |
| **Forms** | React Hook Form | Performant, easy validation |
| **Analytics** | Google Analytics 4 | Industry standard, free |
| **Deployment** | Vercel | Zero-config, global CDN, free tier |
| **Email** | EmailJS / API Route | Simple contact form handling |

**Cost:** ~$12/year (domain only) - Everything else free!

---

## 📊 Key Features & USPs

### Hotel USPs (Business)
1. **Prime Location:** 2-minute walk to Old Bazaar (Čaršija)
2. **Free Parking:** On-site, complimentary for all guests
3. **Breakfast Included:** Daily buffet with local specialties
4. **Modern Rooms:** 60 contemporary, well-appointed rooms
5. **Walkable City:** All major attractions within 10 minutes

### Website USPs (Technical)
1. **Blazing Fast:** Core Web Vitals all green (90+ Lighthouse score)
2. **Mobile-First:** Perfect experience on all devices
3. **SEO Optimized:** Schema.org, hreflang, sitemap
4. **Multi-Language:** Seamless EN/MK/SQ switching
5. **Analytics-Ready:** GA4 tracking with custom events
6. **Conversion-Focused:** Sticky Book Now CTA, clear UX flow

---

## 🎨 Brand Identity Quick Reference

### Colors
- **Primary:** Luxury Gold (#D4AF37)
- **Dark:** Navy Blue (#1A1A2E)
- **Light:** Cream (#F5F5F0)

### Fonts
- **Headlines:** Playfair Display (Serif)
- **Body:** Inter (Sans-Serif)

### Photography Style
- Natural lighting, warm tones
- Showcase Old Bazaar proximity
- Professional, inviting spaces
- Real hotel (no generic stock photos)

### Tone of Voice
- Sophisticated but not pretentious
- Warm and welcoming
- Locally rooted (Skopje pride)
- Modern and professional

---

## 🔗 D-EDGE Booking Integration

### Base URL
```
https://www.secure-hotel-booking.com/Hotel-De-KOKA/2DGL/{locale}?hotelId=15117
```

### Language Mapping
- English: `/en-US`
- Macedonian: `/mk-MK` (ASSUMPTION - verify with D-EDGE)
- Albanian: `/sq-AL` (ASSUMPTION - verify with D-EDGE)

### Implementation
- Link-out (opens in new tab)
- `target="_blank"` with `rel="noopener noreferrer"`
- GA4 event tracking on click
- Sticky "Book Now" CTA in header

**⚠️ IMPORTANT:** Verify Macedonian/Albanian language codes with D-EDGE support.

---

## 📈 Success Metrics (Post-Launch)

### Primary KPIs
1. **Direct Booking Rate:** % of visitors who click "Book Now"
2. **Conversion Rate:** Booking clicks → Completed reservations (tracked via D-EDGE)
3. **Bounce Rate:** < 40% (industry standard)
4. **Avg. Session Duration:** > 2 minutes

### Secondary KPIs
1. **Page Load Time:** < 2.5s (LCP)
2. **Mobile Traffic:** Expected 60%+ of total
3. **Language Distribution:** Track EN vs MK vs SQ usage
4. **Contact Form Submissions:** Measure lead generation

### GA4 Events to Monitor
- `click_book_now` (most important!)
- `outbound_booking_engine`
- `view_rooms`
- `form_submit` (contact)
- `scroll_depth`

---

## ⚠️ Assumptions & Open Questions

### D-EDGE Integration
- ❓ Language code support (MK/SQ) - **Action:** Contact D-EDGE support
- ❓ Room type deep linking - **Action:** Review D-EDGE API docs
- ❓ Tracking parameters - **Action:** Ask if we can pass UTM tags

### Hotel Information Needed
- ❓ Exact street address
- ❓ GPS coordinates (for maps + Schema.org)
- ❓ Phone number & email
- ❓ Number of room types (Deluxe, Suite, etc.)
- ❓ Star rating (4 or 5?)
- ❓ Check-in/check-out times
- ❓ Cancellation policy details

### Content Assets Needed
- ❓ Professional photography (60+ images) - client provides or photoshoot?
- ❓ Logo files (SVG preferred)
- ❓ Exact brand colors (if different from proposed palette)
- ❓ Social media handles

---

## 📅 Timeline & Milestones

### Week 1: Planning & Design
- Day 1-2: Finalize content, gather assets
- Day 3-5: Design wireframes & mockups
- Day 6-7: Client review & approval

### Week 2: Development
- Day 1-3: Build homepage + navigation
- Day 4-5: Build Rooms + Location pages
- Day 6-7: Build Contact page + forms

### Week 3: Testing & Launch
- Day 1-2: Integrate D-EDGE links + GA4
- Day 3-4: Mobile testing, performance optimization
- Day 5: Client review on staging
- Day 6-7: Launch to production!

**Total:** 3 weeks to MVP launch

---

## 👥 Team Roles

### Recommended Team
- **1x Project Manager** - Coordinate, manage client
- **1x UX/UI Designer** - Figma mockups, design system
- **1x Frontend Developer** - Next.js implementation
- **1x Copywriter** - Translate & refine content (MK/SQ)
- **1x QA Tester** - Cross-browser, mobile testing

### Minimal Team (Budget Option)
- **1x Full-Stack Designer/Developer** - Design + code
- **1x Translator** - MK/SQ copy (Fiverr/Upwork)
- **Client** - QA testing on staging

---

## 🔐 Security & Privacy

### Requirements
- ✅ SSL certificate (HTTPS only)
- ✅ Secure form handling (CSRF protection)
- ✅ Privacy policy page (GDPR compliance)
- ✅ Cookie consent banner (if using cookies beyond GA4)
- ✅ Contact form spam protection (reCAPTCHA or honeypot)
- ✅ Environment variables for sensitive keys (never commit!)

### Vercel Security Headers
- X-Frame-Options: SAMEORIGIN
- X-Content-Type-Options: nosniff
- Referrer-Policy: origin-when-cross-origin
- Strict-Transport-Security (HSTS)

---

## 📞 Support & Maintenance

### Post-Launch Support Plan
**Month 1-3 (Critical Period):**
- Monitor GA4 for errors/issues
- Quick fixes for bugs (response time: 24h)
- Monthly performance reports
- Content updates (pricing, photos, etc.)

**Ongoing (Month 4+):**
- Quarterly performance reviews
- Content updates as needed
- Security updates (Next.js, dependencies)
- Annual redesign/refresh (optional)

### Maintenance Tasks
- [ ] Monthly: Review GA4 metrics
- [ ] Quarterly: Update dependencies (npm audit)
- [ ] Bi-Annually: Refresh photography
- [ ] Annually: SEO audit, content refresh

---

## 🚫 What's NOT Included (Out of Scope)

- ❌ Custom booking engine (using D-EDGE)
- ❌ Payment processing
- ❌ PMS integration
- ❌ Channel manager
- ❌ Admin dashboard for reservations
- ❌ Guest portal/login
- ❌ Email marketing automation (post-MVP)
- ❌ CRM features

**Why:** MVP focuses on presentation + direct booking handoff. These features can be added post-launch if needed.

---

## ✅ Pre-Launch Checklist

### Content
- [ ] All text finalized (EN/MK/SQ)
- [ ] All images uploaded & optimized
- [ ] Room descriptions complete
- [ ] Hotel info confirmed (address, phone, email)
- [ ] Policies written (privacy, cancellation, terms)

### Technical
- [ ] D-EDGE links tested (all languages)
- [ ] Contact form sending emails
- [ ] GA4 tracking verified
- [ ] All pages mobile responsive
- [ ] Core Web Vitals green (Lighthouse 90+)
- [ ] SSL certificate active
- [ ] 404 page created
- [ ] Sitemap.xml submitted to Google

### SEO
- [ ] Meta titles/descriptions (all pages, all languages)
- [ ] Schema.org markup validated
- [ ] Hreflang tags implemented
- [ ] Google Search Console verified
- [ ] Google Business Profile claimed

### Legal
- [ ] Privacy policy live
- [ ] Terms & conditions live
- [ ] Cookie consent (if applicable)

---

## 🎓 Resources & Learning

### Documentation
- **Next.js Docs:** https://nextjs.org/docs
- **Tailwind CSS:** https://tailwindcss.com/docs
- **next-intl:** https://next-intl-docs.vercel.app/

### Design Inspiration
- **Awwwards (Hotels):** https://www.awwwards.com/websites/hotel/
- **Dribbble:** Search "hotel website"

### SEO Tools (Free)
- **Google Search Console:** Track rankings
- **Google PageSpeed Insights:** Performance
- **Schema.org Validator:** Test structured data

### Analytics
- **Google Analytics 4:** Free, industry standard
- **Vercel Analytics:** Speed insights (included with Vercel)

---

## 📝 Changelog

### Version 1.0 (2024-12-20)
- Initial project documentation created
- Strategy, technical, and design guides complete
- Ready for client review

---

## 🤝 Contributing

This is a client project, but if you're part of the team:

1. Read all documentation files before starting work
2. Follow naming conventions in design/code
3. Update documentation if you change implementation
4. Test on multiple devices before committing
5. Use conventional commit messages

---

## 📧 Contact

**Project Lead:** [Your Name]
**Email:** [Your Email]
**Client:** Hotel De KOKA - Skopje, North Macedonia

---

## 📄 License

© 2024 Hotel De KOKA. All rights reserved.
This documentation is proprietary and confidential.

---

**Built with ❤️ for Hotel De KOKA - Where modern luxury meets historic Skopje.**

**Ready to transform direct bookings! 🚀**
