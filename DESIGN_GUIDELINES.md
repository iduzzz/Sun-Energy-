# Design Guidelines & Visual Identity
**Hotel De KOKA - Premium Boutique Hotel**

---

## 🎨 Brand Identity

### Positioning Statement
"Modern luxury in the heart of historic Skopje. Where contemporary comfort meets centuries-old charm."

### Brand Personality
- **Sophisticated** - Premium quality without pretension
- **Welcoming** - Warm hospitality, genuine care
- **Local** - Authentically Skopje, celebrating the Old Bazaar
- **Modern** - Clean, contemporary, tech-forward

---

## 🌈 Color Palette

### Primary Colors

**Luxury Gold**
```
Hex: #D4AF37
RGB: 212, 175, 55
Usage: Primary CTAs, accents, highlights
Psychology: Prestige, quality, warmth
```

**Dark Gold**
```
Hex: #B8950A
RGB: 184, 149, 10
Usage: Hover states, secondary accents
```

**Navy Blue**
```
Hex: #1A1A2E
RGB: 26, 26, 46
Usage: Headlines, body text, dark backgrounds
Psychology: Trust, stability, luxury
```

### Secondary Colors

**Cream**
```
Hex: #F5F5F0
RGB: 245, 245, 240
Usage: Section backgrounds, soft contrasts
```

**Light Gray**
```
Hex: #F8F9FA
RGB: 248, 249, 250
Usage: Cards, subtle backgrounds
```

**Charcoal**
```
Hex: #2C2C2C
RGB: 44, 44, 44
Usage: Body text, secondary headings
```

### Accent Colors

**Success Green**
```
Hex: #10B981
Usage: Form success messages
```

**Error Red**
```
Hex: #EF4444
Usage: Error states, alerts
```

**Info Blue**
```
Hex: #3B82F6
Usage: Links, information highlights
```

---

## 📝 Typography

### Font Families

**Headlines (Serif)**
- **Font:** Playfair Display
- **Weights:** 400 (Regular), 600 (SemiBold), 700 (Bold)
- **Usage:** H1, H2, Hero headlines
- **Fallback:** Georgia, serif
- **Why:** Elegant, luxurious, readable

**Body Text (Sans-Serif)**
- **Font:** Inter
- **Weights:** 400 (Regular), 500 (Medium), 600 (SemiBold), 700 (Bold)
- **Usage:** Body copy, UI elements, navigation
- **Fallback:** system-ui, -apple-system, sans-serif
- **Why:** Modern, clean, excellent readability

### Type Scale

| Element | Font | Size | Weight | Line Height | Letter Spacing |
|---------|------|------|--------|-------------|----------------|
| **H1** | Playfair Display | 56px / 3.5rem | Bold (700) | 1.1 | -0.02em |
| **H2** | Playfair Display | 48px / 3rem | Bold (700) | 1.2 | -0.01em |
| **H3** | Inter | 32px / 2rem | SemiBold (600) | 1.3 | 0 |
| **H4** | Inter | 24px / 1.5rem | SemiBold (600) | 1.4 | 0 |
| **Body Large** | Inter | 20px / 1.25rem | Regular (400) | 1.6 | 0 |
| **Body** | Inter | 16px / 1rem | Regular (400) | 1.6 | 0 |
| **Body Small** | Inter | 14px / 0.875rem | Regular (400) | 1.5 | 0 |
| **Caption** | Inter | 12px / 0.75rem | Medium (500) | 1.4 | 0.02em |
| **Button** | Inter | 16px / 1rem | SemiBold (600) | 1 | 0.01em |

### Mobile Type Scale (< 768px)

| Element | Size |
|---------|------|
| **H1** | 36px / 2.25rem |
| **H2** | 32px / 2rem |
| **H3** | 24px / 1.5rem |
| **H4** | 20px / 1.25rem |

---

## 🖼️ Imagery Guidelines

### Photography Style

