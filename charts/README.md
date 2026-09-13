# Chart Library

Chart images for the CloudAI trading-signals video pipeline. Each file is a
TradingView screenshot (from the user's own subscription/layout), cropped
and hosted here so the Creatomate Render API can reference it by a stable
public URL — no Creatomate upload step required, same approach as
`/broll` in this repo.

## Structure

- `charts/current/` — the *latest* chart for each symbol+timeframe pair,
  always at the same filename/URL. This is what the render pipeline's
  `modifications` payload should point to — the URL never changes, only
  the file content does, each time a new screenshot comes in.
- `charts/archive/` — a dated copy of every chart ever used, kept for the
  rights/production log and so a specific video's exact chart can always
  be found again after the fact.

## Naming convention

`chart_<symbol>-<timeframe>.png` for `current/`, e.g.:
- `chart_btcusd-4h.png`
- `chart_ethusd-4h.png`
- `chart_btcusd-1d.png`

`chart_<symbol>-<timeframe>_<YYYY-MM-DD>.png` for `archive/`, e.g.:
- `chart_btcusd-4h_2026-09-13.png`

## Stable URLs (for the generator script)

Base: `https://raw.githubusercontent.com/CloudAITrading/crypto-broll-library/main/charts/current/`

Example: `https://raw.githubusercontent.com/CloudAITrading/crypto-broll-library/main/charts/current/chart_btcusd-4h.png`
