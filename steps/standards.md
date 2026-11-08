Any UI you add or change must meet WCAG 2.2 level AA. In particular:

- Semantics first: native `<button>`, `<a href>`, `<label>`, `<fieldset>`, headings in order,
  landmarks. ARIA only where HTML has no equivalent, and then complete (role, name, state).
- Every control has an accessible name; every form field has a visible, associated label;
  errors are announced and say how to fix them (3.3.1, 3.3.3).
- Images: meaningful `alt`, or `alt=""` when decorative. Icon-only buttons get a text name.
- Keyboard: everything works without a mouse, focus order follows the visual order, nothing
  traps focus except an open modal, and focus is always visible and not hidden behind sticky
  headers (2.4.7, 2.4.11).
- Contrast: 4.5:1 for text, 3:1 for large text, icons and control borders (1.4.3, 1.4.11).
- Pointer: targets at least 24×24 CSS px (2.5.8); drag actions have a single-pointer
  alternative (2.5.7).
- Motion: respect `prefers-reduced-motion`; no content that flashes more than 3 times a second.
- Don't rely on colour alone, and don't remove `outline` without a visible replacement.

If the project has an accessibility linter or test (`eslint-plugin-jsx-a11y`, axe, pa11y,
Lighthouse CI), run it on what you changed.
