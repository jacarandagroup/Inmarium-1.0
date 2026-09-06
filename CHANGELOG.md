# INMARIUM Framework 1.0 — final audit update

This update keeps the approved Framework 1.0 architecture and closes the most important production gaps found during the Bootstrap/Tailwind comparison.

## Added

- Navbar 2.0: `navbar-inner`, `navbar-menu`, `navbar-actions`, `navbar-text`, `navbar-toggle`, `navbar-collapse`, responsive expansion, sticky/fixed/transparent/solid/blur/bordered/shadow/compact modifiers.
- Generic `collapse` state primitive.
- `drawer` with left/right/top/bottom positions and backdrop.
- Reusable `close` control.
- `button-group` and vertical variant.
- `input-group` and `addon`.
- Form validation: `valid`, `invalid`, `valid-feedback`, `invalid-feedback`, `required`, field success/danger states.
- `toast` feedback component and `toast-stack`.
- `skeleton` loading placeholders.
- Background utilities: sizing, positioning, repeat and attachment.
- Modern typography: `text-balance`, `text-pretty`, whitespace helpers and line clamps.
- Small, intentional effects/transform/interactivity utility sets.
- `inmarium.js`: tiny dependency-free progressive-enhancement helper for state-based components.

## Deliberately not added to 1.0

Carousel, popover, scrollspy, mega-menu, autocomplete/multiselect, arbitrary-value syntax, peer/group variant systems, large filter/mask/blend utility matrices, and a utility generator remain outside the 1.0 scope.
