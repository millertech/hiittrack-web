# HIITTrack Web — Development Learnings

Lessons learned while building and iterating on the marketing site.
Updated as we go so the same mistakes aren't repeated.

---

## Visual flow & section design

### Don't stack grids
Three grid-based sections in a row (How It Works cards → Feature cards → Insight cards) looked like a wall of identical boxes. The eye had nothing to latch onto.

**Fix:** Vary the visual treatment per section. Feature cards stay as a grid. How It Works became a vertical timeline with numbered circles and a dashed connecting line. Insights became a blockquote callout with pill-shaped tags. Each section now has a distinct shape.

### Section order matters for narrative
The original order put "How It Works" before features — explaining *how* to use the app before the reader knew *what* it does. That's backwards.

**Better order:**
1. Hero (hook)
2. Features (what it does)
3. How It Works (how to use it)
4. Insights (the smart differentiator)
5. Why / Trust builders
6. Screenshots (proof)
7. Pricing
8. Call to action
9. Email signup
10. Footer

### Numbered steps need visual hierarchy
Small 2rem numbered circles on white cards didn't read as "step 1, 2, 3, 4" — they looked like another feature grid with arbitrary decorations. The numbers were hard to read against the accent background.

**Fix:** Larger circles (2.75rem), heavier font (900 weight, 1.25rem), positioned on a vertical dashed line to show sequence. The timeline pattern immediately signals "steps in order" without needing to read the numbers carefully.

### Grid items must divide evenly into row count
`auto-fill` grids look broken when the total item count doesn't divide evenly into the number of columns. 8 feature cards on a 3-column grid = 3 + 3 + 2 orphans. 6 screenshots on a 4-column grid = 4 + 2 orphans. The last row always looks unfinished.

**Rules:**
- Pick your column count first, then make sure the item count is a multiple.
- Use explicit `repeat(N, 1fr)` instead of `auto-fill` when you need guaranteed column count.
- When cutting items to balance, merge the removed content into remaining cards rather than deleting it entirely — e.g., "Audio & haptics" details folded into the "Fully customizable" card, "Rep estimation" folded into "AI-powered insights."

**Current grid math:**
| Section | Items | Columns | Rows | Balanced? |
|---|---|---|---|---|
| Features | 6 | 3 | 2 | Yes |
| Screenshots | 6 | 3 | 2 | Yes |

**Mobile overrides:** Features collapse to 1 column. Screenshots collapse to 2 columns (3 rows of 2 = still balanced).

---

## Content integration

### Don't dump feature specs onto a marketing page
FEATURES.md and MARKETING.md had detailed specs (50Hz sampling, CoreMotion, NSPersistentContainer). The website isn't docs — it's a single-page sales pitch.

**Rule:** Surface the *benefit*, not the implementation. "Your phone's accelerometer measures effort" is enough. Save "50Hz CoreMotion with per-second aggregation" for the App Store description or a technical blog post.

### Consolidate similar content
Insights were originally a full section with 6 cards duplicating content already mentioned in the Features grid (AI insights was already a feature card). This created redundancy.

**Fix:** Insights section became a single compelling quote example + a row of capability tags. Shows the *experience* of the feature rather than listing specs again.

---

## Development workflow

### Always preview in the browser before committing
HTML structure that looks fine in an editor can produce awkward visual flow (triple grids, orphaned numbers, same-looking sections). Open `index.html` in a browser — or run a local server — after every structural change.

```bash
# Quick preview
cd hiittrack-web
python3 -m http.server 8091
# → http://localhost:8091
```

### Background alternation checklist
When reordering sections, verify the `section-alt` class still creates proper alternating backgrounds. The pattern should be: default → alt → default → alt → ... Special sections (#cta uses `--color-accent-light`) break the pattern intentionally.

Current background order:
| Section | Background |
|---|---|
| Header | `--color-bg` |
| Features | `--color-bg` (default) |
| How It Works | `--color-surface-alt` (section-alt) |
| Insights | `--color-bg` (default) |
| Why | `--color-surface-alt` (section-alt) |
| Screenshots | `--color-bg` (default) |
| Pricing | `--color-surface-alt` (section-alt) |
| CTA | `--color-accent-light` (special) |
| Signup | `--color-surface-alt` (section-alt) |
| Footer | `--color-text` (dark) |

### Markdown files are internal docs, not website copy
FEATURES.md and MARKETING.md should match the site's tone but serve different purposes:
- **FEATURES.md** — Internal reference. What the app does in plain language. No jargon, no spec dumps.
- **MARKETING.md** — App Store copy, social media posts, competitive positioning. Ready to paste.
- **Website (index.html)** — The curated sales pitch. Pulls the best bits from both files but doesn't try to include everything.

### One-file approach works until it doesn't
The entire site is one HTML file + one CSS file. This is intentional — no build step, no framework, no dependencies. If the site grows beyond ~10 sections, consider splitting into multiple pages. For now, the single-page format matches the "no bloat" brand.

---

## Brand voice reminders

- Direct. Short sentences. No corporate hedge words.
- "No subscription BS" — the tone is conversational, slightly irreverent, never slimy.
- Privacy is a feature, not a footnote. Mention it early and often.
- Technical details (50Hz, CoreMotion, Swift Charts) add credibility only in small doses. Don't lecture.
- Every section should pass the "so what?" test — if it doesn't tell the reader something they care about, cut it.
