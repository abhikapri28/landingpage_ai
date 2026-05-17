# landingpage_ai
Trying to think of more interactive and enhanced version of our landing page
---

## Quick Start

1. Clone the Repo or download landing page.
2. Open it in any browser — done.

---

## File Structure

```
nexusai-landing.html
README.md
```

---

## External Dependencies (CDN)

| Resource | Provider | Purpose |
|---|---|---|
| Syne + DM Sans fonts | Google Fonts | Display & body typography |
| Tabler Icons v3 | jsDelivr | All UI icons |

No npm, no bundler, no build step required.

---

## Page Sections

| # | Section | ID |
|---|---|---|
| 1 | Navbar | — |
| 2 | Hero | `#home` |
| 3 | Client Logo Strip | — |
| 4 | Services | `#services` |
| 5 | Process / How It Works | `#process` |
| 6 | Industries | `#industries` |
| 7 | Testimonials | `#testimonials` |
| 8 | Pricing | `#pricing` |
| 9 | FAQ Accordion | `#faq` |
| 10 | Final CTA | `#cta` |
| 11 | Footer | — |

---

## Customisation Guide

### 1. Company Name & Branding

```html
<!-- Navbar logo -->
<a href="#" class="nav-logo">Your<span>Brand</span></a>

<!-- Footer logo -->
<span class="footer-logo">Your<span>Brand</span></span>
```

The `<span>` inside the logo renders in the accent colour (indigo). You can split your name at any point.

---

### 2. Colours

All colours are defined as CSS variables at the top of the `<style>` block:

```css
:root {
  --accent:        #0f0e1a;   /* dark navy — headings, navbar bg */
  --accent2:       #4f46e5;   /* indigo — buttons, icons, highlights */
  --accent2-hover: #4338ca;   /* indigo hover state */
  --text:          #111118;   /* body text */
  --muted:         #6b7280;   /* secondary text */
  --surface:       #f7f6f3;   /* light section backgrounds */
  --border:        rgba(0,0,0,0.09);
  --tag-bg:        #ede9fe;   /* pill / badge backgrounds */
  --tag-text:      #4338ca;   /* pill / badge text */
  --dark-bg:       #0f0e1a;   /* testimonials dark section */
}
```

To change the brand colour, update `--accent2` and `--accent2-hover` to your hex values.

---

### 3. Fonts

Fonts are imported from Google Fonts at the top of `<head>`:

```html
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:...&display=swap" rel="stylesheet" />
```

- **Syne** — used for all headings (`font-family: 'Syne', sans-serif`)
- **DM Sans** — used for body text and UI elements

To swap fonts, replace the Google Fonts URL and update the `font-family` values in `:root` or the relevant CSS classes.

---

### 4. Hero Section

```html
<!-- Availability badge -->
<div class="hero-badge">
  <div class="hero-badge-dot"></div>
  Now taking projects for Q3 2026   <!-- ← update this -->
</div>

<!-- Main headline -->
<h1>We build <em>AI systems</em><br>that work while<br>you sleep</h1>

<!-- Subheadline -->
<p class="hero-sub">Custom AI tools and integrations for businesses...</p>

<!-- Stats row -->
<strong><em>40</em>+</strong>   <!-- number in accent colour -->
<span>Clients automated</span>  <!-- label below -->
```

The floating cards on desktop are purely decorative. Edit their metric numbers inside `.hero-float.left` and `.hero-float.right`.

---

### 5. Services Cards

Each card follows this pattern:

```html
<div class="service-card">
  <div class="service-icon"><i class="ti ti-ICON-NAME"></i></div>
  <h3>Service Title</h3>
  <p>Short description of the service.</p>
  <span class="service-tag">Optional tag</span>   <!-- remove if not needed -->
</div>
```

Find icon names at: **https://tabler.io/icons** — use the outline version, e.g. `ti-robot`, `ti-brain`.

---

### 6. Process Steps

```html
<div class="step-item">
  <div class="step-num">01</div>
  <div class="step-body">
    <h3>Step Title</h3>
    <p>Step description.</p>
  </div>
</div>
```

The timeline visual on the right is a separate decorative element. Update the day ranges inside `.tl-duration` spans to match your actual delivery times.

---

