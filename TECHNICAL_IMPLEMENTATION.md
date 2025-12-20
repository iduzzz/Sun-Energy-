# Technical Implementation Guide
**Hotel Website - Next.js + TypeScript + Tailwind CSS**

---

## 📁 Project Structure

```
hotel-website/
├── public/
│   ├── images/
│   │   ├── hero/
│   │   ├── rooms/
│   │   ├── location/
│   │   ├── gallery/
│   │   └── icons/
│   ├── locales/
│   │   ├── en.json
│   │   ├── mk.json
│   │   └── sq.json
│   └── favicon.ico
│
├── src/
│   ├── app/
│   │   ├── [locale]/
│   │   │   ├── layout.tsx
│   │   │   ├── page.tsx (Home)
│   │   │   ├── rooms/
│   │   │   │   ├── page.tsx
│   │   │   │   └── [slug]/page.tsx
│   │   │   ├── location/
│   │   │   │   └── page.tsx
│   │   │   ├── contact/
│   │   │   │   └── page.tsx
│   │   │   └── policies/
│   │   │       └── page.tsx
│   │   ├── api/
│   │   │   └── contact/
│   │   │       └── route.ts
│   │   └── globals.css
│   │
│   ├── components/
│   │   ├── layout/
│   │   │   ├── Header.tsx
│   │   │   ├── Footer.tsx
│   │   │   └── LanguageSwitcher.tsx
│   │   ├── home/
│   │   │   ├── HeroSection.tsx
│   │   │   ├── USPHighlights.tsx
│   │   │   ├── RoomsPreview.tsx
│   │   │   ├── LocationSpotlight.tsx
│   │   │   ├── AmenitiesSection.tsx
│   │   │   ├── GalleryTeaser.tsx
│   │   │   ├── ReviewsSection.tsx
│   │   │   └── FinalCTA.tsx
│   │   ├── shared/
│   │   │   ├── BookNowButton.tsx
│   │   │   ├── RoomCard.tsx
│   │   │   ├── ContactForm.tsx
│   │   │   └── ImageGallery.tsx
│   │   └── analytics/
│   │       └── GA4Events.tsx
│   │
│   ├── lib/
│   │   ├── i18n.ts
│   │   ├── gtag.ts
│   │   └── constants.ts
│   │
│   └── types/
│       └── index.ts
│
├── next.config.js
├── tailwind.config.js
├── tsconfig.json
└── package.json
```

---

## 🚀 Setup & Installation

### 1. Initialize Project

```bash
npx create-next-app@latest hotel-website --typescript --tailwind --app
cd hotel-website
```

### 2. Install Dependencies

```bash
npm install next-intl
npm install @heroicons/react
npm install clsx tailwind-merge
npm install react-hook-form
npm install @emailjs/browser
npm install --save-dev @types/node
```

### 3. Configure `next.config.js`

```javascript
/** @type {import('next').NextConfig} */
const withNextIntl = require('next-intl/plugin')();

const nextConfig = {
  images: {
    formats: ['image/webp'],
    remotePatterns: [
      {
        protocol: 'https',
        hostname: 'yourdomain.com',
      },
    ],
  },
  // Optimize for production
  compiler: {
    removeConsole: process.env.NODE_ENV === 'production',
  },
  // Headers for security
  async headers() {
    return [
      {
        source: '/:path*',
        headers: [
          {
            key: 'X-DNS-Prefetch-Control',
            value: 'on'
          },
          {
            key: 'Strict-Transport-Security',
            value: 'max-age=63072000; includeSubDomains; preload'
          },
          {
            key: 'X-Frame-Options',
            value: 'SAMEORIGIN'
          },
          {
            key: 'X-Content-Type-Options',
            value: 'nosniff'
          },
          {
            key: 'Referrer-Policy',
            value: 'origin-when-cross-origin'
          }
        ]
      }
    ];
  }
};

module.exports = withNextIntl(nextConfig);
```

---

## 🌍 Multi-language Configuration

### `src/lib/i18n.ts`

