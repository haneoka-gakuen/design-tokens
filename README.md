# Haneoka design tokens

Shared Material Design 3 colors, typography, shapes, motion, elevation, density and component roles for websites and authoring tools.

```css
@import "@haneoka/design-tokens/tokens.css";

.panel {
  color: var(--md-sys-color-on-surface);
  background: var(--md-sys-color-surface-container);
  border-radius: var(--md-sys-shape-corner-large);
}
```

Set `data-theme="dark"` on the document element to select the dark scheme. Set `data-seed="band-1"` through `band-5` to select a band scheme. All schemes retain contrast-adjusted Material system roles. Font families can be supplied through `--md-ref-typeface-brand`, `--md-ref-typeface-plain` and `--md-ref-typeface-code`.

```ts
import { materialTheme } from "@haneoka/design-tokens";
console.log(materialTheme.sourceColors.primary);
```

`--md-sys-*` provides the common system contract. `--md-comp-*` supplies sizes and color roles for browsing, playback and authoring components. Applications import the same stylesheet in their preferred framework; CSS and the small theme descriptor are independently usable.

## Development

```sh
pnpm install --frozen-lockfile
pnpm build
pnpm typecheck
pnpm generate
```

`generate` rebuilds the committed light/dark palettes using Material color utilities. Runtime theme switches change attributes without generating colors in the browser. The package includes reduced-motion tokens and safe-area metrics.
