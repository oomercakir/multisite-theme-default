# multisite-theme-default

Default starter theme for the [multisite-cms](https://github.com/oomercakir/multisite-cms-platform) platform.

Pure-Liquid theme — every section/block carries its `{% schema %}` JSON block inline,
following the Horizon (Shopify) convention.

## Structure

```
asset/         # CSS, JS bundled with the theme
block/         # Reusable atomic + composite blocks
layout/        # Top-level page layouts
partial/       # Header/footer + small reusable snippets
section/       # Page sections (each with {% schema %})
```

## Usage

The platform `pnpm pull-themes` script clones this repo into a local
`.theme-cache/default/` and bundles the file contents into
`starter-themes.data.ts`. New tenants get a per-site copy on signup;
existing tenants see a "Tema güncellemesi mevcut" banner when this
repo gets new commits.

## Authoring rules

- Every section/*.liquid + block/*.liquid MUST have a `{% schema %}` block
- Schema field types: see the platform repo's `packages/cms/src/types/field.ts`
- Color variables: use `var(--color-*)` so sections inherit color schemes
