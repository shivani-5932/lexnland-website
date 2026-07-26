# Lex n Land — Landing Website

A premium, luxury real-estate landing page built with **Next.js 14 (App Router)**,
**TypeScript**, **Tailwind CSS**, **GSAP + ScrollTrigger**, **Lenis** smooth scroll,
and **lucide-react** icons — matching the Lex n Land mobile app's brand identity
exactly.

## Brand tokens

| Token       | Hex       |
|-------------|-----------|
| Wine        | `#A63B69` |
| Wine Dark   | `#7F2E50` |
| Soft Pink   | `#F7E8EE` |
| Background  | `#FCFAFB` |
| Text        | `#1D1D1F` |
| Text Soft   | `#6B6B6B` |
| Gold Accent | `#D4AF37` |

Fonts: **Playfair Display** (headings) + **Poppins** (body), loaded via
`next/font/google` and exposed as Tailwind's `font-serif` / `font-sans`.

All tokens live in `tailwind.config.ts` — change them there and the whole site
updates.

## Getting started

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

## Project structure

```
app/
  layout.tsx        Root layout — fonts, loader, cursor, smooth scroll
  page.tsx           Composes every section
  globals.css        Base styles + CSS custom properties
components/
  Navbar.tsx          Sticky glass nav with mobile drawer
  Hero.tsx            Animated headline, 3D-tilt phone mockup with app video
  DownloadSection.tsx Store buttons + QR code (pre-launch)
  LaunchingSoon.tsx   Glass cards + early-access CTA
  Features.tsx        12-feature grid
  HowItWorks.tsx       Interactive 8-step journey with live phone preview
  WhyUs.tsx            Comparison table
  Properties.tsx       Featured property cards
  Testimonials.tsx    Horizontal-scroll testimonial cards
  AppDemo.tsx          Full walkthrough video player
  About.tsx            Mission / vision
  Roadmap.tsx          Founder's future-vision cards
  FAQ.tsx              Accordion
  Contact.tsx          Info panel + form
  Newsletter.tsx      Email capture
  Footer.tsx
  Loader.tsx           Animated logo splash on first paint
  CustomCursor.tsx     Dot + ring cursor (desktop only)
  Reveal.tsx           Reusable GSAP ScrollTrigger fade/slide-in wrapper
  SmoothScrollProvider.tsx   Wires Lenis to GSAP's ticker
lib/
  data.ts              All section copy/content in one place
public/
  logo.png
  videos/hero-loop.mp4   Short looping clip for the hero phone mockup
  videos/app-demo.mp4    Full walkthrough for the App Demo section
```

## Notes & next steps

- **Property photos** are stock Unsplash images — swap in real listings via
  `lib/data.ts` → `PROPERTIES`.
- **Store links & QR code** in `DownloadSection.tsx` point to placeholder URLs —
  update with your real waitlist / App Store / Play Store links.
- **Videos** are already compressed (H.264, muted where used as background loops).
  Replace `public/videos/*.mp4` with new exports if you update the app walkthrough.
- The design uses Tailwind's arbitrary values extensively to hit exact pixel/
  spacing values from the original spec — feel free to consolidate into named
  scale values as the design settles.
- Add `shadcn/ui` components (`npx shadcn@latest init`) if you want prebuilt,
  themeable primitives (dialogs, toasts, etc.) as the product grows.
