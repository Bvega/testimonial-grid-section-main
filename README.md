# Testimonials Grid Section

## Overview

This project implements the "Testimonials Grid Section" challenge from Frontend Mentor using Bootstrap and custom CSS. The design handoff was provided as a Figma file, and the goal was to create a responsive, pixel-perfect layout that matches the given mockups.

* **Frontend Mentor Challenge**: [Testimonials Grid Section](https://www.frontendmentor.io/challenges/testimonials-grid-section-Nnw6J7Un7)
* **Live Demo**: *Add a link if deployed*

## Table of Contents

1. [Features](#features)
2. [Getting Started](#getting-started)
3. [Approach](#approach)
4. [Custom CSS Grid](#custom-css-grid)
5. [Reflection](#reflection)
6. [Design Files](#design-files)

## Features

* Responsive layout using Bootstrap’s grid system and utility classes
* Five testimonial cards with distinct styles and backgrounds
* Mobile-first design, scaling to tablets (2 columns) and desktops (4×2 grid)
* Custom CSS to span Kira’s card across two rows on large screens
* Semantic HTML and clear, descriptive commits

## Getting Started

1. **Clone the repository**

   ```bash
   git clone https://github.com/Bvega/testimonial-grid-section-main.git
   cd testimonial-grid-section-main
   git checkout bootstrap-refactor
   ```
2. **Open `index.html`** in your browser (or serve via Live Server in VS Code).
3. **Review the code** in `css/style.css` for the custom grid rules.

## Approach

1. **Bootstrap Setup**: Included Bootstrap via CDN in the `<head>` of `index.html`.
2. **Markup Refactor**: Converted the original grid into a structured set of `<div>`s with Bootstrap classes (`container`, `row`, `col-*`, etc.).
3. **Utility Classes**: Used Bootstrap’s spacing, typography, and utility classes to match the design’s padding, margins, and text styles.
4. **Custom Grid Override**: Added a CSS Grid layout on large screens (`@media (min-width: 992px)`) to explicitly place each testimonial card, ensuring Kira’s card spans top to bottom.

## Custom CSS Grid

In `css/style.css`, under the `@media (min-width: 992px)` section, the custom grid overrides Bootstrap’s `.row`:

```css
.testimonials-grid {
  display: grid !important;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: auto auto;
  gap: 1.5rem;
}
.testimonial-daniel   { grid-column: 1 / span 2; grid-row: 1; }
.testimonial-jonathan { grid-column: 3;           grid-row: 1; }
.testimonial-kira     { grid-column: 4;           grid-row: 1 / span 2; }
.testimonial-jeanette { grid-column: 1;           grid-row: 2; }
.testimonial-patrick  { grid-column: 2 / span 2;  grid-row: 2; }
```

## Reflection

I encountered challenges aligning the tall testimonial (Kira’s card) to span both rows within Bootstrap’s row/column system. To solve this, I used a CSS Grid wrapper on large screens, which gave precise control over the card positions while retaining Bootstrap for the core responsive behavior. Next time, I would explore using only Bootstrap subclasses (empty placeholder columns) for a pure-utility approach, but the CSS Grid solution provided the most straightforward, maintainable result.

## Design Files

* Desktop and mobile designs available in the `design/` folder.
* Figma prototype link provided in the challenge description.

---

*Project completed by Bolivar Vega Leon*
