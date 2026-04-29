# SSCK Front Page Remix — Notes

## What this is
A complete reimagining of the Sachs Sax Caplan, P.L. homepage as **Sachs Sax Caplan Kaskel** — a single static `index.html` file with Tailwind via CDN. All content is lifted verbatim from the existing ssclawfirm.com site; only the firm name was extended to "Kaskel" and the design was rebuilt from scratch.

Open `delivery/index.html` directly in any browser, or serve with `python3 -m http.server 8080` from this folder.

## Aesthetic direction
**Editorial-establishment.** The page is composed like a Sunday legal supplement rather than a generic law-firm template. Recurring devices:
- Section labels in tracking-widest gold caps (`§ 02 — THE FIRM`)
- Big "ghost numerals" behind practice cards (01–05) as editorial anchors
- A masthead-style firm name with middle-dot separators and a single gold underline under the new partner: `Sachs · Sax · Caplan · Kaskel`
- Italic Fraunces pull-quotes used as breath moments, not headlines
- A single full-bleed hero photograph instead of the original's slideshow

## Type
- Display: **Fraunces** (variable contemporary serif from Google Fonts)
- Body: **DM Sans**
Chosen specifically to avoid generic Inter/Roboto pairings and to feel periodical-grade.

## Color
| Token | Value | Use |
|---|---|---|
| `--navy` | `#1B2A4A` | About section, primary surfaces |
| `--navy-deep` | `#0E1A33` | Footer, top utility bar |
| `--gold` | `#C5973B` | Eyebrows, rules, CTAs, hover states |
| `--gold-light` | `#D9B570` | Hero italic subhead |
| `--cream` | `#F6F1E7` | Pull-quote and contact bands |
| `--paper` | `#FAFAF7` | Page background |
| `--ink` | `#1C1C1C` | Body copy |

## Content kept verbatim
- All five practice-area descriptions (Commercial Litigation, Community Association, Estate Planning, Real Estate, Government & Lobbying)
- The two-paragraph firm "From the boardroom to the courtroom…" positioning statement
- Three blog headlines, dates, authors, and excerpt text (Feb 4, 2026 / Jan 29, 2026 / Dec 5, 2025)
- AV® Martindale-Hubbell credential language ("awarded to only one percent of firms reviewed")
- Both office addresses (Boca Raton main, Palm Beach Gardens)
- Phone (561-994-4499), fax (561-537-8638), email (info@ssclawfirm.com)

## Design decisions and trade-offs

**Hero — single image, no carousel.** The original site rotates through five backgrounds. This concentrates the eye on one image (Miami skyline at dawn) and uses a single gradient + film-grain overlay so type stays primary.

**Asymmetric practice grid (7+5 / 5+4+3).** Replaces the original's 4-up grid. The five practices get visual weights that map to firm focus. Card 5 (Government & Lobbying) is intentionally a no-photo navy block with a corner ornament — it punctuates the grid instead of feeling thin.

**The `K` badge.** The existing SSC monogram is reused everywhere with a small gold pill bearing a `K` tucked into the bottom-right. This works as an honest placeholder that signals the rebrand without faking a finished SSCK logo.

**Big serif phone number in contact section.** The 96px Fraunces phone number is the visual centerpiece of the contact band. Most law-firm sites bury the phone in a footer; this treats it as a headline.

**Footer with link grid + social + legal row + "Designed in Boca Raton" signature.** Editorial completeness without padding it out with marketing-form fields.

## What this is NOT (deliberate scope cuts)

- **No interior pages.** Practice/About/Attorneys/News/Contact links all go to `#` anchors or in-page sections.
- **No CMS integration.** All news cards are hard-coded.
- **No contact form.** The "Schedule a consultation" CTA is a button only; no form behind it.
- **No newsletter signup field.** The original has one in the footer; the remix omits it for restraint.
- **No "Make a Payment" gateway integration.** Link is a placeholder.
- **No accessibility audit beyond fundamentals.** Semantic HTML, alt text, focus styles, AA contrast on body copy. A formal audit would tighten focus rings, ARIA on the mobile menu, and form-free interactive controls.
- **The SSCK logo is a placeholder.** Uses the existing SSC monogram + gold "K" pill until a final mark is designed.

## What would change for a full build

1. Replace the placeholder SSCK monogram with the final logo (header, footer, masthead favicon)
2. Build out interior pages: Who We Are, individual practice pages, attorney bio template, full news index
3. Wire the news section to a CMS (the firm currently uses EasyBlog inside Joomla — likely a port to a headless CMS or Sanity)
4. Add a real contact form with server-side validation
5. Integrate a payment gateway for "Make a Payment"
6. Add structured data (LegalService schema, address microdata)
7. Run a full WCAG 2.2 AA audit
8. Performance pass: convert images to WebP, lazy-load below-fold images, replace Tailwind CDN with built CSS
9. Analytics + consent banner
10. Production hosting on Vercel with the framework of choice (Next.js App Router would suit this content model)

## Files

```
delivery/
├── index.html               # the page
├── reference/images/        # all imagery (18 files, ~6 MB)
└── REMIX-NOTES.md           # this file
```

To preview: open `index.html` directly, or run `python3 -m http.server 8080` from `delivery/` and visit http://localhost:8080/.
