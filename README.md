# Rosé Pine Dawn for renCal

[Rosé Pine Dawn](https://rosepinetheme.com/) as a light theme for [renCal](https://rencal.org). Assign it to the **light** slot in **Settings → Themes**, or pick it in Single mode.

## Local install

Installing via the GUI adds the plugin to `plugins.toml`:

| Platform | Path |
| --- | --- |
| macOS | `~/Library/Application Support/rencal/plugins.toml` |
| Linux | `~/.config/rencal/plugins.toml` |

```toml
plugins = [
  "gwenwindflower/rencal-theme-rose-pine-dawn"
]
```

For local development with live reloading, clone the repo and add the path to your `plugins.toml`:

```toml
plugins = [
  ...
  "/path/to/rose-pine-dawn",
]
```

renCal links the checkout into its plugins directory and reloads `themes/dawn.css` as you save it, so edits show up in the running app while Rosé Pine Dawn is selected.

## Colour mapping

Values come from the [official palette](https://rosepinetheme.com/palette/) and follow its role guidance. Dawn's lighter accents miss 4.5:1 as normal text on Base, so those roles use a darkened variant that keeps the role's OKLCH hue (Gold also loses some chroma to stay in sRGB). The variants are marked *text* below.

| renCal role | Dawn role | Value |
| --- | --- | --- |
| Background, sidebar | Base | `#faf4ed` |
| Cards, popovers | Surface | `#fffaf3` |
| Tooltips, toasts | Overlay | `#f2e9e1` |
| Text | Text | `#575279` |
| Muted text | Subtle *text* | `#696583` |
| Muted text on selection | Subtle *text*, darker | `#615d7a` |
| Hover, secondary, accent | Text tint, 4% and 8% | derived |
| Selection | Highlight Med, with Text | `#dfdad9` |
| Borders, inputs | Highlight High | `#cecacd` |
| Primary action, success | Pine | `#286983` |
| Focus ring | Iris | `#907aa9` |
| Today | Pine | `#286983` |
| Brand (year label, invites badge) | Rose *text* | `#a1514f` |
| Warning | Gold *text* | `#935c03` |
| Error, destructive | Love *text* | `#9d4f66` |

Filled Primary, Today and Brand controls use Base for their labels; Destructive uses white. Per-calendar and per-event colours are untouched.

## Contrast

Ratios are WCAG 2 contrast, computed from `themes/dawn.css` against renCal 0.9.3's `color-mix()` derivations, including the 4% white lighten on filled hovers.

| Pair | Ratio |
| --- | --- |
| Text on Base / Surface / Overlay / selection | 6.66 / 7.00 / 6.07 / 5.25 |
| Muted text, lowest (accent row on Base) | 4.53 |
| Muted text on selection | 4.52 |
| Labels on Primary / Primary hover | 5.59 / 5.11 |
| Labels on Today fill | 5.59 |
| Labels on Brand / Brand hover | 5.05 / 4.66 |
| Labels on Destructive / Destructive hover | 5.61 / 5.17 |
| Today, Brand, Warning, Error as text on Base | 5.59, 5.05, 5.10, 5.14 |
| Success text on its 10% badge tint | 4.87 |
| Error text in a focused destructive menu item | 4.72 |
| Focus ring on Base (non-text, 3:1) | 3.47 |

Event text is derived by renCal from each calendar's colour and is not set by this theme.

## Credits and license

The colour palette is [Rosé Pine](https://github.com/rose-pine/palette) by mvllow and the Rosé Pine contributors, used under the MIT License (Copyright (c) mvllow). See THIRD_PARTY_NOTICES.txt for details.
