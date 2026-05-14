# ✨ Glowing Icons

A lightweight, responsive social media icon bar with animated neon glow effects on hover. Built with pure HTML and CSS — no JavaScript required.

---

## 📸 Preview

A row of five social media icons centered on a black background. Each icon glows in its brand color when hovered:

| Icon | Brand Color |
|------|------------|
| Facebook | `#1877F2` (Blue) |
| Instagram | `#fd1d1d` (Red) |
| Snapchat | `#fffc00` (Yellow) |
| TikTok | `#4de8f4` (Cyan) |
| WhatsApp | `#25d366` (Green) |

---

## 📁 Project Structure

```
GlowingIcons/
├── GlowingIcons.html   # Main HTML file with icon markup
└── GlowingIcons.css    # Stylesheet with layout, glow effects, and responsive rules
```

---

## 🚀 Getting Started

### Prerequisites

No build tools or package managers needed. All you need is a modern web browser.

### Running Locally

1. Clone or download this repository.
2. Make sure `GlowingIcons.html` and `GlowingIcons.css` are in the **same directory**.
3. Open `GlowingIcons.html` in any modern browser (Chrome, Firefox, Edge, Safari).

```bash
# Optional: serve with a simple local server
npx serve .
# or
python3 -m http.server 8000
```

---

## 🧰 Dependencies

This project uses one external dependency loaded via CDN:

| Dependency | Version | Purpose |
|------------|---------|---------|
| [Font Awesome](https://fontawesome.com/) | `7.0.0` | Social media icon set (brands) |

The CDN link is included in the `<head>` of `GlowingIcons.html`:

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.0/css/all.min.css">
```

> **Note:** An active internet connection is required for the icons to load since Font Awesome is fetched from a CDN. For offline use, download and self-host Font Awesome.

---

## 🎨 How It Works

### CSS Custom Properties (`--color`)

Each `<a>` element receives its unique brand color via an inline CSS custom property:

```html
<a href="" style="--color:#1877F2;">
    <i class="fa-brands fa-facebook-f"></i>
</a>
```

The stylesheet then references `var(--color)` to apply that color to the icon text, background fill on hover, and the multi-layered `box-shadow` glow effect — all without any JavaScript or repeated CSS rules.

### Glow Effect

The neon glow is achieved with four stacked `box-shadow` layers of increasing spread:

```css
a:hover {
    background: var(--color);
    color: #000;
    box-shadow:
        0 0 5px var(--color),
        0 0 50px var(--color),
        0 0 75px var(--color),
        0 0 100px var(--color);
}
```

This creates a soft-to-intense bloom that mimics neon lighting.

### Layout

- Icons are centered both horizontally and vertically using Flexbox on the `body`.
- The `.icons` container uses `width: 80%` capped at `max-width: 500px`.
- Individual icons use `vw`-based sizing (`15vw`) capped at `80px × 80px` to scale fluidly with the viewport.

---

## 📱 Responsive Design

A media query at `max-width: 600px` adapts the layout for small screens:

| Property | Desktop | Mobile (≤ 600px) |
|----------|---------|-----------------|
| Icon layout | Row (horizontal) | Column (vertical) |
| Icon size | `15vw`, max `80px` | `20vw`, max `60px` |
| Glow spread | Up to `100px` | Up to `70px` (toned down for smaller screens) |

---

## ✏️ Customization

### Adding a New Icon

1. Find the Font Awesome brand class for your platform at [fontawesome.com/icons](https://fontawesome.com/icons).
2. Add a new `<a>` tag inside `.icons` with the desired brand color:

```html
<a href="https://x.com/yourhandle" style="--color:#000000;">
    <i class="fa-brands fa-x-twitter"></i>
</a>
```

### Changing a Color

Update the `--color` value in the `style` attribute of the relevant `<a>` tag:

```html
<!-- Change Instagram to its gradient purple -->
<a href="" style="--color:#C13584;">
    <i class="fa-brands fa-instagram"></i>
</a>
```

### Adjusting Icon Size

Edit the `max-width` / `max-height` properties in `GlowingIcons.css`:

```css
a {
    max-width: 80px;  /* Increase for larger icons */
    max-height: 80px;
}
```

### Changing Hover Animation Speed

Modify the `transition` value on the `a` selector:

```css
a {
    transition: 0.3s ease; /* Lower = faster, Higher = slower */
}
```

---

## 🌐 Browser Compatibility

| Browser | Support |
|---------|---------|
| Chrome | ✅ Full |
| Firefox | ✅ Full |
| Safari | ✅ Full |
| Edge | ✅ Full |
| IE 11 | ❌ Not supported (no CSS custom properties) |

---

## 📄 License

This project is open source and free to use. Attribution appreciated but not required.
