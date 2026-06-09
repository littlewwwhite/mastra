---
'@mastra/playground-ui': minor
---

Added role-based semantic font tokens so consumers can swap fonts in one declaration. Components now reference `--font-display` (headlines, brand) and `--font-body` (UI, paragraphs) instead of type-based `--font-sans` / `--font-serif`. Existing utilities keep working through backward-compat aliases (`--font-sans` → `--font-body`, `--font-serif` → `--font-display`).

**Override fonts in your app**

```css
:root {
  --font-display: 'Mona Sans', system-ui, sans-serif;
  --font-body: 'Mona Sans', system-ui, sans-serif;
  --font-mono: 'Commit Mono', ui-monospace, monospace;
}
```

**Removed legacy raw font-name aliases** — `--geist-mono`, `--font-inter`, and the branded display-font alias are no longer exported. Use `--font-mono`, `--font-body`, and `--font-display` directly.

The package no longer ships font files — defaults are system fonts. Bring your own fonts via `@font-face` in your app and override the tokens above.
