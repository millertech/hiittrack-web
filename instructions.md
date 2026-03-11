# HIITTrack Website – Design & Feature Guide

## Overall Feel

The HIITTrack website is a **retro-inspired, minimalist single-page site** that mirrors the philosophy of the app itself: no bloat, no distractions, just what you need. Key design principles:

- **Old-school simplicity** – Pure HTML + CSS, no JavaScript frameworks, no third-party trackers. The site loads fast and works everywhere.
- **Warm, paper-like aesthetic** – A neutral color palette with warm tones (`#f5f0e8` background) gives the page a tactile, analog feel reminiscent of printed manuals or zines.
- **Retro orange-red accent** (`#b84c2e`) – Used sparingly for buttons and interactive elements, giving the page personality without overwhelming it.
- **Mobile-first, responsive layout** – Designed for phones first, scales cleanly to desktop. No breakpoints that feel forced.
- **Honest, direct tone** – Copy is conversational and straightforward. No corporate marketing speak. Speaks directly to the user as a fellow human tired of over-engineered apps.
- **Monospace touches** – Courier-style fonts for certain elements reinforce the old-school developer aesthetic.

---

## Site Structure & Sections

The site is a single `index.html` page with eight distinct sections:

### 1. Header / Hero
- App icon (emoji placeholder `⏱`, replaceable with real icon)
- App wordmark: **HIITTrack**
- Hero headline: *"The HIIT timer that just works."*
- Tagline: *"No tracking. No ads. Just train."*
- Primary CTA button linking to the App Store
- Optional "Coming soon" banner (commented out, ready to toggle)

### 2. Features
- Section title: *"Everything you need. Nothing you don't."*
- 6-item feature grid with icons:
  - **Reliable countdown timer** – No lag, no crashes
  - **Tabata & classic HIIT presets** – 20/10 Tabata, 40/20 circuits
  - **Custom intervals** – User-defined work/rest/rounds/sets
  - **Workout history & basic stats** – Sessions logged, total time, weekly streaks
  - **Apple Watch support** – View current interval from wrist
  - **Zero data collection** – No accounts, no cloud, no analytics SDKs

### 3. Why HIITTrack?
- Alternating-background section with a bullet list of differentiators:
  - No subscription – one-time purchase
  - No tracking or third-party SDKs
  - Fast, offline, no login required
  - Built by one developer (not a VC startup)
  - Side-hustle honest – no dark patterns
  - Small binary, no background processes, no notification spam

### 4. Screenshots
- Section title: *"Simple by design."*
- 4-image grid showcasing app screens:
  - `screen-timer.png` – Active timer
  - `screen-presets.png` – Presets
  - `screen-custom.png` – Custom intervals
  - `screen-history.png` – History & stats
- Images use `loading="lazy"` and an `onerror` fallback class

### 5. Pricing
- Section title: *"Simple pricing."*
- Pricing box:
  - One-time purchase: **$6.99**
  - No subscription, no upsells
  - Free tier available (core timer always free)
  - Advanced features (history, custom intervals, Watch app) via single in-app purchase

### 6. Call to Action
- *"Ready to train the old-school way?"*
- Large App Store download button
- Optional "Coming soon" note (commented out)

### 7. Email Signup
- *"Stay in the loop."*
- Incentive: Free 4-week HIIT routine PDF
- Placeholder email form (replace with ConvertKit / Mailchimp / Beehiiv embed)
- Privacy note: No spam, no selling emails

### 8. Footer
- Brand line: **HIITTrack © [year] Miller Technologies** (year auto-set via JS)
- Links: Privacy, @ee_developer on X, Contact (mailto)
- Closing notes about data privacy and upcoming apps

---

## Tech Stack

| Component | Detail |
|-----------|--------|
| HTML | Semantic, single-page, no build step |
| CSS | Custom properties, mobile-first, retro-inspired |
| JavaScript | Minimal inline script (copyright year only) |
| Hosting | GitHub Pages with custom domain (`CNAME`) |
| Frameworks | None – intentionally zero dependencies |
| Tracking | None – no analytics, no cookies, no third-party scripts |