```typescript
import {notFound} from 'next/navigation';
import {getRequestConfig} from 'next-intl/server';

export const locales = ['en', 'mk', 'sq'] as const;
export type Locale = (typeof locales)[number];

export default getRequestConfig(async ({locale}) => {
  if (!locales.includes(locale as Locale)) notFound();

  return {
    messages: (await import(`../../public/locales/${locale}.json`)).default
  };
});
```

### `src/middleware.ts`

```typescript
import createMiddleware from 'next-intl/middleware';
import {locales} from './lib/i18n';

export default createMiddleware({
  locales,
  defaultLocale: 'en',
  localePrefix: 'as-needed'
});

export const config = {
  matcher: ['/((?!api|_next|_vercel|.*\\..*).*)']
};
```

### Translation Files

**`public/locales/en.json`**
```json
{
  "hero": {
    "headline": "Your Gateway to Skopje's Historic Heart",
    "subheadline": "Modern comfort meets centuries-old charm. 60 stylish rooms, free parking, and the Old Bazaar at your doorstep.",
    "cta": "Book Your Stay"
  },
  "usp": {
    "location": {
      "title": "Old Bazaar Steps Away",
      "description": "Walk to Skopje's historic heart in 2 minutes"
    },
    "parking": {
      "title": "Free Parking Included",
      "description": "Complimentary secure parking for all guests"
    },
    "breakfast": {
      "title": "Daily Breakfast",
      "description": "Start your day with complimentary breakfast"
    }
  },
  "rooms": {
    "title": "Modern Comfort Awaits",
    "viewAll": "See All Rooms"
  },
  "booking": {
    "bookNow": "Book Now",
    "bestRate": "Best rates guaranteed when you book direct"
  }
}
```

**`public/locales/mk.json`**
```json
{
  "hero": {
    "headline": "Вашиот Премин кон Историското Срце на Скопје",
    "subheadline": "Модерен комфор среќава вековна шарм. 60 стилски соби, бесплатен паркинг и Старата Чаршија пред ваши врати.",
    "cta": "Резервирајте Престој"
  },
  "usp": {
    "location": {
      "title": "Стара Чаршија на Чекори",
      "description": "Прошетајте до историското срце на Скопје за 2 минути"
    },
    "parking": {
      "title": "Бесплатен Паркинг",
      "description": "Комплиментарен сигурен паркинг за сите гости"
    },
    "breakfast": {
      "title": "Дневен Појадок",
      "description": "Започнете го денот со бесплатен појадок"
    }
  },
  "rooms": {
    "title": "Модерен Комфор Ве Чека",
    "viewAll": "Видете Ги Сите Соби"
  },
  "booking": {
    "bookNow": "Резервирајте Сега",
    "bestRate": "Најдобри цени гарантирани при директна резервација"
  }
}
```

**`public/locales/sq.json`**
```json
{
  "hero": {
    "headline": "Porta Juaj drejt Zemrës Historike të Shkupit",
    "subheadline": "Komoditeti modern takon sharmin shekullor. 60 dhoma moderne, parking falas dhe Çarshia e Vjetër para derës tuaj.",
    "cta": "Rezervo Qëndrimin"
  },
  "usp": {
    "location": {
      "title": "Çarshia e Vjetër Në Hapa",
      "description": "Ecni drejt zemrës historike të Shkupit në 2 minuta"
    },
    "parking": {
      "title": "Parking Falas",
      "description": "Parking i sigurt falas për të gjithë mysafirët"
    },
    "breakfast": {
      "title": "Mëngjes Ditor",
      "description": "Filloni ditën me mëngjes falas"
    }
  },
  "rooms": {
    "title": "Komoditeti Modern Ju Pret",
    "viewAll": "Shiko Të Gjitha Dhomat"
  },
  "booking": {
    "bookNow": "Rezervo Tani",
    "bestRate": "Tarifat më të mira të garantuara kur rezervoni direkt"
  }
}
```

---

## 🎨 Tailwind Configuration

