# Aethercraft — Personal Space Vehicles Website

## Concept & Vision

Aethercraft is a premium personal spaceship company, positioned like Porsche or Rolls-Royce translated 50 years forward. The website is cinematic, dark, luxurious — not cartoonish sci-fi but realistic near-future aerospace elegance. Every interaction should feel like handling precision engineering. The brand exudes confidence, heritage, and technological mastery.

## Design Language

### Aesthetic Direction
Dark cinematic luxury — deep space blacks, brushed titanium surfaces, holographic cyan accents. Inspired by: Porsche's configurator, Rolls-Royce's website, Apple spatial computing aesthetics, NASA concept art. Premium without being gaudy; futuristic without being cartoonish.

### Color Palette
- **Void Black:** `#050510` — deep space background
- **Panel Dark:** `#0d1117` — card/section backgrounds
- **Titanium Gold:** `#c9a84c` — accent, premium highlights
- **Hologram Cyan:** `#4ecdc4` — interactive elements, data displays
- **Text Primary:** `#f0f0f0` — main text
- **Text Secondary:** `#8b949e` — subdued text
- **Wireframe Blue:** `#58a6ff` — technical drawings, specs

### Typography
- **Headings:** Instrument Serif (Google Fonts) — elegant, editorial authority
- **Body:** DM Sans (Google Fonts) — clean, geometric, highly legible
- **Technical/Specs:** JetBrains Mono (Google Fonts) — monospace for specs and data

### Spatial System
- Base unit: 8px
- Section padding: 120px vertical (desktop), 80px (mobile)
- Content max-width: 1400px
- Card gaps: 32px

### Motion Philosophy
- **Page load:** Ship materializes from wireframe — opacity 0→1 with stroke-dashoffset animation (1.5s)
- **Scroll reveals:** Elements fade up with 60px translate, 0.8s ease-out, staggered 100ms
- **Parallax:** Starfield layers at different speeds (0.1x, 0.3x, 0.5x scroll)
- **Hover states:** 300ms transitions, subtle scale (1.02) and glow effects
- **Configurator toggles:** Smooth 200ms state changes

### Visual Assets
- **Starfield:** Canvas-based animated starfield with 3 depth layers
- **Icons:** Inline SVG only — no emoji
- **Ship images:** Atmospheric dark photography placeholders with gradient overlays
- **Decorative:** Subtle grid patterns, scan lines, corner accents

## Layout & Structure

### Page Architecture
1. **Hero** — Full viewport, starfield canvas, centered logo + tagline + flagship silhouette CTA
2. **Ship Lineup** — Vertical scroll, 5 ship cards in size ascending order
3. **Technology** — 3-column pillar section with icons and descriptions
4. **Configure** — Interactive ship builder with color/interior/package toggles
5. **Heritage** — Split layout: story left, founding details right
6. **Footer** — Minimal: logo, legal links, social icons, contact

### Responsive Strategy
- Mobile-first CSS
- Breakpoints: 480px, 768px, 1024px, 1280px
- Ship cards stack vertically on mobile
- Configurator becomes scrollable horizontal on mobile

## Features & Interactions

### Hero
- Starfield canvas with 3 parallax layers
- Logo fades in from wireframe (stroke animation)
- Tagline types in character-by-character
- "Explore the Fleet" CTA pulses subtly
- Mouse movement creates subtle parallax shift on ship silhouette

### Ship Lineup
- Each ship card: full-width, cinematic image background
- Hover: card lifts (translateY -8px), specs panel expands
- "Configure" button opens configure section with that ship pre-selected
- Scroll-triggered reveal: cards fade up as they enter viewport

### Technology Section
- 3 pillars with inline SVG icons
- Each pillar: hover reveals additional detail text
- Subtle scan-line overlay for tech aesthetic

### Configure Section
- Ship selector tabs (5 ships)
- Color picker: 4 hull colors with swatches
- Interior package: 3 levels (Standard, Premium, Elite)
- Add-on packages: checkboxes with price additions
- Live price calculator
- "Reserve Yours" CTA (links to contact)

