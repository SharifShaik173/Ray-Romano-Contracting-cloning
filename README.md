## Ray Romano Contracting — Website
 
A single-page marketing website for **Ray Romano Contracting**, a boutique NYC/Hamptons renovation and general contracting company. Built with plain HTML and CSS (no framework, no build step).
 
## Project Structure
 
```
.
├── index.html      # All page markup/content
├── style.css       # All page styling
└── Assets/         # Images referenced by the page (not included in this upload)
    ├── RAY+ROMA+OFFICAL+LOGO+SCREENSHOT.webp   # Logo (nav + favicon)
    ├── main1.webp – main5.webp                 # Full-bleed section background images
    └── img1.webp – img7.webp                   # Gallery grid images
```
 
> ⚠️ The `Assets/` folder is referenced by both `index.html` and `style.css` but was not included in the upload. The page will render with broken images/backgrounds until these files are added at the paths above.
 
## Page Sections (in order)
 
| Section | ID(s) | Purpose |
|---|---|---|
| Nav + Hero | `#m1` / `nav`, `#s1` | Logo, nav links (Sag Harbor Hamilton, About, Services, Portfolio, Videos, Tips, Quote), hero title + tagline |
| Intro copy | `#s2` | "Renovating Your Home" — company overview |
| Divider banner | `#m2` | "Everybody Loves Raymond, the Contractor" |
| About Ray | `#s3` | Founder bio, press mentions (Town Haul, Oprah, Neil Cavuto, Domino, NYT) |
| Divider banner | `#m3` | "Services" |
| Services copy | `#s4` | Design/build process, co-op board negotiation support |
| Divider banner | `#m4` | "Testimonials" |
| Testimonials | `#s5` | Three client quotes (Jamie Floyd, Donna & Scott, David Siegel) |
| Divider banner | `#m5` | "Gallery" |
| Gallery grid | `#m6` / `#s6` | 7-image CSS grid gallery, "Top" anchor link back to `#top` |
| Footer | `footer` | Address, phone numbers, email |
 
## Styling Notes
 
- Layout is built almost entirely with `position: absolute` / `relative` and `vh`/`%` units rather than modern layout tools (Flexbox/Grid), so the design is viewport-height driven and may need testing across screen sizes.
- Section backgrounds (`#m1`–`#m5`) use `background-attachment: fixed` for a parallax effect.
- Nav links use non-breaking spaces (`&nbsp;`) for spacing instead of CSS gap/margin — a good candidate for cleanup.
- Gallery tiles (`#d1s6`–`#d7s6`) are empty `<div>`s styled with background images rather than `<img>` tags — not ideal for accessibility/SEO (no alt text).
## Known Issues / Suggested Improvements
 
1. **Duplicate `id` attribute**: `<main id="m1" id="top">` — HTML only honors the first `id`; the in-page "Top" anchor link (`href="#top"`) will not work as written. Fix by giving the wrapper a single id (e.g. `id="m1" ` plus a separate anchor, or renaming to `id="top"`).
2. **Empty nav links**: all `<a href="">` currently point nowhere — need real hrefs (`#s2`, `#s4`, etc., or separate pages).
3. **Deprecated `<font>` tag**: `#nav2` wraps links in `<font>`, which is obsolete HTML4; replace with a `<ul>`/`<nav>` list styled via CSS.
4. **No `alt` text** on the logo `<img>` or gallery images — add for accessibility and SEO.
5. **No responsive/mobile breakpoints** — the CSS has a single fixed layout; consider media queries for smaller viewports.
6. **Missing `Assets/` folder** — required for the site to display correctly.
## Running Locally
 
No build tools required. Simply:
 
1. Ensure `index.html`, `style.css`, and the `Assets/` folder are in the same directory.
2. Open `index.html` directly in a browser, or serve locally:
```bash
   npx serve .
   # or
   python3 -m http.server 8000
```
3. Visit `http://localhost:8000` (or the port shown).
## Contact Info (from footer)
 
302 West 86th Street, New York, NY 10024
(O) 212-496-8102 · (T) 917-701-1498
ray@rayromanocontracting.com
 