### `tailwind.config.js`

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    './src/pages/**/*.{js,ts,jsx,tsx,mdx}',
    './src/components/**/*.{js,ts,jsx,tsx,mdx}',
    './src/app/**/*.{js,ts,jsx,tsx,mdx}',
  ],
  theme: {
    extend: {
      colors: {
        primary: {
          50: '#f0f9ff',
          100: '#e0f2fe',
          500: '#0ea5e9',
          600: '#0284c7',
          700: '#0369a1',
          900: '#0c4a6e',
        },
        luxury: {
          gold: '#D4AF37',
          darkGold: '#B8950A',
          navy: '#1a1a2e',
          cream: '#f5f5f0',
        }
      },
      fontFamily: {
        sans: ['Inter', 'system-ui', 'sans-serif'],
        serif: ['Playfair Display', 'serif'],
      },
      boxShadow: {
        'luxury': '0 10px 40px rgba(212, 175, 55, 0.1)',
      }
    },
  },
  plugins: [
    require('@tailwindcss/forms'),
    require('@tailwindcss/typography'),
  ],
}
```

---

## 🔧 Core Components

### 1. Book Now Button Component

**`src/components/shared/BookNowButton.tsx`**

```typescript
'use client';

import { useLocale } from 'next-intl';
import { trackEvent } from '@/lib/gtag';

interface BookNowButtonProps {
  roomType?: string;
  location?: 'header' | 'hero' | 'footer' | 'room-page';
  className?: string;
  children: React.ReactNode;
}

const DEDGE_BASE_URL = 'https://www.secure-hotel-booking.com/Hotel-De-KOKA/2DGL';
const HOTEL_ID = '15117';

const getLocaleCode = (locale: string): string => {
  const localeMap: Record<string, string> = {
    'en': 'en-US',
    'mk': 'mk-MK',  // ASSUMPTION: Verify with D-EDGE
    'sq': 'sq-AL',  // ASSUMPTION: Verify with D-EDGE
  };
  return localeMap[locale] || 'en-US';
};

export default function BookNowButton({
  roomType = 'general',
  location = 'hero',
  className = '',
  children
}: BookNowButtonProps) {
  const locale = useLocale();
  const localeCode = getLocaleCode(locale);

  const bookingUrl = `${DEDGE_BASE_URL}/${localeCode}?hotelId=${HOTEL_ID}`;

  const handleClick = () => {
    // Track click event
    trackEvent({
      action: 'click_book_now',
      category: 'Booking',
      label: roomType,
      value: 1,
      params: {
        room_type: roomType,
        cta_location: location,
        language: locale,
      }
    });

    // Track outbound link
    trackEvent({
      action: 'outbound_booking_engine',
      category: 'Outbound Link',
      label: 'D-EDGE Booking Engine',
      params: {
        destination: 'D-EDGE',
        room_type: roomType,
        language: locale,
      }
    });
  };

  return (
    <a
      href={bookingUrl}
      target="_blank"
      rel="noopener noreferrer"
      onClick={handleClick}
      className={`inline-flex items-center justify-center px-8 py-4 bg-luxury-gold hover:bg-luxury-darkGold text-white font-semibold rounded-lg transition-all duration-300 shadow-lg hover:shadow-xl transform hover:scale-105 ${className}`}
    >
      {children}
    </a>
  );
}
```

---

### 2. Header with Sticky Book Now

**`src/components/layout/Header.tsx`**

```typescript
'use client';

import { useState, useEffect } from 'react';
import { useTranslations, useLocale } from 'next-intl';
import Link from 'next/link';
import { usePathname } from 'next/navigation';
import BookNowButton from '../shared/BookNowButton';
import LanguageSwitcher from './LanguageSwitcher';

