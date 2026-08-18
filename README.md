# Pulse — API Health Monitoring for Teams

> Know when your APIs break before your users do.

A premium landing page built for the **Acdyon Technologies Frontend Challenge**.

## 🚀 Live Demo

[View Live Site →](https://pulse-landing.vercel.app) *(deploy URL TBD)*

## ✨ Highlights

- **Zero JavaScript shipped** — Astro compiles to static HTML/CSS, zero framework runtime
- **Full dark mode** — system preference detection + manual toggle, zero-FOUC
- **64KB total page weight** — no bloat, instant load
- **Responsive** — tested at 390px (mobile) and 1440px (desktop)
- **Honest copy** — no fake testimonials, no fabricated user counts, no borrowed logos
- **Easter egg** — try the Konami code (↑↑↓↓←→←→BA)

## 🛠 Tech Stack

| Layer | Choice |
|-------|--------|
| Framework | [Astro](https://astro.build) (static site generator) |
| Styling | CSS Custom Properties + scoped component styles |
| Animations | CSS `@keyframes` + `IntersectionObserver` |
| Fonts | Inter + JetBrains Mono (Google Fonts) |
| Build | Vite (via Astro) |
| Deployment | Vercel / Netlify |

## 📂 Project Structure

```
pulse-landing/
├── src/
│   ├── components/          # All page sections as Astro components
│   │   ├── Navbar.astro     # Sticky nav + dark mode toggle
│   │   ├── Hero.astro       # Hero with animated gradient text
│   │   ├── DashboardMock.astro  # Realistic API dashboard mock
│   │   ├── ProblemSection.astro # Pain point cards
│   │   ├── ProductShowcase.astro # Full dashboard showcase
│   │   ├── Features.astro   # Feature grid with spotlight effect
│   │   ├── HowItWorks.astro # 3-step flow
│   │   ├── CTASection.astro # Waitlist CTA
│   │   └── Footer.astro     # Footer with attribution
│   ├── layouts/
│   │   └── Layout.astro     # Base HTML, meta, zero-FOUC script
│   ├── styles/
│   │   └── global.css       # Design system (tokens, animations)
│   └── pages/
│       └── index.astro      # Main page composition
├── DECISIONS.md             # Required writeup
└── package.json
```

## 🏃 Quick Start

```bash
# Install dependencies
npm install

# Start dev server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## 📋 Assessment Checklist

- [x] Hero section with clear value prop and strong CTA
- [x] Section that **shows** the product (mock dashboard, not just claims)
- [x] Motion/micro-interaction that earns its keep (sparkline animation)
- [x] Working at 390px mobile and 1440px desktop
- [x] Real dark-mode support (all-or-nothing)
- [x] No fabricated testimonials, fake user counts, or fake logos
- [x] DECISIONS.md (1 page max)
- [x] Easter egg (Konami code)

---

*Built with care for the Acdyon Technologies Frontend Challenge.*
