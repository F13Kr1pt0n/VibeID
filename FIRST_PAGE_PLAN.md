# VibeID Landing Page — Reviewer Package

## Review summary

This plan defines the first public VibeID landing page: a fast, mobile-first introduction to an NFC-powered digital identity product. The page must explain the tap-to-profile experience in seconds, establish trust without overwhelming visitors with infrastructure details, and move them toward one primary conversion.

**Primary conversion:** Create or claim a VibeID profile  
**Secondary conversion:** View the NFC tap demo  
**Audience:** Creators, DJs and artists, festival attendees, event promoters, and lifestyle/merch brands  
**Positioning:** Premium nightlife and creator technology; bold, energetic, and easy to understand  
**Future-facing, not MVP promises:** Ecommerce, merch, API access, events integrations, and advanced analytics

### Landing-page goals

1. Explain “tap wristband → open profile → share identity” within five seconds.
2. Make the no-app NFC flow feel tangible through a lightweight product demonstration.
3. Establish confidence through clear speed, privacy, and security messaging.
4. Preview the profile’s modular value: socials, music, bio/theme, and later extensions.
5. Send qualified visitors into onboarding through one consistent primary CTA.
6. Provide measurable interaction points so messaging can be improved after launch.

## Page section map

| Order | Section | Purpose | Required content or behavior |
|---:|---|---|---|
| 1 | Header | Brand recognition and direct action | VibeID identity, minimal navigation, primary CTA |
| 2 | Hero | Explain the product immediately | “Tap. Share. Get Found.” direction, one-sentence value proposition, primary CTA, tap-demo CTA, wristband-to-profile visual, concise trust strip |
| 3 | How It Works | Demonstrate the core loop | Three steps: tap wristband, open live profile, share socials/music/events; optional reduced-motion-safe loop animation |
| 4 | Profile Preview | Show what the user gets | Modular previews for social links, music, bio, and themes; label events and merch as future features unless committed for MVP |
| 5 | Security & Speed | Answer trust objections | Plain-language claims about fast delivery, tag mapping/validation, and abuse protection; only publish claims confirmed by engineering |
| 6 | Use Cases | Help visitors self-identify | DJs/artists, attendees, promoters, and brands |
| 7 | Social Proof | Support credibility | Real metrics or approved testimonials only; omit the section at launch if no verified evidence exists |
| 8 | Final CTA | Close the conversion path | One primary action using the same CTA language as the hero; optional partnership link |
| 9 | Footer | Complete the public surface | Contact, social handles, and required legal links; developer/API link remains future scope |

## Messaging and visual direction

**Brand promise:** “Instant identity from one tap.”

Use short, action-first copy. Keep technical language out of the hero and explain security in plain language lower on the page. The initial visual direction is a near-black base, electric violet/blue primary accent, mint/cyan secondary accent, strong geometric type, card-based hierarchy, and restrained glow or pulse effects.

Motion should reinforce the NFC interaction rather than decorate every section. Target 150–250 ms interface transitions, support prefers-reduced-motion, and avoid hero effects that delay content or interaction.

CTA wording must be normalized before implementation. The draft currently suggests “Create Profile,” “Get Your VibeID,” and “Claim Username”; reviewers should approve one primary label and one destination.

## Key technical constraints

### Confirmed product and UX constraints

- Mobile-first layout with a concise above-the-fold explanation.
- No app is required for the public tap-to-profile experience.
- One semantic H1, logical heading order, keyboard-visible focus, and WCAG 2.2 AA contrast.
- Thumb-friendly controls and no interaction that depends on hover.
- Non-critical media is lazy-loaded; critical hero content is not hidden behind animation.
- Responsive images use modern formats where supported and explicit dimensions to reduce layout shift.
- Motion respects reduced-motion preferences.
- Analytics must not collect sensitive profile or NFC identifiers from the public landing page.

### Targets requiring implementation validation

- Target LCP: under 2.0 seconds on a representative mobile 4G profile.
- Core Web Vitals should be measured in production, not inferred from local load time.
- The public landing page must not expose privileged NFC-management endpoints or secrets.
- Security, CDN, signed-tag, and rate-limit claims must match the deployed architecture.
- Analytics events proposed for launch:
  - landing_view
  - hero_primary_cta_click
  - hero_secondary_cta_click
  - tap_flow_interaction
  - final_cta_click

### Proposed architecture — approval required

The original draft proposes Next.js App Router, Tailwind CSS, framework image optimization, and Cloudflare or Vercel edge caching. The repository currently contains no application scaffold or dependency manifest that confirms this stack. Treat these as proposals until the implementation stack and deployment target are approved.

Suggested section boundaries, independent of framework:

- Header
- HeroSection
- TapFlowSection
- ProfileModulesSection
- SecuritySection
- UseCasesSection
- SocialProofSection
- FinalCtaSection
- SiteFooter

Sections should be data-driven where repeated content or rapid copy iteration makes that useful. Avoid premature abstraction for one-off layout elements.

## Scope boundary and acceptance

This package covers the landing page and its handoff points. It does not define the profile builder, authentication implementation, NFC provisioning, ecommerce, partner integrations, analytics backend, or API.

The landing page is implementation-ready when the unresolved checklist below is closed. The built page is launch-ready when it is responsive, accessible, connected to an approved CTA destination, instrumented with approved events, tested on current mobile and desktop browsers, and verified against production performance and security claims.

## Missing before reviewer approval

- [ ] Approve the implementation stack and deployment target.
- [ ] Choose one primary CTA label and provide its exact route or URL.
- [ ] Define what the tap-demo CTA opens: inline animation, video, prototype, or live demo.
- [ ] Confirm which profile modules exist at MVP launch; mark every other module as “coming soon” or remove it.
- [ ] Provide approved logo/wordmark, font licenses, color values, and wristband/profile visual assets.
- [ ] Confirm the exact security and performance claims with engineering.
- [ ] Provide privacy policy, terms, contact destination, and approved social links.
- [ ] Supply verified metrics/testimonials, or approve omission of Social Proof for MVP.
- [ ] Select the analytics provider, consent requirements, event properties, and validation owner.
- [ ] Define supported browsers/devices and the performance test profile.
- [ ] Confirm whether the mobile sticky CTA is required and ensure it does not obscure content.
- [ ] Assign owners for copy approval, design approval, technical acceptance, and launch sign-off.
