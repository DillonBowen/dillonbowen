# Design

Source of truth: Dilly's Trading Co. Color & Mood Board Guide Book v2.0.

## Color

| Token | Hex | Role | Share |
|---|---|---|---|
| Noir Black | `#1A1A1A` | Primary surfaces, headers, dark sections, buttons | 50–60% |
| Archival Cream | `#F1EFE8` | Light section grounds, card fills, the system's "white" | 25–35% |
| Darkroom Grey | `#5F5E5A` | Body/secondary text on cream, captions, metadata | 10–15% |
| Aperture Gold | `#C9A46E` | Accent only: rules, one gold word in a black headline, dividers | 3–8% |

Rules from the guide: never white text on Darkroom Grey; never gold as a large background fill or photo overlay; cream text on noir for body on dark (gold reserved for accents). On noir, secondary text uses cream at reduced weight, not grey.

## Typography

- **Libre Franklin** (single family, weight contrast): 900 for display headlines, 600 for subheads, 400 for body. Franklin Gothic lineage = American newspaper masthead: literal "editorial authority."
- Display: `clamp()` fluid, max ~5.5rem, letter-spacing -0.03em, line-height ~0.95.
- Body: 17–18px, line-height 1.6, max 68ch. On cream body text is Noir Black; Darkroom Grey only for captions/metadata.

## Layout

- Single long-scroll page, alternating noir/cream bands weighted toward noir.
- Content column max 1080px; generous fluid section padding `clamp(96px, 14vh, 180px)`.
- Photography treated as film stills: full-bleed or large offset blocks, thin gold rules as dividers.

## Motion

- Parallax depth on hero layers and photo blocks via rAF `translate3d`, speed factors ±0.2.
- Scroll reveals via IntersectionObserver, gated on `html.js` so content is visible without JS; reveal = opacity + 24px rise + slight blur clear, 700ms `cubic-bezier(0.22, 1, 0.36, 1)`.
- Hero: one orchestrated load sequence (masked line reveals, gold rule draw).
- Gold hairline scroll-progress bar at top.
- `prefers-reduced-motion: reduce` kills parallax and collapses all animation to near-instant.
