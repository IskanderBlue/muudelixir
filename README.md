# MUUD Elixir — landing page

Single-page static site for MUUD Elixir. No build step — just `index.html` + `/images`.

## Preview it (no domain needed)

**Option A — drag & drop (fastest):** go to https://app.netlify.com/drop and drag this whole folder in. You get a live `*.netlify.app` URL instantly.

**Option B — GitHub Pages:** push this repo to GitHub, then Settings → Pages → deploy from `main` / root.

## Wiring up the real "Buy" buttons (PayPal)

Two products: **single jar $19.99** and **3-pack $59.99** (item prices), plus a flat **$20 shipping** charge (covers 1–3 units) configured in PayPal, plus tax. All checkout links are placeholders (`href="#"`) marked with `TODO` comments. There are **four** spots, two per product (buy section + sticky bar), identified by `data-product="single"` / `data-product="triple"`:

1. Buy section (`#buy` → `.tiers`) — one link per tier.
2. Sticky bottom bar (`.bb-right`) — one link per product.

**To go live:** in the PayPal **Business** dashboard, create a Hosted Button for each product (set price + the $20 shipping). PayPal gives you a hosted-button ID / HTML snippet. Replace the matching `href="#"` links (or swap them for PayPal's snippet), then delete the `[data-buy]` placeholder-alert block at the bottom of the `<script>`.

**Later moving to Shopify?** Same swap — replace the same links with the Shopify checkout URLs and adjust prices. No structural changes needed.

## Editing content

- **Testimonials:** `#testimonials` section. Each `.tcard` has a quote + name. To use a real customer photo instead of the monogram, set a background image on the `.avatar` (or replace it with an `<img>`) and remove the `placeholder` class.
- **Customer photos:** the `.gallery` row has drop-in `.shot` spots — put an `<img src="images/yourphoto.jpg">` inside any `.shot` to replace a placeholder.
- **Images:** live in `/images`. `jar.jpg` is the product; `infographic.jpg` is the full label breakdown.
