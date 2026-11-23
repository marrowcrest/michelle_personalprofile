# UI/UX Guidelines

Design rules for Mich Candelaria's portfolio (`index.html`). Contrast ratios below were checked with the WCAG 2.x formula.

## 1. Color rules

- **60-30-10.** 60% dominant neutral base (backgrounds, surfaces), 30% secondary color (subheadings, cards, secondary elements), 10% high-impact accent (primary buttons, CTAs, key highlights).
- **Limit the palette.** About 2–3 core colors plus neutrals.
- **Build harmony.** Use monochromatic, analogous or complementary schemes. Avoid pairing saturated opposite colors that vibrate.
- **Contrast for readability.** WCAG minimums: 4.5:1 for body text, 3:1 for large text (18pt+, or 14pt+ bold), UI components and meaningful graphics.
- **Never rely on color alone.** Pair color cues (errors, status, links) with text, icons or underlines.
- **Keep roles consistent.** The same color does the same job on every page, e.g. one accent reserved for primary CTAs.

**Verification checklist**

- [ ] Grayscale test: hierarchy and spacing still work without color.
- [ ] Contrast check: every text and button pair is tested before publishing.
- [ ] Context check: cultural color meanings, and both light and dark mode surfaces.

Sources: [NN/G](https://www.nngroup.com/articles/color-enhance-design/), [UX Pilot](https://uxpilot.ai/blogs/color-theory-in-web-design), [Penpot](https://penpot.app/blog/web-design-color-theory-how-to-build-brands-and-improve-ux-with-color/), [Creative Tim](https://www.creative-tim.com/blog/educational-ui-ux/practical-tips-for-using-colors-in-web-design/), [freeCodeCamp](https://medium.com/free-code-camp/comprehensive-guide-for-color-usage-in-web-design-e2a9afce09fb), [Section 508](https://www.section508.gov/create/making-color-usage-accessible/), [WebAIM](https://webaim.org/articles/contrast/)

## 2. Section contrast and pacing

Users should see at a glance where one topic ends and the next begins. That comes from alternating surface lightness, deliberate pacing and clear boundary cues.

- **Surface ramp, not just black and white.** Use 3–4 levels: primary light, tinted/soft surface, card/border surface, dark anchor.
- **Alternate adjacent sections.** Never stack two full-width sections with the same background unless a strong divider separates them.
- **Use anchor sections sparingly.** Dark or bold brand backgrounds are for high-priority moments: the hero, key proof, or the final CTA.
- **Keep brightness jumps comfortable.** Body sections alternate between white and a tint about 5–10% darker.
- **Contrast contained elements.** On a tinted section, use white cards. On a white section, use tinted cards or a 1px border.
- **Recheck contrast per surface.** Every background change means rechecking headings, body copy and CTAs.

**Typical pacing**

| Section | Surface | Purpose |
| --- | --- | --- |
| Hero | Dark anchor or soft tint | Captures attention, frames the main CTA |
| Trust bar | Primary light | Clean reset with muted logos |
| Core features | Soft tint | Separates cards without heavy lines |
| Process / deep dive | Primary light | Keeps text-heavy reading easy |
| Proof | Soft tint or dark anchor | Credibility before the final pitch |
| Final CTA + footer | Dark anchor | Signals the end; the button pops |

**Pitfalls**

- **Chattering stripes:** harsh black and white alternating on every section causes fatigue.
- **Disappearing CTAs:** a brand-colored button on a background of the same brand color.
- **Hard photo edges:** add a border, padding buffer or gradient where a full-bleed photo meets a solid block.

## 3. Canopy palette

Taken from a photo looking up through sunlit leaves into a clear sky. Deep forest gives authority, sky blue gives structural clarity, and sunlit lime is the action accent.

| Role | Name | Hex | Verified contrast | Use |
| --- | --- | --- | --- | --- |
| Text / dark anchor | Deep Canopy | `#122312` | 16.47:1 on white | Headings, body text, dark sections |
| Secondary brand | Forest Moss | `#2C5422` | 8.76:1 on white, 8.10:1 on mist | Links, eyebrows, tags, text bubbles |
| Structural accent | Clear Sky Blue | `#4E91D2` | 3.33:1 on white, 4.95:1 on Deep Canopy | **Graphics only on light** (lines, dots). Text only on dark surfaces |
| Action accent | Sunlit Leaf | `#B8D432` | 9.81:1 with Deep Canopy text | Primary CTA buttons only. Add a `#6F8418` edge on light surfaces (it's 1.68:1 against white) |
| Base | Pure Daylight | `#FFFFFF` | — | 60% base surface |
| Tint | Morning Mist | `#F4F7F2` | — | Alternating sections |
| Divider | Soft Sage | `#E4ECE0` | 1.21:1 (decorative) | Card borders and dividers. Form fields need a darker border (`#7C8A76`, 3.65:1) |

**Corrections to the original notes:**
- Sunlit Leaf with Deep Canopy is 9.81:1, not 11.2:1. It still passes.
- Clear Sky Blue fails as link text on white, so links use Forest Moss.

## 4. Font pairings

| Option | Headings | Body / UI | Mono (numbers, labels) |
| --- | --- | --- | --- |
| **A: Technical Precision** | Space Grotesk 600/700, −0.025em | Inter 400/500/600, line-height 1.6 | JetBrains Mono 500, +0.04em |
| **B: Executive & Architectural** | Plus Jakarta Sans 700/800, −0.02em | DM Sans 400/500, line-height 1.6 | IBM Plex Mono 500 |
| **C: Editorial Authority** | Instrument Serif 400, −0.015em (it has only one weight) | Geist 400/500/600 | Geist Mono 500 |
| **D: Swiss Grid** | Archivo 700 (Switzer is the original pick; Fontshare can't be reached from the sandbox) | Archivo 400 | Space Mono 400 |

**Mono rule:** use it only for numbers and short labels: eyebrows, step numbers, stats, timestamps. Never use it for words in sentences.

## 5. As applied to this site

| Section | Surface | Inside |
| --- | --- | --- |
| Header | White, 1px border | Lime CTA with a darker edge |
| Hero | Morning Mist | White phone card, sky status dot |
| Services | White | Mist cards with a Sage border |
| How it works | Morning Mist | White cards, sky top line |
| Selected work | White | Sage dividers |
| About | Morning Mist | White skills card |
| Free lead check + footer | Deep Canopy (dark anchor) | Raised form panel, sky eyebrow, lime CTA |

- **Fonts:** Option A is the default until a final pick. Switching means changing the font `<link>` and the `--font-*` tokens in `:root`.
- **Dark mode:** follows the system setting, using its own token set. Every pair is re-verified to pass.
