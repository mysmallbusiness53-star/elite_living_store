# Elite Living Premium Storefront — Setup Guide

## What's included
- Responsive luxury-style storefront (HTML/CSS/vanilla JavaScript)
- 117 supplied product photographs copied into `assets/products/`
- `products.json` editable product catalogue
- Product search, category filter, sort, detail modal, local demo shopping bag and quantity controls
- Demo checkout explainer (intentionally does not submit orders or process payments)
- Contact form that prepares a draft email in the visitor's email app
- Draft policy page, favicon and source files

## Important launch status
This is a front-end storefront prototype, **not a production-ready e-commerce system**. Product names, categories, prices, descriptions, stock, business contact information and delivery arrangements have not been provided, so editable placeholders are used. The shopping bag is stored in the visitor's browser only. No real orders, customer accounts, payment, email delivery, inventory sync or admin dashboard are implemented. Do not accept live orders from this version.

## Run locally
Because the catalogue is loaded from `products.json`, open the project using a local web server rather than double-clicking `index.html`.

### Windows
1. Install Python 3 if needed.
2. Extract the ZIP.
3. Open Command Prompt in the extracted `elite_livings_luxury_store` folder.
4. Run: `python -m http.server 8000`
5. Open `http://localhost:8000` in your browser.
6. Press Ctrl+C in the command window to stop the server.

## Edit the catalogue
Open `products.json` in a text editor. Each product has:
- `name`: replace placeholder with the verified product name
- `category`: replace `Uncategorised` with the real category
- `price`: replace `null` with a number in ZAR, e.g. `249.00`
- `description`: replace with accurate information
- `image`: relative path to the included original photograph
- `available`: update when a real stock process is in place
- `alt`: accurate description for accessibility

Do not guess product names or prices from filenames. Check each photograph and match it to the correct product before launch. All 117 supplied JPG/PNG/WebP images found in the ZIP were copied to the project and included in the catalogue. If the ZIP contains other non-product files, they are not used as product photos.

## Replace business placeholders
- Edit business name and brand wording in `index.html`, `policies.html`, and `README.md` as needed.
- Replace `[Add business email]` and `[Add business number]` in `index.html`.
- The contact form uses `mailto:` without a preset recipient. Configure a real recipient or replace this with a secure backend form.
- Update SEO title, meta description, favicon and social links once confirmed details are available.

## What is required for a real store
1. Choose a platform/backend (for example Shopify, WooCommerce, or a custom server-side application).
2. Configure a secure database and server-side order creation/validation.
3. Set up a South African merchant account and configure a payment provider such as PayFast, Yoco or Peach Payments. Keep secret keys on the server, never in browser JavaScript.
4. Set real delivery options, rates, tax handling and fulfilment rules.
5. Configure order emails through a transactional email provider.
6. Implement authentication and a protected admin dashboard, with role-based access and secure password handling.
7. Finalise policies and privacy/consent settings for the real business.
8. Test payment provider sandbox flows, failed payments, order confirmation, refunds, inventory, mobile layouts and security before going live.
9. Deploy over HTTPS, connect the domain, configure backups, analytics (with appropriate consent), sitemap and robots.txt.

## Testing report
- [x] Responsive layout and mobile navigation implemented
- [x] Product list loads from JSON when served over HTTP
- [x] Search, category filter and sorting implemented
- [x] Product detail modal implemented
- [x] Add/remove/update cart quantities implemented
- [x] Subtotal uses configured numeric prices; unconfirmed prices are visibly marked
- [x] Cart persists locally in the browser
- [x] Checkout does not falsely claim an order/payment succeeded
- [x] Contact form validates required fields and prepares an email draft
- [x] Policy draft page created
- [ ] Product-to-photo matching verified by business owner
- [ ] Real product names, prices, specifications, stock and categories entered
- [ ] Live backend/database/admin dashboard
- [ ] Real customer accounts and order history
- [ ] Payment gateway configured and sandbox-tested
- [ ] Shipping/tax rules and order tracking configured
- [ ] Transactional email service configured
- [ ] Final legal/policy review
- [ ] Hosting, domain, HTTPS, analytics and SEO deployment configured

## File structure
- `index.html` — main storefront
- `styles.css` — design system and responsive styles
- `app.js` — storefront interactions
- `products.json` — editable product catalogue
- `assets/products/` — supplied photographs
- `assets/favicon.svg` — favicon
- `policies.html` — editable policy draft