export default function Header() {
  const t = useTranslations();
  const locale = useLocale();
  const pathname = usePathname();
  const [isScrolled, setIsScrolled] = useState(false);
  const [isMobileMenuOpen, setIsMobileMenuOpen] = useState(false);

  useEffect(() => {
    const handleScroll = () => {
      setIsScrolled(window.scrollY > 50);
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  const navLinks = [
    { href: `/${locale}`, label: t('nav.home') },
    { href: `/${locale}/rooms`, label: t('nav.rooms') },
    { href: `/${locale}/location`, label: t('nav.location') },
    { href: `/${locale}/contact`, label: t('nav.contact') },
  ];

  return (
    <header
      className={`fixed top-0 left-0 right-0 z-50 transition-all duration-300 ${
        isScrolled
          ? 'bg-white shadow-lg py-3'
          : 'bg-transparent py-5'
      }`}
    >
      <div className="container mx-auto px-4">
        <div className="flex items-center justify-between">
          {/* Logo */}
          <Link href={`/${locale}`} className="flex items-center">
            <span className={`text-2xl font-bold transition-colors ${
              isScrolled ? 'text-luxury-navy' : 'text-white'
            }`}>
              Hotel De KOKA
            </span>
          </Link>

          {/* Desktop Navigation */}
          <nav className="hidden lg:flex items-center space-x-8">
            {navLinks.map((link) => (
              <Link
                key={link.href}
                href={link.href}
                className={`font-medium transition-colors ${
                  isScrolled
                    ? 'text-gray-700 hover:text-luxury-gold'
                    : 'text-white hover:text-luxury-gold'
                } ${pathname === link.href ? 'text-luxury-gold' : ''}`}
              >
                {link.label}
              </Link>
            ))}
          </nav>

          {/* Right Section */}
          <div className="flex items-center space-x-4">
            <LanguageSwitcher isScrolled={isScrolled} />
            <BookNowButton location="header" className="hidden md:inline-flex">
              {t('booking.bookNow')}
            </BookNowButton>

            {/* Mobile Menu Toggle */}
            <button
              onClick={() => setIsMobileMenuOpen(!isMobileMenuOpen)}
              className="lg:hidden p-2"
              aria-label="Toggle menu"
            >
              <svg
                className={`w-6 h-6 ${isScrolled ? 'text-gray-900' : 'text-white'}`}
                fill="none"
                strokeLinecap="round"
                strokeLinejoin="round"
                strokeWidth="2"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                {isMobileMenuOpen ? (
                  <path d="M6 18L18 6M6 6l12 12" />
                ) : (
                  <path d="M4 6h16M4 12h16M4 18h16" />
                )}
              </svg>
            </button>
          </div>
        </div>

        {/* Mobile Menu */}
        {isMobileMenuOpen && (
          <div className="lg:hidden mt-4 pb-4 border-t border-gray-200">
            <nav className="flex flex-col space-y-3 pt-4">
              {navLinks.map((link) => (
                <Link
                  key={link.href}
                  href={link.href}
                  onClick={() => setIsMobileMenuOpen(false)}
                  className="text-gray-700 hover:text-luxury-gold font-medium"
                >
                  {link.label}
                </Link>
              ))}
              <BookNowButton location="header" className="w-full mt-4">
                {t('booking.bookNow')}
              </BookNowButton>
            </nav>
          </div>
        )}
      </div>
    </header>
  );
}
```

---

### 3. Hero Section

**`src/components/home/HeroSection.tsx`**

```typescript
'use client';

import { useTranslations } from 'next-intl';
import Image from 'next/image';
import BookNowButton from '../shared/BookNowButton';

export default function HeroSection() {
  const t = useTranslations('hero');

  return (
    <section className="relative h-screen min-h-[600px] flex items-center justify-center">
      {/* Background Image */}
      <div className="absolute inset-0 z-0">
        <Image
          src="/images/hero/hotel-main.jpg"
          alt="Hotel De KOKA"
          fill
          priority
          quality={90}
          className="object-cover"
          sizes="100vw"
        />
        {/* Gradient Overlay */}
        <div className="absolute inset-0 bg-gradient-to-r from-black/60 to-black/30" />
      </div>

      {/* Content */}
      <div className="relative z-10 container mx-auto px-4 text-center text-white">
        <h1 className="text-4xl md:text-6xl lg:text-7xl font-serif font-bold mb-6 animate-fade-in">
          {t('headline')}
        </h1>
        <p className="text-lg md:text-xl lg:text-2xl mb-10 max-w-3xl mx-auto opacity-90">
          {t('subheadline')}
        </p>

        <div className="flex flex-col sm:flex-row gap-4 justify-center items-center">
          <BookNowButton location="hero" className="text-lg px-10 py-5">
            {t('cta')}
          </BookNowButton>
          <button
            onClick={() => {
              document.getElementById('rooms-section')?.scrollIntoView({
                behavior: 'smooth'
              });
            }}
            className="px-10 py-5 border-2 border-white text-white font-semibold rounded-lg hover:bg-white hover:text-luxury-navy transition-all duration-300"
          >
            {t('exploreRooms')}
          </button>
        </div>
      </div>

      {/* Scroll Indicator */}
      <div className="absolute bottom-8 left-1/2 transform -translate-x-1/2 z-10">
        <div className="animate-bounce">
          <svg
            className="w-6 h-6 text-white"
            fill="none"
            strokeLinecap="round"
            strokeLinejoin="round"
            strokeWidth="2"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path d="M19 14l-7 7m0 0l-7-7m7 7V3" />
          </svg>
        </div>
      </div>
    </section>
  );
}
```

---

### 4. USP Highlights Section

**`src/components/home/USPHighlights.tsx`**

```typescript
import { useTranslations } from 'next-intl';
import { MapPinIcon, TruckIcon, CakeIcon } from '@heroicons/react/24/outline';

const uspItems = [
  {
    icon: MapPinIcon,
    key: 'location',
  },
  {
    icon: TruckIcon,
    key: 'parking',
  },
  {
    icon: CakeIcon,
    key: 'breakfast',
  },
];

export default function USPHighlights() {
  const t = useTranslations('usp');

  return (
    <section className="py-20 bg-luxury-cream">
      <div className="container mx-auto px-4">
        <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
          {uspItems.map((item) => {
            const Icon = item.icon;
            return (
              <div
                key={item.key}
                className="text-center group hover:transform hover:scale-105 transition-all duration-300"
              >
                <div className="inline-flex items-center justify-center w-20 h-20 mb-6 bg-luxury-gold rounded-full group-hover:bg-luxury-darkGold transition-colors">
                  <Icon className="w-10 h-10 text-white" />
                </div>
                <h3 className="text-2xl font-semibold mb-3 text-luxury-navy">
                  {t(`${item.key}.title`)}
                </h3>
                <p className="text-gray-600 text-lg">
                  {t(`${item.key}.description`)}
                </p>
              </div>
            );
          })}
        </div>
      </div>
    </section>
  );
}
```

---

### 5. Google Analytics Tracking

**`src/lib/gtag.ts`**

```typescript
export const GA_TRACKING_ID = process.env.NEXT_PUBLIC_GA_ID || '';

// https://developers.google.com/analytics/devguides/collection/gtagjs/pages
export const pageview = (url: string) => {
  if (typeof window !== 'undefined' && window.gtag) {
    window.gtag('config', GA_TRACKING_ID, {
      page_path: url,
    });
  }
};

interface GtagEvent {
  action: string;
  category: string;
  label: string;
  value?: number;
  params?: Record<string, any>;
}

// https://developers.google.com/analytics/devguides/collection/gtagjs/events
export const trackEvent = ({ action, category, label, value, params }: GtagEvent) => {
  if (typeof window !== 'undefined' && window.gtag) {
    window.gtag('event', action, {
      event_category: category,
      event_label: label,
      value: value,
      ...params,
    });
  }
};

// Track scroll depth
export const trackScrollDepth = (percentage: number) => {
  trackEvent({
    action: 'scroll_depth',
    category: 'Engagement',
    label: `${percentage}%`,
    params: {
      scroll_percentage: percentage,
      page_path: window.location.pathname,
    },
  });
};

// Track form submission
export const trackFormSubmit = (formType: string) => {
  trackEvent({
    action: 'form_submit',
    category: 'Lead Generation',
    label: formType,
    params: {
      form_type: formType,
      language: document.documentElement.lang,
    },
  });
};

// Track language switch
export const trackLanguageSwitch = (fromLang: string, toLang: string) => {
  trackEvent({
    action: 'language_switch',
    category: 'User Preference',
    label: `${fromLang} to ${toLang}`,
    params: {
      from_language: fromLang,
      to_language: toLang,
    },
  });
};

declare global {
  interface Window {
    gtag: (
      command: 'config' | 'event' | 'set',
      targetId: string,
      config?: Record<string, any>
    ) => void;
  }
}
```

**`src/app/[locale]/layout.tsx`** (GA4 Script)

```typescript
import Script from 'next/script';
import { GA_TRACKING_ID } from '@/lib/gtag';

export default function RootLayout({
  children,
  params: { locale }
}: {
  children: React.ReactNode;
  params: { locale: string };
}) {
  return (
    <html lang={locale}>
      <head>
        {/* Google Analytics */}
        <Script
          strategy="afterInteractive"
          src={`https://www.googletagmanager.com/gtag/js?id=${GA_TRACKING_ID}`}
        />
        <Script
          id="gtag-init"
          strategy="afterInteractive"
          dangerouslySetInnerHTML={{
            __html: `
              window.dataLayer = window.dataLayer || [];
              function gtag(){dataLayer.push(arguments);}
              gtag('js', new Date());
              gtag('config', '${GA_TRACKING_ID}', {
                page_path: window.location.pathname,
              });
            `,
          }}
        />
      </head>
      <body>{children}</body>
    </html>
  );
}
```

---

## 📧 Contact Form Implementation

**`src/components/shared/ContactForm.tsx`**

```typescript
'use client';

import { useState } from 'react';
import { useForm } from 'react-hook-form';
import { useTranslations } from 'next-intl';
import { trackFormSubmit } from '@/lib/gtag';

interface FormData {
  name: string;
  email: string;
  phone: string;
  message: string;
}

export default function ContactForm() {
  const t = useTranslations('contact');
  const [isSubmitting, setIsSubmitting] = useState(false);
  const [submitStatus, setSubmitStatus] = useState<'idle' | 'success' | 'error'>('idle');

  const {
    register,
    handleSubmit,
    reset,
    formState: { errors },
  } = useForm<FormData>();

  const onSubmit = async (data: FormData) => {
    setIsSubmitting(true);
    setSubmitStatus('idle');

    try {
      // Send to API route
      const response = await fetch('/api/contact', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify(data),
      });

      if (response.ok) {
        setSubmitStatus('success');
        trackFormSubmit('contact');
        reset();
      } else {
        setSubmitStatus('error');
      }
    } catch (error) {
      setSubmitStatus('error');
    } finally {
      setIsSubmitting(false);
    }
  };

  return (
    <form onSubmit={handleSubmit(onSubmit)} className="space-y-6">
      {/* Name */}
      <div>
        <label htmlFor="name" className="block text-sm font-medium text-gray-700 mb-2">
          {t('form.name')}
        </label>
        <input
          type="text"
          id="name"
          {...register('name', { required: t('form.nameRequired') })}
          className="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-luxury-gold focus:border-transparent"
        />
        {errors.name && (
          <p className="mt-1 text-sm text-red-600">{errors.name.message}</p>
        )}
      </div>

      {/* Email */}
      <div>
        <label htmlFor="email" className="block text-sm font-medium text-gray-700 mb-2">
          {t('form.email')}
        </label>
        <input
          type="email"
          id="email"
          {...register('email', {
            required: t('form.emailRequired'),
            pattern: {
              value: /^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}$/i,
              message: t('form.emailInvalid'),
            },
          })}
          className="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-luxury-gold focus:border-transparent"
        />
        {errors.email && (
          <p className="mt-1 text-sm text-red-600">{errors.email.message}</p>
        )}
      </div>

      {/* Phone */}
      <div>
        <label htmlFor="phone" className="block text-sm font-medium text-gray-700 mb-2">
          {t('form.phone')}
        </label>
        <input
          type="tel"
          id="phone"
          {...register('phone')}
          className="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-luxury-gold focus:border-transparent"
        />
      </div>

      {/* Message */}
      <div>
        <label htmlFor="message" className="block text-sm font-medium text-gray-700 mb-2">
          {t('form.message')}
        </label>
        <textarea
          id="message"
          rows={5}
          {...register('message', { required: t('form.messageRequired') })}
          className="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-luxury-gold focus:border-transparent"
        />
        {errors.message && (
          <p className="mt-1 text-sm text-red-600">{errors.message.message}</p>
        )}
      </div>

      {/* Submit Button */}
      <button
        type="submit"
        disabled={isSubmitting}
        className="w-full px-8 py-4 bg-luxury-gold hover:bg-luxury-darkGold text-white font-semibold rounded-lg transition-all duration-300 disabled:opacity-50 disabled:cursor-not-allowed"
      >
        {isSubmitting ? t('form.sending') : t('form.submit')}
      </button>

      {/* Status Messages */}
      {submitStatus === 'success' && (
        <div className="p-4 bg-green-50 border border-green-200 rounded-lg">
          <p className="text-green-800">{t('form.successMessage')}</p>
        </div>
      )}
      {submitStatus === 'error' && (
        <div className="p-4 bg-red-50 border border-red-200 rounded-lg">
          <p className="text-red-800">{t('form.errorMessage')}</p>
        </div>
      )}
    </form>
  );
}
```

**`src/app/api/contact/route.ts`**

```typescript
import { NextRequest, NextResponse } from 'next/server';

export async function POST(request: NextRequest) {
  try {
    const body = await request.json();
    const { name, email, phone, message } = body;

    // Validate input
    if (!name || !email || !message) {
      return NextResponse.json(
        { error: 'Missing required fields' },
        { status: 400 }
      );
    }

    // Send email using EmailJS or similar service
    // For now, we'll just log it (replace with actual email service)
    console.log('Contact form submission:', { name, email, phone, message });

    // Example: Using EmailJS
    /*
    const response = await fetch('https://api.emailjs.com/api/v1.0/email/send', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify({
        service_id: process.env.EMAILJS_SERVICE_ID,
        template_id: process.env.EMAILJS_TEMPLATE_ID,
        user_id: process.env.EMAILJS_PUBLIC_KEY,
        template_params: {
          from_name: name,
          from_email: email,
          phone: phone,
          message: message,
        },
      }),
    });
    */

    return NextResponse.json(
      { message: 'Email sent successfully' },
      { status: 200 }
    );
  } catch (error) {
    console.error('Contact form error:', error);
    return NextResponse.json(
      { error: 'Failed to send email' },
      { status: 500 }
    );
  }
}
```

---

## 🔍 SEO Implementation

**`src/app/[locale]/layout.tsx`** (Complete with SEO)

```typescript
import { Metadata } from 'next';
import { notFound } from 'next/navigation';
import { NextIntlClientProvider } from 'next-intl';
import { locales } from '@/lib/i18n';
import Header from '@/components/layout/Header';
import Footer from '@/components/layout/Footer';
import './globals.css';

export function generateStaticParams() {
  return locales.map((locale) => ({ locale }));
}

export async function generateMetadata({
  params: { locale }
}: {
  params: { locale: string };
}): Promise<Metadata> {
  const messages = await import(`../../../public/locales/${locale}.json`);

  return {
    title: messages.default.meta.title,
    description: messages.default.meta.description,
    openGraph: {
      title: messages.default.meta.title,
      description: messages.default.meta.description,
      url: `https://yourdomain.com/${locale === 'en' ? '' : locale}`,
      siteName: 'Hotel De KOKA',
      images: [
        {
          url: 'https://yourdomain.com/og-image.jpg',
          width: 1200,
          height: 630,
        },
      ],
      locale: locale,
      type: 'website',
    },
    twitter: {
      card: 'summary_large_image',
      title: messages.default.meta.title,
      description: messages.default.meta.description,
      images: ['https://yourdomain.com/twitter-image.jpg'],
    },
    alternates: {
      canonical: `https://yourdomain.com/${locale === 'en' ? '' : locale}`,
      languages: {
        'en': 'https://yourdomain.com/',
        'mk': 'https://yourdomain.com/mk',
        'sq': 'https://yourdomain.com/sq',
      },
    },
  };
}

export default async function LocaleLayout({
  children,
  params: { locale }
}: {
  children: React.ReactNode;
  params: { locale: string };
}) {
  let messages;
  try {
    messages = (await import(`../../../public/locales/${locale}.json`)).default;
  } catch (error) {
    notFound();
  }

  return (
    <html lang={locale}>
      <body>
        <NextIntlClientProvider locale={locale} messages={messages}>
          <Header />
          <main>{children}</main>
          <Footer />
        </NextIntlClientProvider>

        {/* Schema.org JSON-LD */}
        <script
          type="application/ld+json"
          dangerouslySetInnerHTML={{
            __html: JSON.stringify({
              '@context': 'https://schema.org',
              '@type': 'Hotel',
              name: 'Hotel De KOKA',
              description: messages.meta.description,
              image: 'https://yourdomain.com/hotel-main.jpg',
              address: {
                '@type': 'PostalAddress',
                streetAddress: '[Your Street Address]',
                addressLocality: 'Skopje',
                addressRegion: 'Skopje',
                postalCode: '[Postal Code]',
                addressCountry: 'MK',
              },
              geo: {
                '@type': 'GeoCoordinates',
                latitude: 42.0000,
                longitude: 21.0000,
              },
              telephone: '+389-XX-XXX-XXX',
              email: 'info@hotelname.com',
              starRating: {
                '@type': 'Rating',
                ratingValue: '4',
              },
              priceRange: '$$',
              amenityFeature: [
                { '@type': 'LocationFeatureSpecification', name: 'Free Parking', value: true },
                { '@type': 'LocationFeatureSpecification', name: 'Free Breakfast', value: true },
                { '@type': 'LocationFeatureSpecification', name: 'Free WiFi', value: true },
              ],
              url: 'https://yourdomain.com',
            }),
          }}
        />
      </body>
    </html>
  );
}
```

---

## 🚀 Deployment

### Vercel Deployment (Recommended)

1. **Push code to GitHub**

```bash
git init
git add .
git commit -m "Initial hotel website commit"
git branch -M main
git remote add origin https://github.com/yourusername/hotel-website.git
git push -u origin main
```

2. **Deploy to Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Import GitHub repository
   - Framework Preset: Next.js
   - Add environment variables:
     - `NEXT_PUBLIC_GA_ID`: Your GA4 ID
     - `EMAILJS_SERVICE_ID`: EmailJS service ID
     - `EMAILJS_TEMPLATE_ID`: EmailJS template ID
     - `EMAILJS_PUBLIC_KEY`: EmailJS public key

3. **Connect Custom Domain**
   - Add your domain in Vercel dashboard
   - Update DNS records as instructed

---

## ✅ Pre-Launch Checklist

- [ ] All translations complete (EN/MK/SQ)
- [ ] D-EDGE booking URL tested in all languages
- [ ] GA4 tracking verified in Google Analytics
- [ ] All images optimized (WebP format)
- [ ] Contact form sending emails successfully
- [ ] Mobile responsive on iOS/Android
- [ ] Core Web Vitals green (Lighthouse 90+)
- [ ] Schema.org markup validated
- [ ] Sitemap.xml generated and submitted
- [ ] SSL certificate active
- [ ] 404 page created
- [ ] Privacy policy page added
- [ ] Cookie consent banner (if needed for GDPR)
- [ ] Social media meta tags verified
- [ ] Favicon added
- [ ] Google Search Console verified

---

**Ready to build! 🚀**
