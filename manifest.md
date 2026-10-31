# INMARIUM — Project Manifest

**INMARIUM 1.0 · The common language of design and code · by Jacaranda Group**

This manifest describes what we believe in and what the project is aimed at. It is derived from the current state of the repository: `README.md`, `CHANGELOG.md`, `framework.css`, the source layers (`foundation/`, `layout/`, `components/`, `utilities/`, `themes/`), the optional helper `inmarium.js`, and the documentation pages (`index.html`, `tutorial.html`, `reference.html`, `showcase.html`).

---

## 1. What we believe

### 1.1 Design and code should speak the same language
INMARIUM exists to close the gap between designers and developers. Layout, spacing, hierarchy and components are turned into readable words, so **designers can code and developers can design**. A class list is not an implementation detail — it is a sentence that describes a composition.

### 1.2 Read the interface before you build it
Every INMARIUM class list follows one grammar:
1. **Name the structure** — start with a visual primitive: `grid`, `flex`, `stack`, `cluster`, `container`.
2. **Describe the relationship** — add `cols-3`, `gap-6`, `items-center`, `justify-between`.
3. **Give it character** — finish with `p-6`, `rounded-xl`, `shadow-lg`, or a semantic color.

Example: `card stack gap-4 p-6 rounded-xl shadow-md` reads as *"a card, vertical, with medium space, generous padding, rounded corners and a soft shadow."*

### 1.3 Describe what you mean. Let the system handle the mechanics.
INMARIUM is not about writing less CSS at any cost. It is about giving design and development a **shared vocabulary**. Authors express intent; the framework resolves the mechanics.

### 1.4 CSS is the foundation; JavaScript is optional
Interactive behavior is **CSS-first**: components react to state classes and ARIA attributes (`.open`, `.active`, `[data-open]`). The tiny dependency-free `inmarium.js` is only progressive enhancement — you may toggle state yourself and skip the script entirely.

### 1.5 One clear cascade, no fights
The core rule: **components define defaults; utilities are final local overrides.** This is enforced by native CSS Cascade Layers (`@layer reset, tokens, base, themes, layout, components, utilities`), so utilities like `rounded-full`, `shadow-lg`, `p-8`, `w-full` override component defaults **without `!important`**, and project CSS loaded after `framework.css` stays easy to override.

### 1.6 Meaning before decoration
Components carry semantics first: buttons are `role + meaning + treatment + size` (`btn primary lg outline`), alerts communicate status, badges are short status labels, lists are chosen by meaning. Themes (`default`, `dark`, `pastel`, `corporate`) let the same interface change character via `data-theme` on `html` or any subtree — because the language is semantic tokens, not raw values.

### 1.7 Space is part of the sentence
A single shared scale drives gaps, margins and padding, so every composition keeps a common visual rhythm (`gap-2 … gap-16`, `p-*`, `m-*`).

### 1.8 Say what changes, where it changes
Responsive design is written plainly in the markup: `grid cols-4 tablet-cols-2 mobile-cols-1` states exactly what happens at each breakpoint. No hidden machinery, no memorized breakpoints syntax.

### 1.9 Discipline over completeness
We deliberately keep 1.0 small and intentional. Things we chose **not** to add: carousel, popover, scrollspy, mega-menu, autocomplete/multiselect, arbitrary-value syntax, peer/group variant systems, large filter/mask/blend matrices, and a utility generator. Every addition must earn its place (Bootstrap/Tailwind comparison audit → targeted additions only).

### 1.10 Stability with a path forward
Compatibility aliases are retained (`full` → `w-full`, `none` → `hidden`, `rounded-round` → `rounded-full`), but new code should prefer canonical names.

---

## 2. What the project is aimed at

### 2.1 Mission
Provide a complete, readable, production-ready **visual language and CSS framework** for the web — a vocabulary that covers layout, typography, color, spacing, components, responsiveness, theming and interaction states.

### 2.2 Concrete goals
- **Zero-dependency core.** Plain modern CSS (custom properties, cascade layers, container/grid/flex features) plus one optional ~3 KB script.
- **Predictable architecture.** Five ordered layers:
  - `foundation/` — reset and design tokens (colors with palette shades, spacing, radius, shadows, borders, transitions, animations, base typography);
  - `layout/` — primitives: display, alignment, flex, grid, stack, cluster, containers, sections, navigation, burger, responsive;
  - `components/` — full application patterns: buttons, button-group, forms + validation (`valid`, `invalid`, `required`, feedback), input-group, cards, lists, alerts, badges, tables, navbar 2.0, collapse, drawer, dropdown, modal, accordion, tabs, tooltip, toast, skeleton, progress, spinner, pagination, breadcrumbs, close;
  - `utilities/` — final local overrides: colors, spacing, shadows, typography, sizing, position, overflow, media, backgrounds, effects, transforms, interactivity, misc, radius, borders;
  - `themes/` — semantic token swaps per theme.
- **Accessibility by default.** State toggling keeps ARIA in sync (`aria-expanded`, `aria-selected`, `aria-hidden`, `data-open`); Escape closes modals, drawers and dropdowns.
- **Learnability.** Three documentation pages form a learning path:
  - `index.html` — the philosophy and language introduction;
  - `tutorial.html` — beginner-friendly handbook with live component lessons;
  - `reference.html` — complete searchable class reference (semantic colors, palette shades, named colors);
  - plus `showcase.html` — visual gallery of all components.
- **Adoption simplicity.** One entry point: `<link href="framework.css" rel="stylesheet">`, optionally `<script src="inmarium.js" defer></script>`.

### 2.3 Target audience
Designers who want to express compositions directly in markup, developers who want a semantic alternative to Bootstrap's rigidity and Tailwind's verbosity, and teams that need a shared vocabulary between design and engineering.

### 2.4 Scope boundaries (what we are NOT aiming at)
Not a JS framework, not a component library with runtime logic, not a utility generator, not an arbitrary-value escape hatch. If a feature does not fit the "describe what you mean" grammar, it stays out of 1.0.

---

## 3. Open items from the current audit

Recorded in `README.md` as pending checks for the next pass:
- `utilities/colors.css` — **INTERACTION**: verify and add interaction color classes if not defined elsewhere.
- `utilities/colors.css` — **STATUS**: verify whether additional status color classes are needed.

---

*Manifest version: aligned with Framework 1.0 final audit update (git `2f01e85 "Update system"`).*
