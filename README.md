# Leaf & Bloom — Luxury Botanical Studio

A multi-page static website for a premium botanical studio offering rare plants, artisan floral arrangements, wedding styling, and curated plant subscriptions.

---

## Project Structure

```
leafandbloom/
├── index.html          # Homepage — hero, featured products, gallery, testimonials
├── about.html          # About page — studio story, team, values
├── products.html       # Shop — full product catalog with filtering and sorting
├── services.html       # Services — offerings, process, pricing tiers
├── checkout.html       # Checkout — cart review and order summary
├── contact.html        # Contact — inquiry form and studio information
├── feedback.html       # Feedback — star rating form, reviews display
├── css/
│   └── style.css       # Global stylesheet with CSS custom properties
├── js/
│   └── script.js       # Application logic — cart, modals, forms, theme
└── images/             # Static image assets
```

---

## Pages

| Page | File | Description |
|---|---|---|
| Home | `index.html` | Hero section, featured products, Instagram gallery, testimonials, newsletter |
| About | `about.html` | Studio background, team profiles, brand values |
| Shop | `products.html` | Full product catalog with category filters and sort controls |
| Services | `services.html` | Service offerings, process steps, subscription plans |
| Checkout | `checkout.html` | Cart contents review, order totals, checkout form |
| Contact | `contact.html` | Contact form, location details, business hours |
| Feedback | `feedback.html` | Star rating widget, comment form, live reviews list |

---

## Technology Stack

| Category | Technology |
|---|---|
| Markup | HTML5 (semantic) |
| Styling | CSS3 — custom properties, flexbox, CSS grid |
| Scripting | Vanilla JavaScript (ES6+) |
| Icons | Font Awesome 6.5 (CDN) |
| Typography | Google Fonts — Cormorant Garamond, Jost, Playfair Display |
| Forms | Netlify Forms |
| Deployment | Netlify (static hosting) |

No frameworks, no build tools, no dependencies beyond the CDN assets listed above.

---

## Features

**Cart System**
- Persistent cart via `localStorage`
- Add to cart from product cards and quick-view modal
- Quantity controls, item removal, cart clear
- Animated badge counter on cart icon
- Correct price resolution from the PRODUCTS data array — prevents string concatenation bugs

**Product Catalog**
- 14 products across five categories: Tropical, Orchid, Arrangements, Terrariums, Ferns
- Category filter tabs
- Sort by: Featured, Price Low to High, Price High to Low, Name A–Z, Name Z–A, Newest First, Best Selling
- Live search by name and category
- Sorting and filtering work in combination and persist until changed

**Quick View Modal**
- Product image, name, category, price, description
- Quantity selector
- Add to cart from modal

**Feedback System**
- Interactive star rating (1–5) with hover labels
- Form fields: name, email (optional), improvement checkboxes, comment, recommendation
- Submissions POST to Netlify Forms via `fetch`
- Submissions also saved to `localStorage` for immediate display
- Reviews rendered with avatar initials, full name, date, star rating, and label

**Theme Toggle**
- Light and dark mode
- Preference persisted in `localStorage`
- Toggle available in desktop navbar and mobile navigation drawer
- Both toggles remain in sync

**Responsive Design**
- Breakpoints at 768px and 480px
- Mobile navbar: logo left, cart and hamburger menu grouped right
- Product grid collapses to two columns on mobile
- Services, stats, and gallery grids adapt to two-column layouts on small screens
- Filter tabs become horizontally scrollable on mobile
- Checkout layout stacks vertically on mobile

**Checkout Scrollbar**
- Custom scrollbar on the cart items list
- Matches site color scheme — green-to-gold gradient thumb
- Cross-browser: `scrollbar-width` / `scrollbar-color` for Firefox, `::-webkit-scrollbar` for Chrome and Safari

---

## Deployment on Netlify

### Initial Deploy

1. Log in to [netlify.com](https://www.netlify.com)
2. From the dashboard, select **Add new site** > **Deploy manually**
3. Drag and drop the project folder, or connect via Git repository

### Netlify Forms Setup

The feedback form is pre-configured for Netlify Forms detection. No additional setup is required beyond deploying the site.

Form name: `leaf-bloom-feedback`

To view submissions:
1. Open the Netlify dashboard
2. Navigate to the site > **Forms** tab
3. Select `leaf-bloom-feedback`

The form uses a honeypot field (`bot-field`) for basic spam protection.

**Note:** Netlify Forms detection requires at least one live deployment. The form will appear in the Forms tab after the first successful submission on the deployed URL.

---

## Local Development

No build step is required. Open any HTML file directly in a browser, or serve the directory with any static file server.

Using the VS Code Live Server extension:

1. Open the project folder in VS Code
2. Right-click `index.html`
3. Select **Open with Live Server**

Using Python:

```bash
# Python 3
python -m http.server 3000
```

Using Node.js:

```bash
npx serve .
```

**Note:** Netlify Forms submissions will not work on localhost. They only function on the deployed Netlify URL. During local development, the feedback form falls back to saving entries in `localStorage` only.

---

## Browser Support

| Browser | Support |
|---|---|
| Chrome 90+ | Full |
| Firefox 88+ | Full |
| Safari 14+ | Full |
| Edge 90+ | Full |
| Mobile Chrome / Safari | Full |

---

## Known Constraints

- No backend or database. All cart and review data is stored in the browser via `localStorage` and clears when the user clears site data.
- Netlify Forms has a free-tier limit of 100 submissions per month. For higher volume, upgrade the Netlify plan or integrate a third-party form service.
- Product data is defined as a static array in `script.js`. To add or modify products, update the `PRODUCTS` array and the corresponding HTML product cards.

---

## License

This project is for academic and portfolio use only. All plant photography and brand assets are proprietary to Leaf & Bloom.