---

## Color Palette

| Token | Value | Usage |
|-------|-------|-------|
| `--color-bg` | `#f5f0e8` | Page background (warm paper) |
| `--color-surface` | `#ffffff` | Card/box backgrounds |
| `--color-surface-alt` | `#edeae0` | Alternating section backgrounds |
| `--color-border` | `#c8c0ae` | Borders and dividers |
| `--color-text` | `#1a1a18` | Primary text |
| `--color-text-muted` | `#6b6658` | Secondary/subdued text |
| `--color-accent` | `#b84c2e` | Buttons, links, highlights (retro orange-red) |
| `--color-accent-dark` | `#8f3520` | Hover/active states |
| `--color-accent-light` | `#f0ddd7` | Subtle accent backgrounds |

---

## Typography

- **Primary font:** System UI stack (`system-ui, -apple-system, "Segoe UI", Helvetica, Arial, sans-serif`)
- **Monospace:** `"Courier New", Courier, monospace` – used for retro accents
- **Base size:** `1rem` with `1.65` line-height for readability

---

## Key Design Decisions

1. **No framework** – Keeps the site fast, simple, and easy to maintain by a single developer.
2. **Single page** – All content on one scrollable page; no navigation complexity.
3. **Lazy-loaded images** – Screenshots use `loading="lazy"` to keep initial load fast.
4. **Graceful fallbacks** – Screenshot `onerror` handlers add a placeholder class if images fail.
5. **Commented placeholders** – App Store links, email form, and "coming soon" banners are marked with clear comments for easy customization before launch.
6. **No build process** – Edit HTML/CSS directly, push to GitHub, deployed via Pages automatically.

---

## Pre-Launch TODO Checklist

### App Store & Links
- [ ] Replace all `https://apps.apple.com/` placeholder hrefs with the real App Store listing URL
- [ ] Verify App Store link opens correctly on iOS devices

### Pricing
- [ ] Confirm `$6.99` matches the actual App Store price
- [ ] Update pricing copy if the free/paid tier structure changes

### Branding & Assets
- [ ] Replace the emoji placeholder (`⏱`) with the real app icon (`icon.png`)
- [ ] Add an `og:image` meta tag with a social sharing preview image (1200×630 recommended)
- [ ] Add a favicon (`favicon.ico` or `favicon.png`)

### Screenshots
- [ ] Verify all four screenshots are final and up to date
- [ ] Optimize PNGs for web (compress with TinyPNG or similar to reduce load time)

### Email Signup
- [ ] Replace the placeholder email form with a real provider embed (ConvertKit, Mailchimp, or Beehiiv)
- [ ] Create and host the free 4-week HIIT routine PDF mentioned in the signup section
- [ ] Test the signup flow end-to-end (submit → confirmation email → PDF delivery)

### Contact & Social
- [ ] Verify the contact email is set up and receiving mail

### Legal & Privacy
- [ ] Review all copy for accuracy before going public

### "Coming Soon" Toggles
- [ ] If the app IS live: ensure "Coming soon" paragraphs remain commented out and App Store buttons are visible
- [ ] If the app is NOT yet live: uncomment the "Coming soon" banners and hide or disable the App Store buttons

### Performance & SEO
- [ ] Test page load speed (Lighthouse or PageSpeed Insights) — target 90+ score
- [ ] Verify `og:url` meta tag matches the live domain (`https://www.hiittrack.com/`)
- [ ] Test on multiple devices/browsers (Safari iOS, Chrome Android, desktop)
- [ ] Confirm HTTPS is working correctly with the custom domain

### Final
- [ ] Do a full read-through of all site copy for typos and tone
- [ ] Push final changes and verify the live site at `https://www.hiittrack.com/`

---

## Completed

- [x] Verify the contact email (`app@hiittrack.com`) is set up and receiving mail
- [x] Confirm the X/Twitter link (`@ee_developer`) is correct
- [x] Update the footer `mailto:` if the support email changes
- [x] Create a minimal privacy policy page (`privacy.html`) and link it from the footer
- [x] Update Apple Watch feature to show as Coming Soon
