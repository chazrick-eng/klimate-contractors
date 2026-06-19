# Klimate Contractors Limited — Website

Jamaica's HVAC, refrigeration & cold storage provider. Static marketing site + product inventory.

## Structure

```
index.html        # Home page (hero, services, featured inventory, projects, about, contact)
shop.html         # Full shop / inventory page (120+ products, filter + search + sort)
assets/           # Logo, brand icon, product photos
uploads/          # Source brand material (Instagram screenshots, logo source)
```

## Running locally

It's a static site — no build step. Either:

- Open `index.html` directly in a browser, **or**
- Serve the folder (recommended, so relative paths resolve cleanly):

```bash
# Python 3
python3 -m http.server 8000
# then visit http://localhost:8000

# or Node
npx serve .
```

## Deploying

Works on any static host — **GitHub Pages**, Netlify, Vercel, Cloudflare Pages, S3, etc.

### GitHub Pages
1. Push this folder to a repo.
2. Repo → **Settings → Pages** → Source: deploy from branch → `main` / root.
3. Site goes live at `https://<user>.github.io/<repo>/`.

## Editing the product catalog

All shop products live in one array in `shop.html` — search for `const PRODUCTS = [`.
Each entry:

```js
{
  id:"unique-id",
  cat:"ac",                  // ac | cold | heater | fan | extractor | pump | gen | tank | curtain | purify | blender
  brand:"Windy",
  name:"Windy 12,000 BTU Inverter Split",
  meta:"Most popular · 17 reviews",
  price:58995,               // JMD; use 0 for "Get Quote"
  oldPrice:64995,            // optional — shows strike-through + Sale badge
  badge:"sale",              // sale | new | exclusive (optional)
  stock:"in",                // in | out | quote
  inverter:true,             // optional, for the "Inverter only" filter
  img:"https://…/photo.jpg", // product image URL, or null to use a built-in SVG placeholder
  ph:"ph-vrf"                // placeholder symbol id when img is null
}
```

Category counts, search, sort and filters all update automatically.

## Contact / brand

- Phone: 1 (876) 913-5679 · 1 (876) 874-8675
- WhatsApp: 1 (876) 874-8675
- Email: klimatecl@gmail.com · info@klimatejamaica.com
- Location: Discovery Bay, St. Ann, Jamaica
- Instagram: @klimatecontractorsltd

## Notes

- Fonts load from Google Fonts (Manrope + Archivo) over CDN.
- Some product images are hot-linked from a third-party CDN as placeholders — replace with Klimate's own photography before production launch.
- Illustrative prices — confirm against the live price list before publishing.
