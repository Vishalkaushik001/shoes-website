# Shoes Website — E-commerce Storefront Template

A responsive, multi-page front-end template for a shoe/footwear e-commerce store. Built with HTML, CSS/SCSS, and JavaScript (Bootstrap + jQuery), based on the **Karma Shop** template.

## Pages Included

| Page | File | Purpose |
|---|---|---|
| Home | `index.html` | Landing page — banners, featured categories, products |
| Category | `category.html` | Product listing / category browsing with filters |
| Single Product | `single-product.html` | Individual product detail page |
| Cart | `cart.html` | Shopping cart summary |
| Checkout | `checkout.html` | Checkout / order form |
| Order Confirmation | `confirmation.html` | Post-checkout confirmation screen |
| Order Tracking | `tracking.html` | Track an order's status |
| Blog | `blog.html` | Blog listing page |
| Single Blog Post | `single-blog.html` | Individual blog post view |
| Contact | `contact.html` | Contact form (submits to `contact_process.php`) |
| Login | `login.html` | User login / sign-in page |
| Elements | `elements.html` | UI component/style guide (buttons, alerts, etc.) |

## Tech Stack

- **Markup:** HTML5
- **Styling:** CSS3 and SCSS (compiled with [Prepros](https://prepros.io/), see `prepros-6.config`)
- **Frameworks/Libraries:**
  - Bootstrap
  - jQuery
  - Owl Carousel (sliders)
  - Magnific Popup (lightbox/modals)
  - Nice Select (custom dropdowns)
  - Ion Range Slider / noUiSlider (price filters)
  - Linearicons / Themify Icons / Font Awesome (icon sets)
  - Google Maps (`gmaps.min.js`) for the contact page
- **Contact form backend:** PHP (`contact_process.php`) — sends form submissions via PHP `mail()`

## Project Structure

```
shoes-website/
├── index.html, category.html, single-product.html, cart.html, ...   # Page templates
├── contact_process.php        # PHP mail handler for the contact form
├── css/                        # Compiled stylesheets + vendor CSS (Bootstrap, icon fonts, sliders, etc.)
├── scss/                       # SCSS source files (compiles to css/main.css)
├── js/
│   ├── vendor/                 # jQuery, Bootstrap JS, Popper
│   └── *.js                    # Plugin scripts + main.js (site behavior)
├── img/                        # Site images (banners, products, categories, blog, brand logos, etc.)
├── fonts/                      # Icon/web fonts
├── Karma Shop-doc/             # Original template documentation (reference only)
└── prepros-6.config            # Prepros build config for compiling SCSS
```

## Getting Started

This is a static front-end template — no build step is strictly required to view it.

### Option 1: Open directly
Simply open `index.html` in a browser.

### Option 2: Serve locally (recommended, avoids path/CORS issues)
```bash
# From the project root
python -m http.server 8000
# then visit http://localhost:8000
```

### Editing styles (SCSS)
The `scss/` folder contains the SCSS source; compiled output lives in `css/main.css`. If you edit the SCSS, recompile with [Prepros](https://prepros.io/) (the project already includes a `prepros-6.config`) or any Sass compiler:
```bash
sass scss/main.scss css/main.css
```

### Contact form
`contact.html` posts to `contact_process.php`, which uses PHP's `mail()` function to forward submissions. This requires a PHP-enabled server (e.g., run via `php -S localhost:8000` or deploy to PHP hosting) — it will not work from a plain static file server.

## Notes & Suggestions for Improvement

- This is a static template — there's no real product database, cart persistence, or payment processing wired up yet. Cart/checkout pages are UI only.
- The recipient email in `contact_process.php` is hardcoded; update it before deploying, and consider moving it to an environment variable or config file.
- Several meta tags (e.g., page description) are currently empty in `index.html` — worth filling in for SEO.
- The `Karma Shop-doc` folder is the original template's documentation and isn't needed for the site to run; consider removing it from the deployed build (or keep it in a separate `/docs` reference branch).
- No `.gitignore` — consider adding one to exclude editor/OS files going forward.

## Credits

Built on the **Karma Shop** HTML e-commerce template. Icon fonts, sliders, and other third-party plugins are included under `css/`, `js/`, and `fonts/` — check the `Karma Shop-doc` folder for original licensing/attribution details.

## License

No license specified. If this template's original license permits redistribution, consider adding a `LICENSE` file; otherwise keep usage private.
