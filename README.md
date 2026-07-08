# Quickline — Demo Website

This repo contains a fictional broadband/internet provider demo site used for Puzzel sales demos. It is **not** branded as Puzzel — it's a generic vertical demo (internet service provider) with the Puzzel chat widget embedded live on the page, so a chat demo can be run as if it were happening on a real customer's website.

---

## Site: Quickline (`index.html`)

**Built:** 8 July 2026 · **Live URL:** https://puzzelse.github.io/nimbus-fibre-demo/

### What it represents
A single-page marketing site for "Quickline," a fictional UK full-fibre broadband provider. It's the first of what may become a small set of vertical demo sites (e.g. broadband/telco, then other verticals) that William can use to run chat demos in a realistic customer-website context, rather than a bare test page.

### Purpose
Not tied to a specific deal — this is a reusable, generic demo environment. The goal is a page that looks like a real, polished consumer broadband site (hero, plans/pricing, features, coverage checker, testimonials, FAQ) with the Puzzel chat widget sitting live in the corner, so prospects can see chat working in a realistic, branded-but-not-Puzzel-branded setting.

### Branding
- Primary dark: `#0F2B2E` · Coral/CTA: `#FF6B4A` · Aqua accent: `#2DD4BF` · Warm background: `#FAF6F0`
- Fonts: Plus Jakarta Sans (body/UI), Fraunces italic (headline accent word)
- Source: designed to feel stylish and Nordic/tech-adjacent to Puzzel's own aesthetic (rounded pill buttons, dark hero with warm off-white sections, serif accent word in headline) **without reusing Puzzel's actual brand palette or fonts** (Puzzel's real colours are Nordic Depths navy, Wild Berry pink, Fjord Sun orange, Poppins/Noto Serif Display — deliberately not used here so the site doesn't read as Puzzel-branded).

### Sections included
Sticky nav, hero with live "speed test" style visual, "why us" feature grid, a mock coverage/postcode checker (front-end only, no real lookup), three-tier pricing plans, testimonials, FAQ accordion, CTA band, footer.

### Data & logic
All company details, pricing, speeds, and customer quotes are fictional and illustrative. No real customer or company data is used. The postcode coverage checker and FAQ accordion are simple front-end JS with no backend — clicking "Check" always returns the same illustrative "available" message.

### Chat widget
The Puzzel chat widget loader is embedded unmodified at the bottom of `index.html`:

```html
<script type="text/javascript">
(function (a, b) {
  var loader = a.createElement('script');
  loader.type = 'text/javascript';
  loader.src = 'https://app-cdn.puzzel.com/public/js/pzl_loader.js';
  loader.setAttribute('id', 'pzlModuleLoader');
  loader.setAttribute('data-customer-id', b);
  a.body.append(loader);
})(document, '99206');
</script>
```

Customer ID `99206` was supplied by William for this demo instance. No other Puzzel Widget API customisation has been made.

**Note:** on first deploy (brand name "Nimbus Fibre"), the console logged `pzl_loader abort bootstrap (no matching site found, or in active debug mode)` and the bubble didn't appear. After renaming the site to "Quickline", the widget bootstrapped correctly and greeted the visitor with pre-built "Quickline — Broadband built for you" branded content from customer `99206`'s own bot config. This confirms customer `99206`'s Puzzel Admin site-matching is tied to the "Quickline" name/branding specifically — keep the site named Quickline for this chat demo to keep working, or check with the Puzzel Admin config owner before renaming again.

### Backend / live data
None — this is a static site with no server-side component. Suitable for GitHub Pages hosting as-is.

### Notes for future vertical sites
This is the first of a planned set of "vertical" demo sites (per William's request). Future sites for other verticals should follow the same pattern: single self-contained HTML file, a distinct fictional company name and palette per vertical, and the same Puzzel chat widget snippet embedded at the bottom (swap the `data-customer-id` if a different instance is needed). Consider giving each vertical its own repo, or adding them as additional HTML files in this repo if they're meant to stay together as a suite — check with William when the next one is requested.

---

<!-- Add a new "## Site: ..." section above this line for each additional vertical demo site added to this repo -->
