# SCSS Typography

A port of [Tailwind CSS Typography](https://tailwindcss.com/docs/typography-plugin) (`@tailwindcss/typography`) in pure SCSS/CSS, with no dependencies on Tailwind or PostCSS.

[![npm](https://img.shields.io/npm/v/scss-typography.svg)](https://www.npmjs.com/package/scss-typography)
[![npm downloads](https://img.shields.io/npm/dm/scss-typography.svg)](https://www.npmjs.com/package/scss-typography)
[![jsDelivr hits](https://img.shields.io/jsdelivr/npm/hm/scss-typography)](https://www.jsdelivr.com/package/npm/scss-typography)
[![CSS gzip size](https://img.badgesize.io/marlen42/scss-typography/main/css/min/typography.min.css?compression=gzip&label=CSS%20gzip%20size)](https://github.com/marlen42/scss-typography/blob/main/css/min/typography.min.css)
[![MIT License](https://img.shields.io/github/license/marlen42/scss-typography)](LICENSE)

## Table of Contents

- [Quick Start](#quick-start)
- [What's Included](#whats-included)
- [Differences from Tailwind Typography](#differences-from-tailwind-typography)
- [Usage](#usage)
- [Copyright and License](#copyright-and-license)

## Quick Start

```bash
npm install scss-typography

pnpm add scss-typography

yarn add scss-typography

bun add scss-typography
```

### CDN

[https://www.jsdelivr.com/package/npm/scss-typography](https://www.jsdelivr.com/package/npm/scss-typography)

## What's Included

The package includes compiled and minified variants, along with their source maps.

<details>
<summary>View full contents</summary>

```text
css/
├── min/
│   ├── typography-colors-responsive.min.css
│   ├── typography-colors.min.css
│   ├── typography-core.min.css
│   ├── typography-reset.min.css
│   ├── typography-sizes-responsive.min.css
│   ├── typography-sizes.min.css
│   └── typography.min.css
├── typography-colors-responsive.css
├── typography-colors-responsive.css.map
├── typography-colors.css
├── typography-colors.css.map
├── typography-core.css
├── typography-core.css.map
├── typography-reset.css
├── typography-reset.css.map
├── typography-sizes-responsive.css
├── typography-sizes-responsive.css.map
├── typography-sizes.css
├── typography-sizes.css.map
├── typography.css
└── typography.css.map
```

</details>

Each variant is available in standard (`.css`) and minified (`.min.css`) form, with their respective source maps (`.css.map`).

## Differences from Tailwind Typography

### ✅ What is supported

| Feature             | Description                                     |
| ------------------- | ----------------------------------------------- |
| `prose`             | Base class with all typographic styles          |
| Sizes               | `prose-sm`, `prose-lg`, `prose-xl`, `prose-2xl` |
| Responsive variants | `sm:prose-lg`, `lg:prose-xl`, etc.              |
| Color themes        | `prose-red`, `prose-blue`, `prose-green`…       |
| Dark mode           | `prose-invert`                                  |

### ❌ What is not supported

- **Element modifiers**: `prose-headings:{utility}`, `prose-p:{utility}`, `prose-a:{utility}`, etc.
- **Plugin-generated utilities**: advanced classes that Tailwind generates dynamically at compile time are not included.
- **`dark:prose-invert`**: there is no reactive dark mode variant; use `prose-invert` directly as a static class.

If your project uses these features, you still need `@tailwindcss/typography` directly. For all other cases, this port is a drop-in replacement with no need for Tailwind in your stack.

## Usage

### In HTML

Usage is identical to `@tailwindcss/typography`. See the [official documentation](https://github.com/tailwindlabs/tailwindcss-typography) for a full reference. Everything marked ✅ in the table above works the same way here.

```html
<!-- Basic usage -->
<article class="prose">...</article>

<!-- With size and responsive -->
<article class="prose md:prose-lg lg:prose-xl">...</article>

<!-- With color theme -->
<article class="prose prose-slate">...</article>

<!-- Dark mode (static, not reactive) -->
<article class="prose prose-invert">...</article>

<!-- Exclude a block from prose styles -->
<article class="prose">
  <p>...</p>
  <div class="not-prose">
    <!-- This block does not inherit prose styles -->
  </div>
</article>
```

### In CSS/SCSS

**Full bundle**: includes colors, sizes, reset, and base styles:

```css
@import "scss-typography/css/typography.css";
```

**Individual variants**: import only what you need:

```scss
@import "scss-typography/css/typography-reset.css"; /* Tailwind Preflight */
@import "scss-typography/css/typography-core.css"; /* Base structure and default size (prose) */
@import "scss-typography/css/typography-sizes.css"; /* Extra sizes: prose-sm, prose-lg, prose-xl, prose-2xl */
@import "scss-typography/css/typography-sizes-responsive.css"; /* Responsive size variants: md:prose-lg, etc. */
@import "scss-typography/css/typography-colors.css"; /* prose-invert and color themes: prose-slate, prose-zinc… */
@import "scss-typography/css/typography-colors-responsive.css"; /* Responsive color variants: md:prose-slate, etc. */
```

## Copyright and License

Code licensed under [MIT](LICENSE). Copyright 2026 marlen42.

Based on [tailwindcss-typography](https://github.com/tailwindlabs/tailwindcss-typography) by [Tailwind Labs](https://github.com/tailwindlabs), also under the MIT license.
