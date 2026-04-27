# EATA 2027 Conference Website

**European Asphalt Technology Association Conference 2027**  
📍 Antwerp, Belgium  
📅 June 8–10, 2027  
🌐 [eata2027.com](#) *(placeholder)*

---

## Overview

This repository contains the official static website for the EATA 2027 Conference. The site is built as a **single-file HTML application** — no build tools, frameworks or server required. All pages, styles, scripts and embedded assets are contained within `index.html`.

---

## Project Structure

```
eata2027-website/
├── index.html          # ← Main website file (single-file application)
├── assets/             # ← Place all image assets here
│   ├── skyline.png     # Antwerp/Brussels skyline watercolour graphic
│   ├── logo-eata.png   # EATA logo
│   ├── speakers/       # Speaker headshot photos
│   │   └── *.jpg
│   ├── sponsors/       # Sponsor logos
│   │   └── *.png
│   └── gallery/        # Conference gallery images
│       └── *.jpg
├── README.md           # ← This file
├── .gitignore
└── CONTRIBUTING.md
```

> **Note:** The current `index.html` embeds the skyline image as base64 for portability. When deploying to production, images should be moved to the `/assets/` folder and referenced via relative paths for better performance and maintainability.

---

## Pages

| Page | Description |
|------|-------------|
| **Home** | Welcome message, key dates, sponsors sidebar, contact |
| **Plan Your Visit** | Venue info, travel guide, accommodation, Antwerp highlights |
| **Program** | Full agenda (3-day tabbed view), keynote speakers, workshops, social events, mobile app |
| **Registration** | Delegate packages, abstract submission, cancellation policy |
| **Sponsors & Partners** | Sponsor tiers, partner logos, sponsorship packages |
| **Media** | Press releases, news, photo gallery, media partners |

---

## How to Run Locally

No build step required. Simply open the file in any modern browser:

```bash
# Option 1 — Open directly
open index.html

# Option 2 — Serve via Python (recommended to avoid any CORS quirks)
python3 -m http.server 8000
# Then visit: http://localhost:8000

# Option 3 — Serve via Node.js
npx serve .
# Then visit: http://localhost:3000
```

---

## How to Update Content

All content is inside `index.html`. Each page section is clearly marked with comments:

```html
<!-- PAGE: HOME -->
<!-- PAGE: PLAN YOUR VISIT -->
<!-- PAGE: PROGRAM -->
<!-- PAGE: REGISTRATION -->
<!-- PAGE: SPONSORS & PARTNERS -->
<!-- PAGE: MEDIA -->
```

### Adding Real Images

1. Place image files in the `/assets/` directory
2. Replace `[ Image Placeholder ]` blocks with standard `<img>` tags:

```html
<!-- Before -->
<div class="visit-card-img">[ Image Placeholder ]</div>

<!-- After -->
<div class="visit-card-img" style="padding:0; overflow:hidden;">
  <img src="assets/antwerp-central-station.jpg" alt="Antwerp Central Station" style="width:100%; height:100%; object-fit:cover;">
</div>
```

### Adding Speaker Photos

In the Program page, replace the speaker card placeholders:

```html
<!-- Before -->
<div class="speaker-img">[ Photo ]</div>

<!-- After -->
<div class="speaker-img" style="overflow:hidden;">
  <img src="assets/speakers/firstname-lastname.jpg" alt="Speaker Name" style="width:100%; height:100%; object-fit:cover;">
</div>
```

### Adding Sponsor Logos

In the Sponsors page, replace the placeholder boxes:

```html
<!-- Before -->
<div class="sponsor-logo-box lg">[ Logo ]</div>

<!-- After -->
<div class="sponsor-logo-box lg" style="background:white; padding:8px;">
  <img src="assets/sponsors/company-name.png" alt="Company Name" style="max-height:54px; max-width:140px; object-fit:contain;">
</div>
```

### Updating Key Dates

In the Home page sidebar, update the date items:

```html
<div class="date-item"><strong>Abstract submission deadline:</strong> 15 January 2027</div>
<div class="date-item"><strong>Full paper submission deadline:</strong> 1 March 2027</div>
```

### Updating Registration Prices

Search for `€ TBC` in the Registration section and replace with actual prices:

```html
<div class="price">€ 850 <span>per person</span></div>
```

---

## Navigation

Navigation is handled by a lightweight JavaScript function. Clicking a nav link calls `showPage(pageId, element)` which shows/hides page `<div>` sections without a page reload. The agenda day tabs use `switchDay(dayId, element)` similarly.

---

## Colour Palette

| Variable | Hex | Usage |
|----------|-----|-------|
| `--crimson` | `#a8003c` | Primary brand colour |
| `--crimson-dark` | `#7a002c` | Hover states, dark elements |
| `--crimson-light` | `#c8005a` | Speaker name accents |
| `--magenta` | `#d4006a` | Secondary accent |
| `--white` | `#ffffff` | Backgrounds |
| `--off-white` | `#faf8f8` | Sidebar, footer |
| `--text-dark` | `#1a1a1a` | Primary text |
| `--text-mid` | `#444444` | Body text |
| `--text-light` | `#777777` | Captions, labels |

All colours are defined as CSS custom properties at the top of the `<style>` block in `index.html`.

---

## Deployment

### GitHub Pages

1. Push this repository to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, root `/`
4. Your site will be live at `https://yourusername.github.io/eata2027-website/`

### Netlify / Vercel (recommended)

1. Connect your GitHub repository
2. Set publish directory to `/` (root)
3. No build command required
4. Deploy

### Custom Domain

Update DNS records with your domain registrar to point to GitHub Pages / Netlify / Vercel as per their documentation.

---

## Browser Support

| Browser | Support |
|---------|---------|
| Chrome 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Edge 90+ | ✅ Full |
| IE 11 | ❌ Not supported |

---

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines on how to submit updates, report issues, or request changes.

---

## Contact

For technical queries about the website, please open a GitHub Issue.  
For conference enquiries: [contact@eata2027.com](mailto:contact@eata2027.com)  
For academic enquiries: [eata2027@paq.edu.pl](mailto:eata2027@paq.edu.pl)

---

*© 2027 European Asphalt Technology Association. All rights reserved.*
