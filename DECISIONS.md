# DECISIONS.md

## 1. Why this strategy over the obvious alternative I rejected

**Chosen:** Astro (static site generator) + vanilla CSS custom properties + minimal vanilla JS  
**Rejected:** React SPA with a component library (e.g., Next.js + shadcn/ui)

A landing page has one job: load fast and convert. React ships a JavaScript runtime to the browser for interactivity the page doesn't need every section here is static HTML/CSS with two small scripts (theme toggle + scroll reveal). Astro compiles to zero-JS static HTML by default, which means:

- **~0 KB of framework JS shipped** (vs. ~80KB+ for React)
- Lighthouse Performance score stays above 95 without heroic optimization
- No hydration delay, the page is interactive on first paint

I also rejected using Tailwind utility classes exclusively for styling. While Tailwind handles layout and spacing well, the premium "shipped" details layered `box-shadow` with inner specular highlights, `radial-gradient` spotlight effects on mouse-move, SVG sparkline animations require custom CSS that would be unreadable as utility strings. I used CSS custom properties as the design-system backbone (colors, typography, spacing, animation curves) and scoped `<style>` blocks per component for everything else.

The product concept ("Pulse" as a pre-launch API monitor) was chosen specifically to solve the honesty constraint. A pre-launch waitlist page doesn't need fake testimonials, fabricated user counts, or borrowed logos. "Join the Waitlist" and "Launching Soon" are true statements, not marketing fiction.

## 2. One trade-off I made under the time limit

The dashboard mock in the hero and product showcase is built entirely in HTML/CSS with hardcoded data. With a real week, I would:

- **Build the response-time chart with D3.js or Chart.js**, feeding it realistic time-series data with smooth interpolation and interactive tooltips on hover
- **Add real form submission** — wire the waitlist form to Supabase or Airtable with a confirmation toast and error handling
- **Run a full accessibility audit** — screen reader testing, ARIA landmarks, keyboard navigation flow, color contrast verification with axe-core
- **Add page load animation choreography** — staggered entrance of hero elements (badge → headline → subheadline → CTAs → dashboard) with precise timing, rather than a single fade-up

## 3. Where I used AI tools and what I verified

**AI-assisted areas:**
- Initial project scaffolding and component file generation (parallel build across multiple components)
- SVG icon paths (heartbeat, bell, shield, grid icons)
- CSS animation keyframes (sparkline draw, pulse-dot, floating)
- Boilerplate HTML structure for repetitive sections (feature cards, endpoint rows)

**What I personally verified and changed:**
- **Design system values** — every color, spacing token, font size, and animation curve was hand-specified based on research into Linear, Raycast, and Supabase design patterns (not defaults)
- **Dark mode completeness** — tested that every element uses CSS custom properties, zero hardcoded colors remain
- **The "shipped vs. scaffolded" details** — inner top specular highlights on cards (`inset 0 1px 0 rgba(255,255,255,0.08)`), noise texture overlay, negative letter-spacing on headings, `text-wrap: balance`, `color-mix()` for translucent navbar, zero-FOUC inline theme script
- **Mouse-tracking spotlight** — verified the radial-gradient approach is GPU-composited and doesn't cause layout thrashing
- **Gradient text fix** — replaced a near-invisible primary→secondary gradient with the vibrant accent→purple→pink animated gradient
- **Honesty audit** — verified zero fake testimonials, zero fake user counts, zero borrowed logos, meta-honest footer attribution
- **Copy quality** — every headline and description was reviewed for clarity, specificity, and honest framing