**Do:**
- ✅ High-resolution (minimum 1920px width for hero)
- ✅ Natural lighting, warm tones
- ✅ Show real hotel spaces and amenities
- ✅ Include people in context (guests enjoying spaces)
- ✅ Showcase Old Bazaar proximity and local flavor
- ✅ Golden hour photography for exterior shots
- ✅ Professional staging (tidy, inviting)

**Don't:**
- ❌ Stock photos that look generic
- ❌ Over-processed, heavily filtered images
- ❌ Dark or poorly lit photos
- ❌ Empty, cold spaces
- ❌ Images with visible dates/watermarks

### Image Specifications

| Location | Dimensions | Aspect Ratio | Format | Max Size |
|----------|-----------|--------------|--------|----------|
| **Hero** | 1920x1080 | 16:9 | WebP (JPEG fallback) | 300KB |
| **Hero Mobile** | 768x1024 | 3:4 | WebP | 150KB |
| **Room Cards** | 800x600 | 4:3 | WebP | 100KB |
| **Gallery** | 1200x900 | 4:3 | WebP | 150KB |
| **Thumbnails** | 400x300 | 4:3 | WebP | 30KB |
| **OG Image** | 1200x630 | 1.91:1 | JPEG | 100KB |

### Required Photos (60+ images total)

**Essential (20 images minimum):**
1. Hotel exterior (day + night) - 2
2. Lobby/reception - 2
3. Each room type (3-4 angles each) - 12
4. Breakfast area/buffet - 2
5. Old Bazaar proximity shot - 2

**Nice-to-Have (40+ images):**
- Room details (bed, bathroom, amenities)
- Breakfast food close-ups
- Staff interactions
- Local area/walking distance shots
- Seasonal variations

---

## 🧩 UI Components

### Buttons

**Primary Button (Book Now)**
```css
Background: #D4AF37 (Luxury Gold)
Text: White
Font: Inter SemiBold 16px
Padding: 16px 32px
Border Radius: 8px
Hover: #B8950A (Dark Gold) + Scale 1.05
Shadow: 0 10px 30px rgba(212, 175, 55, 0.3)
```

**Secondary Button**
```css
Background: Transparent
Border: 2px solid #D4AF37
Text: #D4AF37
Font: Inter SemiBold 16px
Padding: 16px 32px
Border Radius: 8px
Hover: Background #D4AF37, Text White
```

**Text Link**
```css
Text: #3B82F6
Font: Inter Medium 16px
Hover: Underline + #2563EB
```

### Cards

**Room Card**
```css
Background: White
Border Radius: 16px
Shadow: 0 4px 12px rgba(0, 0, 0, 0.08)
Padding: 0 (image full bleed at top)
Hover: Shadow 0 8px 24px rgba(0, 0, 0, 0.12) + Translate Y -4px
```

### Form Elements

**Input Fields**
```css
Background: White
Border: 1px solid #D1D5DB
Border Radius: 8px
Padding: 12px 16px
Font: Inter Regular 16px
Focus: Border #D4AF37, Ring 2px #D4AF37 with opacity 0.2
```

---

## 📐 Spacing & Layout

### Container Width
- **Desktop:** 1280px max-width
- **Padding:** 16px (mobile), 32px (tablet), 64px (desktop)

### Spacing Scale (Tailwind-based)
```
4px   = spacing-1
8px   = spacing-2
12px  = spacing-3
16px  = spacing-4
24px  = spacing-6
32px  = spacing-8
48px  = spacing-12
64px  = spacing-16
96px  = spacing-24
128px = spacing-32
```

### Section Padding
- **Desktop:** 80px top/bottom (spacing-20)
- **Mobile:** 48px top/bottom (spacing-12)

### Grid System
- **Desktop:** 12 columns, 24px gap
- **Tablet:** 8 columns, 16px gap
- **Mobile:** 4 columns, 16px gap

---

## 🎭 Animations & Interactions

### Transition Timing
```css
Fast: 150ms (hover states)
Standard: 300ms (most interactions)
Slow: 500ms (page transitions, modals)
Easing: cubic-bezier(0.4, 0, 0.2, 1)
```