### Heritage Section
- Timeline-style founding story
- Key stats animate in on scroll (counter animation)
- Luna base image with atmospheric overlay

### Footer
- Logo, minimal nav links, social icons (inline SVG)
- Copyright, legal links
- "Made on Luna" tagline

## Component Inventory

### Navigation Bar
- Fixed top, transparent → solid on scroll
- Logo left, nav links center, CTA right
- Mobile: hamburger → slide-in menu
- States: transparent, solid, mobile-open

### Ship Card
- Full-width image background with gradient overlay
- Ship name (h2), tagline, price
- Spec grid: range, passengers, drive, payload
- Configure CTA button
- States: default, hover (expanded specs), mobile (stacked)

### Spec Pill
- Label + value in monospace
- Border with corner accents
- States: default, hover (glow)

### Technology Pillar
- SVG icon (64x64)
- Title + description
- States: default, hover (reveal detail)

### Color Swatch
- 48px circle with color fill
- Border ring on selected
- States: default, hover, selected

### Package Toggle
- Card with title, description, price
- Checkbox or radio based on type
- States: unselected, selected, hover

### CTA Button
- Primary: gold background, dark text
- Secondary: transparent, gold border
- States: default, hover (glow), active (pressed), disabled

### Footer Link
- Text link with underline on hover
- States: default, hover

## Technical Approach

### Architecture
- Single HTML file (`index.html`)
- Embedded `<style>` for all CSS
- Embedded `<script>` for all JS
- Google Fonts loaded via `<link>`

### Starfield Implementation
- HTML5 Canvas
- 3 layers of stars with different sizes and opacities
- requestAnimationFrame for smooth animation
- Mouse move listener for parallax

### Scroll Animations
- IntersectionObserver API
- CSS classes toggled on intersection
- CSS transitions handle the actual animation

### Configurator State
- Plain JS object tracking current selections
- Event delegation for toggle handlers
- Real-time price calculation
- LocalStorage persistence (optional enhancement)

### Performance
- Lazy loading for below-fold images
- CSS containment for complex sections
- Throttled scroll/resize handlers
- Hardware-accelerated transforms only

## Ship Specifications

### Voyager
- Type: Compact single-pilot craft
- Price: $180,000
- Range: 2.4 AU
- Passengers: 1
- Drive: Ion Array Mark VII
- Payload: 120 kg

### Pioneer
- Type: 2-passenger explorer
- Price: $450,000
- Range: 4.1 AU
- Passengers: 2
- Drive: Plasma Array Mark III
- Payload: 380 kg

### Odyssey
- Type: 4-passenger family cruiser
- Price: $890,000
- Range: 8.7 AU
- Passengers: 4
- Drive: Dual Plasma Array
- Payload: 720 kg

### Aether
- Type: Flagship luxury yacht
- Price: $2,400,000
- Range: 15.2 AU
- Passengers: 6
- Drive: Quantum Fold Drive
- Payload: 1,200 kg

### Leviathan
- Type: Colony-class freighter/habitat
- Price: $6,000,000+
- Range: Modular
- Passengers: 12 (habitat module)
- Drive: Modular Bay — user selectable
- Payload: 48,000 kg

## Content

### Hero Tagline
"Your Name in the Stars"

### Heritage Copy
Founded in 2041 by a consortium of aerospace engineers who believed the stars should belong to everyone. Headquartered in the Tycho Industrial District on Luna, Aethercraft has delivered over 4,200 personal spacecraft to adventurers, families, and visionaries across the solar system. Every vessel is crafted by hand in our lunar facilities, tested against the harshest conditions in the solar system, and backed by the Aethercraft Lifetime Warranty.

### Technology Pillars
1. **Plasma Drive** — Our proprietary plasma confinement system delivers 3x the efficiency of conventional ion drives. Sustainable interstellar cruising at a fraction of the fuel cost.
2. **Quantum Navigation** — AI-assisted trajectory planning that accounts for 1.2 million gravitational variables in real-time. Your path, optimized automatically.
3. **Hibernation Pods** — Medical-grade cryogenic pods rated for journeys up to 5 years. Wake up exactly where you want to be.
