# MUUD Elixir — landing page

Single-page static site for MUUD Elixir. No build step — just `index.html` + `/images`.

## Preview it (no domain needed)

**Option A — drag & drop (fastest):** go to https://app.netlify.com/drop and drag this whole folder in. You get a live `*.netlify.app` URL instantly.

**Option B — GitHub Pages:** push this repo to GitHub, then Settings → Pages → deploy from `main` / root.

## Buy buttons (PayPal — live)

Two products, priced **all-in with shipping included** (no separate tax line):

| Product   | Price      | PayPal hosted-button ID |
|-----------|------------|-------------------------|
| Single jar | $39.99 CAD | `LU3HG5AQLKKJC` |
| 3-pack     | $79.99 CAD | `H3QYSLKAVYKU2` |

These render as PayPal Hosted Buttons via the SDK `<script>` block near the bottom of `index.html`:
- Each tier in the buy section (`#buy` → `.tiers`) has a `<div id="paypal-container-…">` that the SDK renders the real PayPal button into.
- The sticky bottom bar buttons are plain `#buy` anchors that smooth-scroll up to the live buttons (PayPal buttons don't fit the cramped bar).

**Changing prices/products:** edit the button in the PayPal Business dashboard (paypal.com/buttons) — the price is stored server-side, so the site needs no change unless the displayed price text (tier `.tier-price`, hero `.price-note`, bar buttons) needs updating to match. To swap a product entirely, generate a new hosted button and replace the `hostedButtonId` + container `id` in both the `<div>` and the `.render()` call.

**Later moving to Shopify?** Replace each `<div id="paypal-container-…">` with a Shopify buy link/button and remove the PayPal SDK block. Update the displayed price text to match.

## Editing content

- **Testimonials:** `#testimonials` section. Each `.tcard` has a quote + name. To use a real customer photo instead of the monogram, set a background image on the `.avatar` (or replace it with an `<img>`) and remove the `placeholder` class.
- **Customer photos:** the `.gallery` row has drop-in `.shot` spots — put an `<img src="images/yourphoto.jpg">` inside any `.shot` to replace a placeholder.
- **Images:** live in `/images`. `jar.jpg` is the product; `infographic.jpg` is the full label breakdown.