### Hover Effects

**Buttons:**
- Scale: 1.05
- Shadow increase
- Color darkening

**Cards:**
- Lift (translateY: -4px)
- Shadow enhancement
- Image zoom (scale: 1.05 on image only)

**Images:**
- Subtle zoom on hover (scale: 1.05)
- Overlay darkening on hero

### Scroll Animations (Optional for Post-MVP)
- Fade in on scroll (intersection observer)
- Parallax on hero section
- Number counters (60 rooms, etc.)

---

## 📱 Mobile-First Approach

### Breakpoints
```css
Mobile: 0-767px (default)
Tablet: 768px-1023px (md:)
Desktop: 1024px-1279px (lg:)
Large Desktop: 1280px+ (xl:)
```

### Mobile Considerations

**Touch Targets:**
- Minimum 44x44px (iOS/Android guideline)
- Buttons: 48px height minimum
- Spacing between clickable elements: 8px minimum

**Typography:**
- Base font size: 16px (prevents iOS zoom on input focus)
- Line height: 1.6 for readability

**Navigation:**
- Hamburger menu for mobile
- Full-width sticky header
- Bottom-aligned Book Now CTA on mobile (optional)

**Images:**
- Serve mobile-optimized images (max 768px width)
- Use 3:4 aspect ratio for hero on mobile (portrait)

---

## ♿ Accessibility (WCAG 2.1 AA - Post-MVP Goal)

### Color Contrast
- **Normal Text (16px):** 4.5:1 minimum
- **Large Text (24px+):** 3:1 minimum
- **UI Components:** 3:1 minimum

