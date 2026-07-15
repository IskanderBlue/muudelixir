# MUUD Elixir — landing page

Single-page static site for MUUD Elixir. No build step — just `index.html` + `/images`.

## Preview it (no domain needed)

**Option A — drag & drop (fastest):** go to https://app.netlify.com/drop and drag this whole folder in. You get a live `*.netlify.app` URL instantly.

**Option B — GitHub Pages:** push this repo to GitHub, then Settings → Pages → deploy from `main` / root.

## Wiring up the real "Buy" button (Shopify)

Everything checkout-related is a placeholder link (`href="#"`) marked with `TODO` comments. Two spots to update in `index.html`:

1. The persistent bottom bar — `.bb-buy` link (`data-buy`).
2. The big buy section — `.btn-light` link (`data-buy`).

Once the Shopify Starter store + Buy Button exists, replace both `href="#"` values with the Shopify checkout / product URL, then delete the `[data-buy]` placeholder-alert block at the bottom of the `<script>`.

## Editing content

- **Testimonials:** `#testimonials` section. Each `.tcard` has a quote + name. To use a real customer photo instead of the monogram, set a background image on the `.avatar` (or replace it with an `<img>`) and remove the `placeholder` class.
- **Customer photos:** the `.gallery` row has drop-in `.shot` spots — put an `<img src="images/yourphoto.jpg">` inside any `.shot` to replace a placeholder.
- **Images:** live in `/images`. `jar.jpg` is the product; `infographic.jpg` is the full label breakdown.
