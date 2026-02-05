# Kaydelish — Static Website

This workspace contains a lightweight, responsive static website for Kaydelish (Bakery & Homemade Food Store).

Quick overview:
- Pages: `index.html`, `cakes.html`, `pastries.html`, `drinks.html`, `contact.html`
- Styles: `css/style.css`, `css/responsive.css`
- Scripts: `js/main.js`, `js/order.js`
- Assets: `assets/images/logo.png` (placeholder)

How to view locally

If you have Python 3 installed you can run a simple static server from the project root:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000` in your browser.

WhatsApp number configuration

Open `js/order.js` and set `WHATSAPP_NUMBER` (international format without "+") to your business number, e.g. `2348012345678`.

Admin & product management (local-only)

- Add `?admin=true` to the URL (e.g. `http://localhost:8000/pastries.html?admin=true`) to reveal a simple product admin panel.
- The admin panel stores product edits and availability in `localStorage`.
- This is intended for quick local management without a backend; for production, connect to a CMS or backend API.

Cake pre-order flow

- Go to `cakes.html`, fill the cake customization form and tap `Order via WhatsApp`.
- The form will open WhatsApp (click-to-chat) with a formatted order summary.

Extending the site

- To add products permanently, integrate a lightweight CMS or edit the HTML product templates in the `*.html` files.
- The layout is mobile-first and simple to customize.

Image gallery & performance

- A responsive gallery is included on the homepage and product pages. Images use `loading="lazy"` to improve performance.
- Replace the placeholder SVG images in `assets/images/` with optimized JPG/WEBP files (keep the same filenames) for best results.
 - Responsive images: SVG variants `*-400.svg` and `*-800.svg` were added and referenced via `srcset`/`sizes` to serve appropriately sized assets to different viewports.
 - For production, replace `*-400.svg`/`*-800.svg` with optimized JPEG or WebP files and update `srcset` filenames. Consider using an image pipeline (Sharp, Squoosh, or a CI step) to generate WebP and AVIF versions.

License & Notes

- This site is intentionally framework-free and optimized for quick deployment as a static site.
- Replace `assets/images/logo.png` with your brand logo (same filename) to keep layout intact.

If you want, I can:
- Add a small build step and template partials to avoid repeating the header/footer, or
- Integrate Netlify forms or a lightweight CMS (Netlify CMS, Forestry, or Airtable) for product management.
