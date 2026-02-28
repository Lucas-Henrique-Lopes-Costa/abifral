# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static landing page for **Abifral**, a Brazilian geriatric diaper brand (Lagoa Santa – MG). No build system — open `index.html` directly in a browser to preview.

## Stack

- **Single file**: `index.html` (~1683 lines) — all HTML, CSS, and JS in one file
- **Tailwind CSS**: loaded via Play CDN (`cdn.tailwindcss.com`), configured inline via `tailwind.config`
- **GSAP + ScrollTrigger**: loaded from CDN, used for all animations
- **Iconify**: icon library via CDN
- **Fonts**: Inter (body), Space Grotesk (display headings), JetBrains Mono (labels/section numbers)

## Page Sections

Sections use anchor IDs for navigation:
- `#hero` — hero with two-product carousel (Classic / Ecofral)
- `#diferenciais` — feature cards (01)
- `#produtos` — product detail panels: `#product-classic` and `#product-ecofral` (02)
- `#sobre` — about / mission / values (03)
- `#contato` — contact info + WhatsApp CTA (04)
- Footer — dark navy, logo + nav links

## Design Tokens

CSS variables defined in `:root` and mirrored in `tailwind.config`:

| Token | Value |
|---|---|
| `--navy` | `#1A1F8F` |
| `--navy-dark` | `#0F1360` |
| `--navy-light` | `#2D34B8` |
| `--teal` | `#00C4B4` |
| `--teal-dark` | `#009E91` |
| `--teal-light` | `#33D0C3` |
| `--off-white` | `#F8F8F6` |
| `--ink` | `#1C1C1C` |
| `--mid` | `#9A9A96` |

Tailwind utility classes `navy` and `teal` are also available (e.g., `bg-navy`, `text-teal`).

## Animation Conventions

GSAP animations are initialized inside `initAnimations()` at the bottom of `index.html`.

- `.gsap-reveal` — scroll-triggered fade+slide-up for generic elements
- `.gsap-card` — staggered entrance for card grids
- `.gsap-stat` — animated counter on scroll (reads `data-target` and `data-suffix` attributes)

## Assets

```
assets/
  raw_file/        # product/brand images served from abifral.com.br/assets/raw_file/
  design_system.html   # design system reference (color palette, typography, components)
  templates/       # reference HTML templates used during design

briefing/
  sobre.txt        # brand "About Us" copy
  contato.txt      # contact info and social handles
  produtos/        # product images organized by product line
    Fraldas Descartaveis Abifral Classic/
    Fraldas Descartaveis Ecofral/
```

## Products

- **Abifral Classic** — premium line (sizes M, G, XG)
- **Ecofral** — eco line (sizes M, G, XG)

## Contact / Brand Info

- Instagram: `@abifraloficial`
- WhatsApp link in contact section and footer
- Address: Avenida das Arvores, 405 – Distrito Industrial Olhos D'água, Lagoa Santa – MG
