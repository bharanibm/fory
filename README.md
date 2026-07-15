# Fory

A responsive, asymmetrical image grid gallery featuring colorful translucent overlays and smooth transitions. The project leverages an advanced CSS Grid matrix that adapts seamlessly between desktop spans and single-column mobile viewports.

## 🔗 Links

* **Live Demo**: [fory-demo](https://fory-steel.vercel.app/)
* **Repository**: [github.com/bharanibm/fory](https://github.com/bharanibm/fory)

## 🌟 Features

* **Asymmetric CSS Grid**: Built using an intricate 3-row by 3-column layout with unequal structural column tracking (40% / 20% / 40%).
* **Translucent Color Overlays**: Each grid item features a unique, colorful background tint utilizing alpha-channel (`hsla`/`rgba`) opacity.
* **Hover Reveals**: Smooth `1s ease` transitions that fade out the color overlays to fully reveal the underlying background graphics on hover.
* **Mobile Responsive**: Implements a dedicated break-point query at `425px` that strips grid column spans and stretches cards into a unified stacked column.

## 🛠️ Tech Stack

* **HTML5**: Structured markup utilizing semantic `<main>` and `<article>` tags.
* **CSS3**: Layout scaffolding using CSS Grid, Flexbox alignment, and media query breakpoint constraints.

## 📁 Project Structure

```text
📂 fory
 ├── 📂 assets          # Local background image assets (pic01 to pic06)
 ├── 📄 index.html      # Structural layout of the grid cards
 ├── 📄 style.css       # Core layout rules, color profiles, and media queries
 └── 📄 README.md       # Project documentation
```

## 🚀 Getting Started

1. Clone this repository locally:
   ```bash
   git clone https://github.com/bharanibm/fory.git
   ```
2. Open `index.html` directly inside any web browser.

## 🧩 Architectural Breakdown

### Grid Structure (Desktop)
The default desktop view establishes a 3-row layout where each row has a fixed height of `450px`, partitioned across three explicit width percentages:
```css
main {
    display: grid;
    grid-template-rows: repeat(3, 450px);
    grid-template-columns: 40% 20% 40%;
}
```
Alternating items (`.art2`, `.art3`, `.art6`) utilize `grid-column: span 2;` to construct an alternating, puzzle-like structural dynamic.

### Mobile Breakpoint Configuration
When viewports drop below `425px`, the complex layout smoothly shifts to structural blocks:
```css
@media (max-width: 425px) {
    main {
        grid-template-rows: repeat(6, 400px);
        grid-template-columns: 100%;
    }
    .art2, .art3, .art6 {
        grid-column: span 1;
    }
}
```