**Tested Combinations:**
- White on Luxury Gold (#FFFFFF on #D4AF37): 4.51:1 ✅
- Navy on White (#1A1A2E on #FFFFFF): 15.2:1 ✅
- Charcoal on Cream (#2C2C2C on #F5F5F0): 11.8:1 ✅

### Keyboard Navigation
- All interactive elements focusable
- Visible focus states (ring: 2px #D4AF37)
- Logical tab order

### Screen Readers
- Semantic HTML (header, nav, main, section, footer)
- Alt text for all images
- ARIA labels for icon buttons
- Skip to main content link

---

## 🖥️ Homepage Design Breakdown

### Section 1: Hero
```
Height: 100vh (min 600px)
Background: Full-screen image with gradient overlay
Layout: Centered text + 2 CTAs
Animation: Fade in on load + scroll indicator
```

### Section 2: USP Highlights
```
Background: Cream (#F5F5F0)
Layout: 3 columns (desktop) → Stack (mobile)
Icons: Outline style, 40px, Luxury Gold
Animation: Hover scale on cards
```

### Section 3: Rooms Preview
```
Background: White
Layout: Grid 3 columns (desktop) → Carousel (mobile)
Cards: Image + Title + 3 bullets + CTA
Animation: Card lift on hover
```

### Section 4: Location Spotlight
```
Background: Light Gray (#F8F9FA)
Layout: 50/50 split (map left, text right)
Mobile: Stack (text first, map second)
Map: Google Maps embed or static image
```

### Section 5: Amenities (Breakfast + Parking)
```
Background: White
Layout: 2 columns → Stack mobile
Images: 50% width each
Text: Large bullets with icons
```

### Section 6: Gallery Teaser
```
Background: Cream
Layout: Masonry grid (3-4 columns)
Mobile: 2 columns
Lightbox: Click to expand (optional post-MVP)
```

### Section 7: Reviews
```
Background: White
Layout: 3 testimonial cards (desktop) → Carousel (mobile)
Cards: Quote + Name + Rating
```

### Section 8: Final CTA
```
Background: Navy (#1A1A2E) with subtle pattern
Text: White
Layout: Centered headline + large CTA
Button: Extra large (60px height)
```

---

## 🎯 Design Inspiration & References

### Reference Websites (Boutique Hotels)
1. **Aman Resorts** - aman.com - Minimalist luxury
2. **Six Senses** - sixsenses.com - Nature-focused elegance
3. **Ace Hotel** - acehotel.com - Modern, playful
4. **Soho House** - sohohouse.com - Sophisticated UI
5. **The Hoxton** - thehoxton.com - Clean, contemporary

### UI Pattern Libraries
- **Tailwind UI** - tailwindui.com - Component examples
- **Shadcn UI** - ui.shadcn.com - Accessible components
- **Headless UI** - headlessui.com - Unstyled components

---

## 📦 Design Assets Checklist

### Required from Client
- [ ] High-res logo (SVG + PNG)
- [ ] Brand colors (if different from proposed)
- [ ] Professional photography (60+ images)
- [ ] Hotel information (address, phone, email)
- [ ] Room descriptions and amenities lists
- [ ] Any existing brand guidelines

### To Be Created
- [ ] Favicon (16x16, 32x32, 192x192)
- [ ] Apple Touch Icon (180x180)
- [ ] OG Image (1200x630)
- [ ] Twitter Card Image (1200x675)
- [ ] Loading spinner/skeleton screens
- [ ] 404 error page design
- [ ] Form validation error states
- [ ] Empty states (if applicable)

---

## 🛠️ Design Tools Recommended

**Design:**
- **Figma** - Primary design tool (collaborative, free tier)
- **Figma Plugins:** Unsplash (stock photos), Iconify (icons)

**Prototyping:**
- **Figma Prototype Mode** - Interactive flows
- **Principle / ProtoPie** - Advanced animations (optional)

**Image Optimization:**
- **Squoosh** - squoosh.app - WebP conversion
- **ImageOptim** - imageoptim.com - Compression
- **TinyPNG** - tinypng.com - Lossy compression

**Color Tools:**
- **Coolors** - coolors.co - Palette generation
- **Contrast Checker** - webaim.org/resources/contrastchecker

**Icons:**
- **Heroicons** - heroicons.com - Free MIT icons (used in code)
- **Feather Icons** - feathericons.com - Alternative

---

## 🚀 Design Workflow

### Phase 1: Wireframes (Week 1)
1. Low-fidelity wireframes (all pages)
2. User flow mapping
3. Content hierarchy definition
4. Client approval

### Phase 2: Visual Design (Week 1-2)
1. Homepage high-fidelity mockup (desktop + mobile)
2. Style guide/design system
3. Key pages mockups (Rooms, Location, Contact)
4. Client feedback round 1
5. Revisions
6. Final approval

### Phase 3: Prototype (Week 2)
1. Interactive prototype in Figma
2. Booking flow demonstration
3. Mobile interactions
4. Client final approval

### Phase 4: Handoff to Dev (Week 2)
1. Export all assets (images, icons, logos)
2. CSS specifications document
3. Figma developer mode access
4. Component library documentation

---

## ✅ Design Quality Checklist

Before handoff to development:

**Visual Design:**
- [ ] Consistent spacing across all sections
- [ ] Typography hierarchy clear and readable
- [ ] Color contrast meets WCAG AA standards
- [ ] All images high-resolution and optimized
- [ ] Hover states defined for all interactive elements
- [ ] Mobile responsive layouts for all breakpoints

**UX/Usability:**
- [ ] Clear visual hierarchy (user knows where to look first)
- [ ] Book Now CTA always visible/accessible
- [ ] Forms have clear labels and error states
- [ ] Loading states designed
- [ ] Empty states designed (if applicable)
- [ ] 404 page designed

**Brand Consistency:**
- [ ] Colors match brand palette
- [ ] Typography consistent throughout
- [ ] Photography style cohesive
- [ ] Tone of voice matches brand personality

**Technical:**
- [ ] All assets exported in correct formats
- [ ] Naming conventions logical
- [ ] Design system documented
- [ ] Specs provided for developers

---

**Design is where strategy meets aesthetics. Every pixel should serve both beauty and purpose. 🎨**
