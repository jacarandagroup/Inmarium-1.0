# INMARIUM Framework 1.0

Core rule: **components define defaults; utilities are final local overrides**. The main `framework.css` uses CSS Cascade Layers, so utilities such as `rounded-full`, `shadow-lg`, `p-8`, `w-full`, and color helpers override component defaults without `!important`. Project CSS loaded after `framework.css` remains easy to override.

## Main composition example

```html
<form class="form card stack gap-4 p-8 rounded-xl shadow-lg max-w-lg">
  <div class="field">
    <label class="label" for="name">Name</label>
    <input class="input lg" id="name" type="text">
  </div>
  <button class="btn primary lg rounded-full w-full">Start</button>
</form>
```

## Responsive grid

```html
<div class="grid cols-4 tablet-cols-2 mobile-cols-1 gap-8 items-stretch">...</div>
```

## Themes

Set `data-theme` on `html` or any subtree: `default`, `dark`, `pastel`, `corporate`.

## Stateful CSS components

Interactive components are CSS-first. You may toggle `.open`, `.active`, or documented ARIA state from your own controller, or include the optional dependency-free `inmarium.js` helper. Examples: `.dropdown.open`, `.modal.open`, `.drawer.open`, `.accordion-item.open`, `.tab.active`.

## Compatibility aliases retained

`full` aliases `w-full`, `none` aliases `hidden`, and `rounded-round` aliases `rounded-full`. New code should prefer the canonical names.

## Documentation pages
- `index.html` — INMARIUM overview and language introduction.
- `tutorial.html` — beginner-friendly handbook with live component lessons.
- `reference.html` — complete searchable Framework 1.0 class reference, including semantic colors, palette shades, and named colors.


## Framework 1.0 final audit additions

Framework 1.0 now includes Navbar 2.0, generic Collapse, Drawer, Close, Button Group, Input Group, form validation states, Toast, Skeleton, background utilities, text balancing/clamping, a small effects/transform/interactivity set, and `inmarium.js` for optional progressive enhancement.

### JavaScript

CSS remains the foundation. Interactive behavior is optional and dependency-free:

```html
<script src="inmarium.js" defer></script>
```

The script only toggles state classes/attributes for components such as navbar collapse, drawer, modal, accordion, tabs, dropdown and toast.
