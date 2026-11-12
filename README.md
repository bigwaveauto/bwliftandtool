# BW Lift & Tool — Shopify theme

Dawn 16.1.1 customized to the "Direction J" design: warm paper ground, navy ink, BW blue, Figtree, white product cards with an In-stock pill, guided "what are you lifting?" cards, the delivery walkthrough on the front page.

## In the code
- `config/settings_data.json` — color schemes: 1 paper (page), 2 white (cards, bands), 3 navy (announcement), 4 paper + blue buttons, 5 cream (freight strip). Cards: 1px border, 6px radius.
- `assets/bwlt.css` — Figtree via Google Fonts, all `.bw-*` components, card/pill styling, product and collection tweaks.
- `sections/bwlt-strip.liquid` — freight strip under the header (header group).
- `sections/bwlt-lifting.liquid` — "What are you lifting?" cards (home + collection).
- `sections/bwlt-steps.liquid` — delivery steps with photo.
- `sections/bwlt-duo.liquid` — two panels (tire & wheel / quote brands).
- `sections/bwlt-who.liquid` — "Who you're buying from".
- `snippets/card-product.liquid` — tag-driven card lines: `freight-included` → green "Freight included to a business"; `freight-lift`/`freight-mid` → "+ freight by zone"; `quote-only` → "from $X" + orange Quote pill; otherwise green In stock pill.
- `sections/main-product.liquid` — `quote-only` products show **Request a quote** (prefilled link) instead of Add to cart, and "from" on the price. Buy-now products show the cash-price terms line.
- `templates/index.json`, `collection.json`, `product.json`, `page.*.json` — all copy lives here; edit in the theme editor.

## Admin checklist (not code)
1. **Online Store → Themes → Add theme → Connect from GitHub** → `bigwaveauto/bwliftandtool`, branch `main`. Preview, then Publish.
2. **Theme settings → Logo**: upload the logo (≈400px wide PNG/SVG) and favicon. Until then the header shows the store name as text.
3. **Navigation** → menus with these handles:
   - `main-menu`: Lifts (/collections/2-post-lifts), 4-Post (/collections/4-post-lifts), Tire changers (/collections/tire-changers), Balancers (/collections/balancers), Delivery & install (/pages/delivery)
   - `footer-shop`: 2-Post Lifts, 4-Post Lifts, Tire & Wheel, Full catalog (/collections/all)
   - `footer-help`: Delivery (/pages/delivery), Warranty & returns (/pages/warranty), Installation (/pages/installation), Request a quote (/pages/request-a-quote), About (/pages/about)
4. **Pages** (Online Store → Pages) — create each and pick the matching theme template on the right: Delivery → `page.delivery`; Warranty → `page.warranty`; Installation → `page.installation`; About → `page.about`; Request a quote → `page.request-a-quote`; Contact → `page.contact`. Page body can stay empty; the copy is in the template.
5. **Collections**:
   - `best-sellers` (manual, sorted manually): OHX-10, OH-10 ALI, OH-12S, Forward I10, Forward F10, OH-15, OH-18, Forward CR14 — these are "The eight we keep in front". Add 407-P, 408-P, 409-HP, OH-9, EFP9 after for the "all 13" view.
   - `2-post-lifts`, `4-post-lifts`, `tire-changers`, `balancers`, `tire-and-wheel` (automated by product type).
6. **Photos**: ask the distributor for the AMGO and Forward dealer image packs (white-background studio shots) and upload one per product. Then in Customize: hero photo (bay), delivery-steps photo (crate on a liftgate), who-you're-buying-from photo (shop from the street), two panel images.
7. **Search & Discovery app** (free): turn on filters — Availability, Price, Product type, Vendor, and Tag groups for capacity (`cap-9k`…`cap-18k`), ceiling (`ceiling-11ft`, `ceiling-12ft`, `ceiling-13ft`), certification (`ali`), freight (`freight-included`, `freight-lift`). Add synonyms: OH10/OH-10, two post/2-post, 4 post/four-post.
8. **Fill the brackets**: search the theme editor for `[PHONE]`, `[PRICE]`, `[SPEC]`, `[CONFIRM]` and replace. The `tel:+1` link on the homepage button needs your number.
9. **Shipping profiles** drive the delivery choice at checkout: a `freight-included` profile ($0 commercial / $225 residential liftgate) and an AMGO zone profile (399 / 549 / 699, +$150 liftgate), plus free local pickup.
