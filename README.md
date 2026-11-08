# Night Porter pack: a11y

WCAG 2.2 AA accessibility for web front-ends: semantics, names and labels, keyboard and focus, contrast, target size and motion.

A [Night Porter](https://night-porter.com) pack: prompts only, no code. Like every pack it can
only make Night Porter stricter: it adds instructions and read-only gates, and can't skip its
trust rules, checks or approvals.

```sh
nightporter market update
nightporter pack add a11y
```

Then enable it in `[defaults]` or a repo file (`repos/<forge>/<owner>/<repo>.toml`):

```toml
packs = ["a11y"]
```

| step | hook | what it does |
|---|---|---|
| `standards` | `pre_fix` | WCAG 2.2 AA rules for any UI the agent adds or changes; runs the project's a11y linter if it has one |
| `review` | `pre_push` | blocks keyboard traps, removed focus styles, unnamed controls and images without text alternatives; asks before incomplete custom widgets, low contrast, motion or small targets |

A pre-push gate reads the diff, not the rendered page, so it complements (not replaces) axe,
pa11y or manual testing with a screen reader.

Read every file before installing: they steer an agent that can edit your code. See
[Writing packs](https://docs.night-porter.com/writing-packs).

Licensed under either of Apache-2.0 or MIT, at your option.
