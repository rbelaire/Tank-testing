# [COMPANY NAME] – UST Testing Website

A clean, industrial, single-page informational website for a Louisiana-based UST testing company. Built with plain HTML, CSS, and minimal JavaScript. No dependencies, no build tools required.

## Preview

Simply open `index.html` in any modern browser:

```bash
# macOS / Linux
open index.html

# Windows
start index.html

# Or drag index.html into your browser
```

The site works entirely offline with `file://` URLs.

## Customization

All placeholder text is clearly marked with `[PLACEHOLDERS]`. Replace each one with your actual information:

### Required Placeholders (appears multiple times):
- **[COMPANY NAME]** – Your business name
- **[PHONE NUMBER]** – Main contact number (also appears in sidebar and footer)
- **[EMAIL ADDRESS]** – Email for contact form and footer link

### Home / Hero Section:
- **[TAGLINE]** – Short catchy phrase (e.g., "Compliance Testing You Can Schedule")
- **[POSITIONING STATEMENT]** – One-sentence value prop (e.g., "Expert UST testing and compliance support for Louisiana fuel retailers")
- **[SERVICE AREA]** – Geographic coverage (e.g., "Serving Louisiana and the Gulf Coast")
- **[INTRO PARAGRAPH]** – 2–3 sentences explaining what you do

### Services Section:
- **[OPTIONAL NOTE]** – Custom notes for any service (leave blank or delete if not needed)

### Compliance Section:
- **[CUSTOM COMPLIANCE NOTE]** – Any special compliance detail you want to highlight

### About Section:
- **[FOUNDING YEAR]** – Year company was founded
- **[OWNER NAME]** – Founder/owner name
- **[OWNER BIO]** – 2–3 sentences about the owner's background
- **[MISSION STATEMENT]** – Your company mission (1–2 sentences)

### Credentials:
Replace these with your actual certifications (or delete the `<li>` if not applicable):
- **[ICC U3 CERTIFIED]** – "ICC Certified — Tank Tightness Testing (U3)"
- **[ICC U4 CERTIFIED]** – "ICC Certified — Cathodic Protection (U4)"
- **[LDEQ CERTIFIED]** – "LDEQ UST Certified Worker"
- **[LSLBC LICENSED]** – "Louisiana State Licensing Board for Contractors — Hazardous Materials, UST Subclassification"
- **[HAZWOPER]** – "OSHA HAZWOPER 40-Hour Certified"
- **[FULLY INSURED]** – "Fully Insured — General Liability, Pollution Liability, Professional Liability"

### Service Area Section:
- **[SERVICE PARISHES]** – Comma-separated list of parishes served (e.g., "Acadia, Iberia, Lafayette, St. Landry, St. Martin, Vermilion")
- **[ADDITIONAL SERVICE NOTES]** – Any extra service area details or federal facility work

### Contact Section:
- **[MAILING ADDRESS]** – Physical address (can span multiple lines)
- **[HOURS]** – Business hours

### Footer:
- **[LICENSE NUMBER]** – LSLBC license number

---

## Quick Setup Checklist

1. Open `index.html` in a text editor
2. Use Find & Replace (`Ctrl+H` or `Cmd+H`) to swap placeholders:
   - Replace `[COMPANY NAME]` with your actual name
   - Replace `[PHONE NUMBER]` with your number
   - Replace `[EMAIL ADDRESS]` with your email
   - Continue for each placeholder
3. Save the file
4. Open `index.html` in a browser to preview
5. Test the contact form (it uses `mailto:`)

---

## Adding a Logo

To add a logo to the sidebar header:

1. Save your logo as `logo.png` in the same folder as `index.html`
2. Add this line in `index.html` right before the `<h1 class="company-name">` tag:

```html
<img src="logo.png" alt="[COMPANY NAME] Logo" class="logo">
```

3. Add this CSS to `style.css` (around line 100, in the `.sidebar-header` section):

```css
.logo {
    max-width: 120px;
    height: auto;
    margin-bottom: 1rem;
}
```

---

## Design Overview

### Layout
- **Left sidebar navigation** (fixed on desktop, hidden toggle on mobile)
- **Right content area** with industrial clean aesthetic
- **Navy + Warm Gray + Rust Orange** color scheme
- **Responsive**: stacks on mobile, sidebar collapses to hamburger menu

### Fonts
- **Headings**: Inter (system fallback: -apple-system, Segoe UI)
- **Body**: Inter / Merriweather
- Loaded from Google Fonts (no files to ship)

### Colors
- Navy (`#1a2b4a`) – Primary brand color
- Warm Gray (`#6b7280`) – Body text
- Rust Orange (`#d97706`) – Accent / CTA
- Light Gray (`#f3f4f6`) – Backgrounds
- White / Light – Content areas

---

## Accessibility

- ✓ Semantic HTML (`<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- ✓ Skip-to-main-content link
- ✓ Proper heading hierarchy
- ✓ Form labels with `<label>` tags
- ✓ Color contrast WCAG AA (4.5:1 minimum)
- ✓ Focus states visible on all interactive elements
- ✓ Alt text on images (prepare to add)

---

## Contact Form

The contact form uses `mailto:` action — when users click "Send Message," it opens their default email client with the form content.

**To make it actually submit to an inbox**, you have two options:

### Option A: Keep `mailto:` (Free, Simple)
- Users see their email client open
- No server required
- Email subject is not prefilled

### Option B: Use a Backend Service (Recommended)
Replace the form's `action` attribute in `index.html` (line ~340):

```html
<!-- Option B.1: Formspree.io (free tier) -->
<form class="contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">

<!-- Option B.2: Basin (free tier) -->
<form class="contact-form" action="https://usebasin.com/f/YOUR_FORM_ID" method="POST">
```

Sign up, get a form ID, and replace `YOUR_FORM_ID`.

---

## Deployment

### Netlify (Recommended – 5 min)
1. Create a free [Netlify](https://www.netlify.com) account
2. Drag the `website/` folder onto the Netlify dashboard
3. Your site is live. Done.

### Cloudflare Pages (Also Easy)
1. Create a free [Cloudflare](https://pages.cloudflare.com) account
2. Connect your GitHub repo (or drag folder)
3. Set build command to: `(empty)` and publish directory to: `website/`
4. Done.

### Self-Hosted
Upload all files in the `website/` folder to any web host via FTP or file manager. That's it.

---

## File Structure

```
website/
├── index.html         (Main page – ~380 lines)
├── style.css          (Styling – ~360 lines)
├── script.js          (Interactivity – ~20 lines)
├── README.md          (This file)
└── logo.png           (Optional – add your logo here)
```

Total code: **~760 lines** (well under the target).

---

## Testing Checklist

- [ ] Opens in Firefox, Chrome, Safari, Edge
- [ ] Mobile: sidebar collapses to hamburger menu
- [ ] Contact form opens email client with To: and body filled
- [ ] Phone number links dial on mobile devices
- [ ] All navigation links scroll to correct sections
- [ ] Footer year auto-updates
- [ ] Print stylesheet hides sidebar (Ctrl+P)
- [ ] No console errors (open DevTools)
- [ ] Works offline (file:// protocol)

---

## Browser Support

- Chrome / Edge 90+
- Firefox 88+
- Safari 14+
- All modern mobile browsers

---

## License

Free to use and modify for your business.

---

## Questions?

All files are plain HTML, CSS, and JavaScript. No hidden dependencies, no frameworks, no tricks. Feel free to edit anything directly in your text editor.
