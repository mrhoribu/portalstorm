# Portal Storm Gaming

Source for [portalstorm.net](https://portalstorm.net/), the home page of **Portal Storm Gaming**:
a casual group of gamers out to explore, conquer, and just outright have fun together. There's no
formal application process. Everyone is respected and welcomed.

- **Discord:** the live widget on the site shows who's online and has a join button
- **Subreddit:** [r/portalstorm](https://www.reddit.com/r/portalstorm)

## Layout

A single static page built on the [Miniport](https://html5up.net/miniport) template by HTML5 UP
(CCA 3.0). No build step.

```
docs/
├── index.html          # The whole site: intro, games grid, Discord widget, subreddit
├── images/             # Logo, game badges, og-banner.png (social previews)
├── assets/css/         # Miniport styles (main.css is compiled from assets/sass/)
├── assets/js/          # Miniport scripts (jQuery, skel, smooth scrolling)
└── CNAME               # Custom domain for GitHub Pages
social/
└── og-banner.html      # Source for docs/images/og-banner.png
```

## Common edits

- **Add or swap a game:** each tile in the `#games` section of `index.html` is a
  `<section class="box style1">` with a linked badge image. Drop a round badge (transparent PNG,
  about 256×256) in `docs/images/` and copy an existing tile. Keep rows at three tiles each.
- **Discord widget:** the `iframe` in `#communicate` uses the server ID. The widget has to stay
  enabled in Discord's **Server Settings → Widget** or the box shows up empty.

## Social previews

Links shared on Discord, Facebook, X, etc. show `docs/images/og-banner.png` (1200×630) through the
Open Graph / Twitter tags in `index.html`'s `<head>`. The embed accent color comes from the
`theme-color` meta tag.

To change the banner (for example, after changing the games list), edit `social/og-banner.html`,
serve the repo root locally, open the page at exactly 1200×630, screenshot it, and save the result
over `docs/images/og-banner.png`. Discord caches embeds, so an old preview may stick around for a
while after you change it.

## Previewing locally

```bash
python3 -m http.server 8000 --directory docs
```

Then open <http://localhost:8000>.

## Deployment

GitHub Pages serves `docs/` from the `main` branch at `portalstorm.net`. Anything merged to `main`
goes live automatically within a minute or two.
