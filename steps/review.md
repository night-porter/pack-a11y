Review the front-end parts of the diff (HTML, templates, JSX/TSX, Vue, Svelte, CSS) against
WCAG 2.2 AA. Ignore files that don't affect what users see or how they interact.

Block (`block`) if the diff:
- adds an interactive element that keyboard users can't reach or operate (click handlers on
  `div`/`span` without role, `tabindex` and key handling; `tabindex` > 0);
- removes focus indication (`outline: none` / `0`) without a visible replacement;
- adds a form control, button or link with no accessible name;
- adds an image or icon that carries meaning with no text alternative.

Ask for approval (`needs_approval`) if the diff:
- adds custom widgets (menus, tabs, dialogs, comboboxes) whose ARIA roles, states or focus
  handling look incomplete;
- sets text or control colours whose contrast you can work out and is below 4.5:1 (text) or
  3:1 (large text, icons, borders);
- adds animation or auto-playing media without a `prefers-reduced-motion` or pause option;
- adds pointer targets smaller than 24×24 CSS px or drag-only interactions.

Otherwise `pass`. In the summary, name the file, line and WCAG success criterion for each problem.
