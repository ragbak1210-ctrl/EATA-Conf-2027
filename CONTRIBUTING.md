# Contributing to the EATA 2027 Website

Thank you for helping maintain the EATA 2027 conference website. This document outlines the process for making changes to the site.

---

## Who Should Be Contributing

This repository is intended for the **EATA 2027 web development and communications team**. If you are an external contributor with a bug report or suggestion, please open a GitHub Issue.

---

## Branching Strategy

We use a simple branching model:

| Branch | Purpose |
|--------|---------|
| `main` | Live production site — changes here go live |
| `develop` | Working branch for ongoing updates |
| `feature/xxx` | Feature-specific branches (e.g. `feature/add-speakers`) |
| `fix/xxx` | Bug fix branches (e.g. `fix/mobile-nav`) |

**Never push directly to `main`.** All changes should come via a Pull Request from `develop` or a feature branch.

---

## Making a Change

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-org/eata2027-website.git
   cd eata2027-website
   ```

2. **Create a new branch**
   ```bash
   git checkout -b feature/add-keynote-speakers
   ```

3. **Make your changes** in `index.html` (or other files as needed)

4. **Test locally**
   ```bash
   python3 -m http.server 8000
   ```
   Open [http://localhost:8000](http://localhost:8000) and verify all pages work correctly.

5. **Commit your changes**
   ```bash
   git add .
   git commit -m "feat: add keynote speaker profiles to Program page"
   ```

6. **Push and open a Pull Request**
   ```bash
   git push origin feature/add-keynote-speakers
   ```
   Then open a Pull Request against `develop` on GitHub.

---

## Commit Message Format

Please use the following prefixes in commit messages:

| Prefix | Use for |
|--------|---------|
| `feat:` | Adding new content or features |
| `fix:` | Fixing a bug or layout issue |
| `content:` | Updating text, dates, names |
| `style:` | CSS/visual-only changes |
| `asset:` | Adding/updating images, logos |
| `docs:` | Updating README or documentation |

**Examples:**
```
feat: add registration price table to Registration page
content: update abstract submission deadline to 15 Jan 2027
fix: correct mobile nav overflow on small screens
asset: add Gold sponsor logos (Nynas, Shell, Cargill)
```

---

## Content Update Checklist

Before submitting a PR with content changes, please verify:

- [ ] Spelling and grammar checked
- [ ] All dates are in format: `DD Month YYYY` (e.g. `15 January 2027`)
- [ ] Email addresses are correctly linked (`mailto:`)
- [ ] All pages still render correctly in Chrome and Firefox
- [ ] Mobile view checked (use browser DevTools — 375px width)
- [ ] No broken placeholder text left in (`TBC`, `To be confirmed`, `[ Logo ]`) unless intentional

---

## Image Guidelines

| Type | Format | Dimensions | Max Size |
|------|--------|-----------|----------|
| Speaker photos | JPG | 300×300px (square) | 150 KB |
| Sponsor logos | PNG (transparent bg) | Min 300px wide | 200 KB |
| Gallery photos | JPG | Min 800px wide | 500 KB |
| Venue/event images | JPG | Min 1200px wide | 800 KB |

All images go in the `/assets/` folder with descriptive, lowercase, hyphenated filenames:
- ✅ `prof-jane-smith-tu-delft.jpg`
- ✅ `sponsor-nynas-logo.png`
- ❌ `IMG_4821.jpg`
- ❌ `Sponsor Logo FINAL v2.PNG`

---

## Reporting Issues

Please use GitHub Issues for:
- Content errors (wrong dates, typos, broken links)
- Layout issues on specific browsers/devices
- Feature requests

Include:
- Page affected
- What you expected to see
- What you actually saw
- Screenshot if relevant
- Browser and OS

---

*For urgent issues, contact the web team at: [contact@eata2027.com](mailto:contact@eata2027.com)*
