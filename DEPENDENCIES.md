DEPENDENCIES
============

This file lists the primary CSS/JS libraries and notable assets used by the site, where they live in the repo (or their CDN), detected versions when available, and brief notes about their usage.

If you want, I can also add license attribution lines or move this content into the `README.md`.

Summary (high level)
- Core JS/CSS: jQuery + Bootstrap (bundled), Modernizr, Font Awesome
- Visual/UX: Animate.css, Owl Carousel, prettyPhoto, parallaxie, headline animations
- Utilities/plugins: isotope, imagesLoaded (bundled), jquery.vide, jquery.easing
- Analytics: Google Tag (gtag.js)
- Plotting (data section): dygraphs (in `data/`)

Detailed list
-------------
CSS files (local)
- css/bootstrap.min.css
  - Bootstrap CSS (site layout, grid, navbar, components)
  - JS counterpart included inside `js/all.js` (see below)
- style.css
  - Main site styles / theme
- css/custom.css
  - Additional site-specific overrides
- css/responsive.css
  - Responsive rules
- css/animate.css
  - Animate.css for CSS animations
- css/owl.carousel.css
  - Owl Carousel styles for carousels
- css/prettyPhoto.css
  - prettyPhoto lightbox styling
- css/camera.css
  - (present in `css/`) likely for a camera slider plugin used in older themes
- css/flaticon.css
  - Icon font (flaticon) styles
- css/font-awesome.css / css/font-awesome.min.css
  - Local Font Awesome files (but site currently loads Font Awesome from CDN: https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.1/css/all.min.css)
- css/versions.css
  - Site/variant specific styles

JS files (local)
- js/all.js
  - Large concatenated bundle. The file begins with the full jQuery 1.12.4 source and also includes Bootstrap v4.1.1 JS (see header). This is the primary JS bundle used site-wide.
  - Because jQuery + Bootstrap are bundled here, there are no separate top-level `jquery.min.js` / `bootstrap.min.js` includes.
- js/modernizr.js
  - Modernizr used for feature detection (included in `<head>`)
- js/jquery.easing.1.3.js
  - Easing functions used by animations
- js/parallaxie.js
  - Parallax scrolling helper
- js/headline.js
  - Headline word-rotation animation used in the landing hero
- js/custom.js
  - Site-specific JS controls and init code
- js/animate.js
  - Additional animation helper (project-specific)
- js/hoverdir.js
  - Hover direction animations for portfolio elements
- js/images-loded.min.js
  - Likely imagesLoaded (note: filename `images-loded` appears to be a typo or custom naming)
- js/isotope.min.js
  - Isotope layout library for filtering/arranging items
- js/jquery.prettyPhoto.js
  - prettyPhoto lightbox plugin
- js/jquery.vide.js
  - video backgrounds plugin
- js/map.js
  - Custom map wrapper (likely for Google Maps initialization)
- js/owl.carousel.js
  - Owl Carousel slider script
- js/portfolio.js
  - Portfolio/portfolio-plugin glue
- js/retina.js
  - Retina image helper
- js/scroll.js
  - Smooth scroll / scroll helpers

Data / plots
- data/Susy_2d/dygraph-combined.js
  - Dygraphs (plotting library) used in `data/Susy_2d/` pages

Fonts & Icons
- fonts/ (folder)
  - Local font files referenced by CSS
- Font Awesome
  - Loaded from CDN in `index.html`: https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.1/css/all.min.css
  - Local `css/font-awesome.css` files are also present
- Flaticon
  - `css/flaticon.css` and fonts referenced from `fonts/`

Analytics
- Google tag (gtag.js) included in `<head>` of `index.html` (measurement id present)

Where includes appear
- `index.html` head includes:
  - `css/bootstrap.min.css`, `style.css`, `css/responsive.css`, `css/custom.css`
  - `js/modernizr.js`
  - Font Awesome via CDN
- `index.html` bottom scripts include:
  - `js/all.js`, `js/jquery.easing.1.3.js`, `js/parallaxie.js`, `js/headline.js`, `js/custom.js` (plus other plugin files listed in repo)

Notes, recommendations, and next steps
-------------------------------------
- `js/all.js` is a large bundle that contains jQuery 1.12.4 and Bootstrap 4.1.1. If you want to upgrade jQuery/Bootstrap or use CDN-delivered versions, consider splitting this bundle into separate vendor files so they can be updated independently.
- There are local Font Awesome files but the site uses a CDN include for Font Awesome 5.15.1 — keep one source to avoid duplication and version drift.
- `images-loded.min.js` filename looks like a typo; verify whether it's `imagesloaded` and whether you want the canonical `imagesloaded` library (different naming doesn't change functionality but may confuse later contributors).
- Consider adding `DEPENDENCIES.md` (this file) to `README.md` or adding license attributions for third-party libraries (especially if publishing the site publicly).

If you'd like, I can:
- Commit this file to the repository (already created in workspace). 
- Add a short `DEPENDENCIES` section to `README.md` and link to license URLs.
- Split `js/all.js` into vendor and app bundles and switch to CDN-hosted vendor scripts (I can prepare a safe refactor plan and test locally).

Last scan summary
- I inspected `css/` and `js/` directories and `index.html`. The main libraries are listed above; versions were detected when present (jQuery 1.12.4 and Bootstrap 4.1.1 inside `js/all.js`, Font Awesome 5.15.1 via CDN). Additional plugin scripts are local files under `js/`.

If you want, I can also open each HTML page (e.g., `research.html`, `about.html`) and annotate which pages use which plugins, or create a `LICENSES.md` with attribution links and copies of license headers where appropriate.