### 7. Testimonials

```html
<div class="tcard">
  <blockquote>"Quote goes here."</blockquote>
  <div class="tcard-author">
    <div class="tcard-avatar">AB</div>   <!-- initials, 2 chars -->
    <div>
      <div class="tcard-name">Full Name</div>
      <div class="tcard-role">Title, Company</div>
    </div>
  </div>
  <div class="tcard-metric">
    <div class="metric-num">97%</div>
    <div class="metric-label">metric label<br>second line</div>
  </div>
</div>
```

Avatar background colour is set via inline style: `style="background:#0891b2"`. Pick any colour that works with white text.

---

### 8. Pricing

Update the three pricing tiers — name, price, description, and feature list:

```html
<div class="pricing-price">₹49,000<sub>/project</sub></div>
```

Change `₹` to `$`, `€`, or any currency symbol. For "Custom" pricing, leave the price as text with no `<sub>` tag.

Feature list items use two states:

```html
<li><i class="ti ti-check"></i> Included feature</li>
<li class="crossed"><i class="ti ti-x"></i> Not included</li>
```

The featured card (middle by default) uses `class="pricing-card featured"` which adds a 2px indigo border and the "Most popular" badge.

---

### 9. FAQ

```html
<div class="faq-item">
  <button class="faq-question">
    Question text here?
    <i class="ti ti-plus"></i>
  </button>
  <div class="faq-answer">
    Answer text here. Can be multiple sentences.
  </div>
</div>
```

The accordion is powered by vanilla JS at the bottom of the file. Only one item can be open at a time.

---

### 10. CTA Buttons

The main CTA buttons currently have no `href`. Connect them to your booking or contact tool:

```html
<!-- Calendly example -->
<button onclick="window.open('https://calendly.com/yourlink', '_blank')">
  Book a free call
</button>

<!-- WhatsApp example -->
<button onclick="window.open('https://wa.me/919999999999', '_blank')">
  Message on WhatsApp
</button>

<!-- mailto example -->
<button onclick="window.location.href='mailto:hello@yourdomain.com'">
  Send us a message
</button>
```

---

### 11. Contact Details (Footer)

```html
<li><a href="mailto:hello@nexusai.in">hello@nexusai.in</a></li>
<li><a href="tel:+919999999999">+91 99999 99999</a></li>
<li><a href="#">New Delhi, India</a></li>
```

---

### 12. Social Links (Footer)

```html
<a href="https://linkedin.com/company/yourpage" class="social-link">
  <i class="ti ti-brand-linkedin"></i>
</a>
```

Replace `#` with your actual profile URLs for LinkedIn, X (Twitter), Instagram, and email.

---

### 13. Logo Strip

Replace the placeholder company names with your actual client names or remove the section entirely:

```html
<div class="logos-row">
  <div class="logo-item">Client One</div>
  <div class="logo-item">Client Two</div>
  ...
</div>
```

If you have client logo image files, replace each `<div class="logo-item">` with an `<img>` tag styled to `height: 28px; opacity: 0.5; filter: grayscale(1);`.

---

## Deployment Options

| Platform | How to deploy |
|---|---|
| **Netlify** | Drag and drop the HTML file at netlify.com/drop |
| **Vercel** | `vercel --prod` from the folder, or drag-drop via dashboard |
| **GitHub Pages** | Push to a repo, enable Pages in Settings → select the file |
| **cPanel / shared hosting** | Upload via File Manager to `public_html/` |
| **Any static host** | It's one file — upload it anywhere |

---

## Browser Support

Works in all modern browsers: Chrome, Firefox, Safari, Edge. No polyfills needed. JavaScript features used (IntersectionObserver, classList) are supported in all browsers released after 2018.

---

## Fonts Not Loading?

The page uses Google Fonts via CDN. If you're viewing offline or on a restricted network, fonts will fall back to the system sans-serif. To self-host fonts:

1. Download the font files from [google-webfonts-helper.herokuapp.com](https://gwfh.mranftl.com)
2. Place them in a `/fonts/` folder
3. Replace the Google Fonts `<link>` with `@font-face` declarations pointing to your local files

---

## License

This file was generated for your personal or commercial use. You are free to modify, deploy, and build on it without restriction. No attribution required.
