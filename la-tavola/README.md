# La Tavola Italiana — Website

Static, SEO/SEM-ready website for **La Tavola Italiana Limited**, an Italian
specialty wine & food retailer/wholesaler on Galu Beach Road, Diani, Kenya.


## Structure

```
├── index.html              # the whole site (single page, anchor-linked sections)
├── assets/
│   ├── css/styles.css      # design system + layout
│   └── js/main.js          # mobile nav, active-category highlight, footer year
├── robots.txt
├── sitemap.xml
└── netlify.toml            # deploy config + cache headers (Netlify only)
```

## What's in place

- **Ordering:** every product "Order" button and the floating button deep-link
  into WhatsApp (`wa.me/254794433309`) with a pre-filled message. Two more
  numbers (0116 740 980 landline, 0735 391 900 mobile) are listed for calls
  in the Visit & Contact section and footer.
- **Catalogue:** curated highlights across Wines & Sparkling, Olive Oil &
  Vinegar, Pasta & Rice, Cheese & Cured Meat, Pantry & Preserves, Coffee &
  Sweets, and Aperitivo & Spirits — sourced from the August 2026 price list —
  plus a "Download Full Price List (PDF)" button (hero and shop section) for
  the complete ~300-SKU wholesale catalogue.
- **Reviews:** a review grid marked up with `schema.org/Review`, plus an
  `AggregateRating` in the page's structured data.
- **SEO:** title/description/keywords tags, Open Graph + Twitter cards, a
  canonical URL, geo meta tags, `robots.txt`, `sitemap.xml`, and JSON-LD for
  `Store`, `Product` offers, `FAQPage` and `BreadcrumbList` — aimed at both
  local ("Italian delicatessen Diani") and international ("Italian wine
  Kenya") search intent.
- **Accessibility:** skip link, visible focus states, `prefers-reduced-motion`
  support, alt-free icon set built from inline SVG (decorative, `aria-hidden`).

## Before going live Ineed to replace these placeholders

1. **Photography.** The site currently uses illustrated category icons instead
   of product photography. Swap in real photos of the shop, the shelves and
   hero products — add them to `assets/images/` and reference them in
   `index.html` (each `<article class="product">` and the hero panel are
   marked so you can find the right spots).
2. **Map pin.** The embedded map and the `geo` coordinates in `index.html`
   use an approximate Galu Beach Road location (`-4.3480, 39.5780`). Replace
   with your exact pin from Google Maps (right-click the pin → coordinates).
3. **Opening hours.** Currently listed as Mon–Sat 8am–7pm, Sun 9am–4pm —
   confirm and edit in `index.html` (search for "Opening hours" and the
   `openingHoursSpecification` block near the top of the file).
4. **Full price list PDF.** `assets/documents/la-tavola-price-list.pdf` is
   linked from the hero button and the note above the shop section. Replace
   this file (keep the same filename, or update the link) whenever pricing
   changes — the on-site product cards are a curated highlight selection,
   not the full ~300-SKU catalogue.
5. **Reviews.** The six testimonials are illustrative placeholders, not real
   customer quotes. Replace with genuine reviews (and update the `4.9`
   average / review count) once you have them — for real, crawlable review
   markup, consider embedding actual Google Business Profile or TripAdvisor
   reviews instead.
6. **og-cover.jpg.** `index.html` references
   `assets/images/og-cover.jpg` for social-media link previews (1200×630px
   recommended) — add that file once you have a hero photo.
7. **Domain.** All canonical/OG URLs currently point at
   `https://latavola-italian.netlify.app/`. Once `latavolaitalian.com` (or
   whichever domain you buy) is live, find-and-replace that placeholder
   string across `index.html`, `sitemap.xml` and `robots.txt`.

## Editing the catalogue or prices

Product data lives inline in `index.html` inside each `<section class="shelf">`.
Each product card is a self-contained `<article class="product">` block with
name, badge (Signature / Bestseller / New), description and price — copy an
existing card to add a new item, or edit the numbers directly.

## Deploying

- **Netlify:** connect the repo, build command "none", publish directory `.`
  (already configured in `netlify.toml`).
- **GitHub Pages:** enable Pages on the repo, serve from the root of the
  `main` branch.
- **Any static host:** upload the contents of this folder as-is.

After deploying, submit `sitemap.xml` in Google Search Console and Bing
Webmaster Tools, and verify the structured data with Google's Rich Results
Test.
