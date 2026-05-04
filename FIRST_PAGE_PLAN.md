# VibeID — First Page Design Plan (Clutch-loop Style)

## 1) Purpose of the First Page
The first page should instantly explain **what VibeID is**, prove trust, and drive a single primary action:
- **Primary CTA:** Create Profile
- **Secondary CTA:** See Demo Tap Flow

This page acts as the launchpad for all future platform layers (identity, social, music, events, ecommerce).

---

## 2) Design Direction ("Clutch-loop style" reference)
Use a bold, modern, high-energy visual system with:
- Strong hero typography
- Dark base with vibrant accent gradients
- Motion micro-interactions (hover, tap pulse, subtle glow)
- Card-based sections with clean hierarchy
- Mobile-first vertical storytelling

Tone: premium + nightlife + creator-tech.

---

## 3) First Page Information Architecture

### A. Hero (Above the Fold)
**Goal:** Explain value in <5 seconds.

- Headline: “Tap. Share. Get Found.”
- Subhead: “VibeID turns NFC wristbands into instant digital identity, social profile, and future storefront.”
- Primary CTA: `Get Your VibeID`
- Secondary CTA: `Watch Tap Demo`
- Visual: animated wristband/NFC tap mockup to profile card
- Trust strip: “No app required • Loads in <2s • Secure tag mapping”

### B. How It Works (3-step loop)
**Goal:** Show frictionless user flow.

1. Tap wristband
2. Open live profile instantly
3. Share socials, music, events

Optional animation: looped connector arrows to reinforce “clutch-loop” flow.

### C. What Lives in Your Profile
**Goal:** Preview modular profile blocks.

Feature cards:
- Social links (Instagram, TikTok, X, YouTube)
- Spotify tracks/playlists
- Events you’re attending
- Custom bio + theme
- Future merch shelf

### D. Security + Speed Section
**Goal:** Build trust early.

Callouts:
- Cloudflare-protected edge routing
- Signed tag validation
- Anti-abuse rate limiting
- Fast CDN delivery

### E. Creator / Brand Use Cases
**Goal:** Show buyer personas.

Cards:
- DJs / artists
- Festival attendees
- Event promoters
- Streetwear / merch brands

### F. Social Proof / Early Metrics (placeholder-ready)
**Goal:** Future conversion booster.

Examples:
- “X taps served”
- “Y creators onboarded”
- Testimonials carousel (optional in MVP)

### G. Final CTA Banner
**Goal:** Conversion close.

- Copy: “Build your vibe profile in minutes.”
- CTA: `Claim Username`
- Secondary link: `Partner With Us`

### H. Footer
- Legal links
- Contact
- Social handles
- API / developer link (future)

---

## 4) UX Requirements (First Page)

### Performance
- Largest Contentful Paint target: <2.0s on mobile 4G
- Image strategy: Next/Image, optimized WebP/AVIF
- Lazy load non-critical media

### Accessibility
- WCAG AA contrast minimum
- Keyboard-focus visible states
- Semantic heading structure (single H1)

### Mobile-first behavior
- Sticky bottom CTA on small screens
- Thumb-friendly buttons
- Compressed hero content (headline + 1 sentence + CTA)

---

## 5) Component Plan (Next.js + Tailwind)

Suggested component breakdown:
- `HeroSection`
- `TapFlowSection`
- `ProfileModulesSection`
- `SecuritySection`
- `UseCasesSection`
- `SocialProofSection`
- `FinalCtaSection`
- `SiteFooter`

Each section should be reusable and data-driven via config objects for rapid iteration.

---

## 6) Content & Messaging Framework

### Brand promise
“Instant identity from one tap.”

### Supporting value points
- No app download required
- Profile updates in real time
- Built-in analytics and future monetization

### Copy style guide
- Short, bold, action-first sentences
- Avoid technical jargon in hero
- Put architecture/security details lower on page

---

## 7) Visual System Starter Tokens

### Colors
- Background: near-black charcoal
- Primary accent: electric violet/blue
- Secondary accent: neon mint/cyan
- Neutral text: off-white + cool gray

### Typography
- Heading: bold geometric sans
- Body: clean sans, medium weight
- Numeric/metrics: mono or semi-mono accent style

### Motion
- 150–250ms transitions
- Soft parallax on hero art
- Pulse animation on NFC tap indicator

---

## 8) Analytics Events for First Page
Track from day one:
- `landing_view`
- `hero_primary_cta_click`
- `hero_secondary_cta_click`
- `tap_flow_interaction`
- `final_cta_click`

These events map directly into the future full analytics model (`tap`, `view`, `click`, conversion funnel).

---

## 9) Technical Integration Notes
- Frontend: Next.js App Router with section-based components
- Backend handoff: CTA routes to auth onboarding endpoint
- Security handoff: NFC endpoint not exposed in public landing flow
- Infra alignment: page cached at edge (Cloudflare/Vercel CDN)

---

## 10) MVP Delivery Plan (First Page only)

### Week 1
- Finalize wireframe + visual direction
- Implement full page sections with placeholder content
- Add responsive layout + base animations

### Week 2
- Integrate analytics events
- Optimize performance/accessibility
- QA across iOS/Android and major browsers
- Launch with A/B test on hero CTA copy

---

## 11) Definition of Done
First page is ready when:
- All sections above are implemented and responsive
- Performance target (<2s perceived load on NFC-entry mobile path) is met
- CTA flow connects to onboarding path
- Tracking events are visible in analytics dashboard
- Security + trust messaging is present and understandable

