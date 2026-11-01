# MultiChart — TradingView Dashboard

A fully static, mobile-first, open-source multi-chart dashboard hosted on **GitHub Pages**. No API keys, account, backend, build step, or market-data proxy required.

## Features

- Add, duplicate, remove and reorder charts; configurable maximum up to 24 (default 12)
- Global symbol search / apply to all charts, or independent symbol per chart
- Independent timeframe (1m to monthly), chart style and supported built-in TradingView studies
- Mobile vertical scroll (one or two columns), responsive desktop grid, expanded chart modal
- Lazy loading of off-screen charts to reduce mobile resource usage
- Light/dark mode, chart height, localStorage persistence
- Public TradingView embedded widgets (internet connection required)

## Deploy to GitHub Pages

1. Create a **public** GitHub repository, for example `tradingview-multichart`.
2. Upload all project files, including the `.github/workflows/pages.yml` folder and `.nojekyll` file, to the `main` branch. Preserve folder structure.
3. Open **Settings → Pages → Build and deployment**, and choose **GitHub Actions** as the source.
4. Open the **Actions** tab and wait for **Deploy GitHub Pages** to finish. If necessary, run the workflow manually.
5. Visit `https://YOUR-USERNAME.github.io/tradingview-multichart/`.

You can also open `index.html` locally for initial UI testing, but TradingView embeds need internet access and may behave differently on `file://` URLs.

## Important TradingView limitations

- These are **TradingView-hosted proprietary widgets**, not open-source chart engines. The surrounding dashboard is MIT-licensed.
- The public Advanced Chart widget can load supported built-in studies via its `studies` configuration. **Not every study identifier is guaranteed to work**, and custom study parameters are not exposed reliably through the public embed API. In particular, Supertrend may be unavailable; unsupported studies may be ignored by the widget.
- Custom Pine Scripts cannot be installed inside these public embedded widgets.
- The page cannot read the widgets' OHLCV data or calculated indicator values for custom trading recommendations.
- The widget may allow interactive symbol changes internally, but these changes **do not automatically sync** to the other widgets. Use the dashboard's global symbol input for syncing.
- Prices may be delayed depending on exchange, symbol, region and TradingView data entitlements. No real-time guarantee.
- No TradingView login is required for ordinary public embeds, but certain platform features or data entitlements may require TradingView access.
- TradingView's widget library, scripts, chart behavior and licensing may change.

## Project files

- `index.html` — layout and configuration dialogs
- `style.css` — responsive mobile/desktop styling
- `app.js` — chart management, TradingView embed integration and persistence
- `manifest.webmanifest` and `assets/icon.svg` — installable web app metadata
- `.github/workflows/pages.yml` — automatic GitHub Pages deployment

## License

MIT license for original dashboard code. TradingView trademarks, widget code, and market data are excluded and governed by their respective terms.
