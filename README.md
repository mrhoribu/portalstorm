# Portalstorm Gaming Community

Source for [portalstorm.net](https://portalstorm.net/), the home page of **Portalstorm Gaming Community**:
a casual group of gamers out to explore, conquer, and just outright have fun together. There's no
formal application process. Everyone is respected and welcomed.

- **Discord:** <https://discord.gg/fVRgG2EMwJ> (permanent invite)
- **Subreddit:** [r/portalstorm](https://www.reddit.com/r/portalstorm)

## Layout

A single static page with one hand-written stylesheet. No build step, no framework, no JavaScript
beyond the footer year.

```
docs/
├── index.html          # The whole site: hero, games grid, Discord, subreddit
├── css/style.css       # All styling; colors and fonts are tokens in :root
├── images/             # Storm logo, favicon, game badges, og-banner.png (social previews)
└── CNAME               # Custom domain for GitHub Pages
social/
└── og-banner.html      # Source for docs/images/og-banner.png
```

## Theme

Dark night-sky background with the storm logo's electric blue fading to lilac. Headings use Space
Grotesk and body text uses Inter (both from Google Fonts). Discord buttons use Discord's own
blurple. Every color is a token in the `:root` block at the top of `docs/css/style.css`, so change
colors there rather than in individual rules.

## Common edits

- **Add or swap a game:** copy one of the `<a class="game">` cards in the `#games` section of
  `index.html`. Drop a round badge (transparent PNG, about 256×256) in `docs/images/` and set the
  name and link text. The grid reflows on its own (3 across on desktop, 2 on tablets, 1 on phones).
- **Discord invite:** the three "Join Discord" buttons (nav, hero, Discord section) all link to
  `https://discord.gg/fVRgG2EMwJ`. If that invite is ever revoked, create a new one set to
  **never expire** and replace all three.

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
