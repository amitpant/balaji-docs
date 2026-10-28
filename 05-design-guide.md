# Design guide

**Minimal, fresh and clean: lots of white space, big real photos, one accent colour, nothing extra.**

## Tokens (placeholder until the logo arrives)

| Token | Value | Use |
| --- | --- | --- |
| `--bg` | `#ffffff` | Page background |
| `--bg-soft` | `#f7f6f3` | Alternate sections, cards |
| `--ink` | `#16181d` | Main text |
| `--ink-soft` | `#5b616e` | Secondary text |
| `--line` | `#e6e4df` | Borders, dividers |
| `--accent` | `#1f6f5c` | Buttons, links, active states (swap for logo colour) |
| `--accent-ink` | `#ffffff` | Text on accent |
| Radius | `12px` cards, `999px` pills | |
| Font | Inter (fallback system sans-serif) | One family only |
| Body size | 16px mobile, 17px desktop | |
| Spacing | 4px base; sections 64px mobile / 112px desktop | |

## Rules

- Mobile-first. Test at 375px and 1280px.
- Headings in sentence case. No all-caps headings.
- Thin borders instead of heavy shadows.
- Photos: full-width hero, 4:3 cards, lazy-loaded, Cloudinary `f_auto,q_auto`.
- Avoid: emoji, auto-playing carousels, stock photos, a second accent colour.

## Home page order

1. Hero: photo, one line, "Get a free consultation"
2. Stats strip
3. Featured projects
4. Services
5. How we work (4 steps)
6. Testimonials
7. Enquiry form
8. Footer: contact, quick links, socials

## Admin

Same tokens. Left sidebar on desktop, bottom tabs on mobile. Plain forms, drag to reorder photos, a clear Publish switch.
