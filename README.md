# Community Library — Accessible Web Page

A demo page for a fictional community library built with web accessibility as the primary goal. It covers the most common patterns a real site needs: navigation, a data table, and a form — all meeting **WCAG 2.1 Level AA**.

🔗 [Live demo](https://ingbernardo.github.io/Web-Accesibility/)

---

## Accessibility features

### Semantic HTML
The page uses the right element for each job: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`, `<table>`, `<form>`. Screen readers use these landmarks to let users jump directly to any section without reading the whole page.

### Skip link
A "Skip to main content" link is the very first element in the DOM. It stays hidden visually until it receives keyboard focus, letting keyboard-only users skip the header and navigation and jump straight to the content.

### Heading hierarchy
Headings follow a strict order (h1 → h2) so screen reader users can navigate the page structure with the heading shortcut keys.

### Language declaration
`<html lang="en">` tells the browser and assistive technology what language the page is in, enabling correct pronunciation by text-to-speech engines.

### Page `<title>` and meta description
A descriptive title and meta description help users identify the page before they even open it — both in browser tabs and in search results.

### Navigation landmark
The `<nav>` element carries `aria-label="Main navigation"` so it is distinguishable from any other navigation region on the page.

### Accessible table
The opening-hours table has:
- A `<caption>` that describes the table's purpose.
- `scope="col"` on column headers and `scope="row"` on row headers, so screen readers announce the correct header for every cell.

### Fully labelled form
Every form control is paired with a visible `<label>` using the `for`/`id` association. Labels are never replaced by placeholder text. The `required` attribute is set in HTML (not just visually) so assistive technology announces it. `autocomplete` attributes on name and email fields let password managers and browsers fill them automatically, reducing cognitive load.

### Decorative image
The banner image uses `alt=""` so screen readers skip it — it adds no information the surrounding text doesn't already provide.

### Keyboard operability
Every interactive element — links, form fields, the Login button, the submit button — is reachable and operable with the Tab key alone. A custom `<div role="button" tabindex="0">` is used for the Login element to demonstrate how to make non-native elements keyboard-accessible.

### Visible focus indicators
A 3 px solid orange outline (`#d35400`) appears on every focused element, well above the 3:1 contrast ratio required by WCAG 1.4.11. The Login button uses a yellow outline (`#f2b134`) against the dark header background for the same reason.

### Colour contrast
| Element | Foreground | Background | Ratio | Criterion |
|---|---|---|---|---|
| Body text | `#1a1a1a` | `#ffffff` | 19.1:1 | 1.4.3 AA ✅ |
| Header text | `#ffffff` | `#0b3d63` | 7.8:1 | 1.4.3 AA ✅ |
| Nav links | `#0b3d63` | `#e8eef3` | 5.8:1 | 1.4.3 AA ✅ |
| Input border | `#555555` | `#ffffff` | 7.5:1 | 1.4.11 AA ✅ |
| Footer text | `#ffffff` | `#1a1a1a` | 19.1:1 | 1.4.3 AA ✅ |

---

## WCAG 2.1 criteria addressed

| # | Criterion | Level |
|---|---|---|
| 1.1.1 | Non-text content (alt text) | A |
| 1.3.1 | Info and relationships (semantic HTML, table headers) | A |
| 1.3.5 | Identify input purpose (autocomplete) | AA |
| 1.4.1 | Use of colour (not the only visual means) | A |
| 1.4.3 | Contrast (minimum) for text | AA |
| 1.4.11 | Non-text contrast (form borders, focus rings) | AA |
| 2.1.1 | Keyboard (all functionality available without a mouse) | A |
| 2.4.1 | Bypass blocks (skip link) | A |
| 2.4.2 | Page titled | A |
| 2.4.3 | Focus order (logical DOM order) | A |
| 2.4.7 | Focus visible (custom focus outlines) | AA |
| 3.1.1 | Language of page | A |
| 3.3.2 | Labels or instructions (visible labels on all inputs) | A |

---

## Tech stack

- Plain HTML5 and CSS3 — no frameworks, no JavaScript.
- All accessibility is achieved through native HTML semantics and CSS, which is the most robust foundation for assistive technology support.

---

## How to run it locally

```bash
git clone https://github.com/IngBernardo/Web-Accesibility.git
cd Web-Accesibility
# Open index.html in your browser — no build step needed
```

To test with a screen reader: **NVDA** (Windows, free) or **VoiceOver** (Mac, built-in, ⌘ + F5).
