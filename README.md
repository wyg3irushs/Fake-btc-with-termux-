# Fake-btc-with-termux-

The project consists of creating a fake BTC sending generator in the blockchain network that will confirm it in our wallet.

---

## Institutional Liquidity Premium v2 — TradingView Indicator

A clean, signal-based Pine Script v5 indicator that generates **BUY / SELL signals** with **visual trade setups** drawn live on the chart — entry price, stop loss, and 5 take-profit levels with automatic checkmarks.

### What You See on the Chart

When a signal fires, the indicator draws a **complete live trade setup**:

```
  ✅ TP5  72,450.00    ← auto-checked when hit
  ✅ TP4  71,800.00    ← auto-checked when hit
  ◻ TP3  71,200.00
  ◻ TP2  70,800.00
  ✅ TP1  70,500.00    ← auto-checked when hit
  ▸ ENTRY 70,000.00    ← white solid line
  ┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈
  ✖ SL   69,300.00    ← red dashed line
```

- **Green rectangle** = buy setup zone (entry → TP1)
- **Red rectangle** = sell setup zone
- Each **TP level** shows `◻` when pending, `✅` when price reaches it
- **SL** turns `❌ SL HIT` if stopped out
- **🏆 FULL TP** label when all 5 levels are hit

### Features

| Module | Description |
|---|---|
| **BUY / SELL Signals** | Based on BOS (Break of Structure) + EMA trend + RSI filter + volume spike confluence |
| **Entry Price Label** | Exact entry price displayed next to the setup |
| **Stop Loss** | ATR-based SL drawn as red dashed line with price label |
| **5 TP Levels** | Configurable R:R ratios (default 1R, 1.5R, 2R, 3R, 4R), auto-checkmarked |
| **Live Setup Box** | Green/red rectangle drawn from entry to TP1 — extends as trade progresses |
| **Premium / Discount** | Subtle background shading shows institutional zones |
| **Dashboard** | Trend, zone, RSI, and active setup count |
| **Alerts** | `alertcondition()` for BUY and SELL signals |

### How to Install

1. Open [TradingView](https://www.tradingview.com/) and go to any chart.
2. Click **Pine Editor** (bottom panel).
3. Click **Open** → **New indicator**.
4. Delete the default code and paste the contents of [`Institutional_Liquidity_Indicator.pine`](./Institutional_Liquidity_Indicator.pine).
5. Click **Save**, then **Add to chart**.

### Configurable Inputs

| Group | Settings |
|---|---|
| **Signal Engine** | Swing lookback, ATR length & multiplier, TP1–TP5 R:R ratios |
| **Confluence** | EMA filter (on/off + length), RSI filter (OB/OS levels), Volume spike multiplier |
| **Design** | All colors customizable (buy, sell, SL, TP, entry, checkmarks, text) |
| **Institutional Zones** | Premium/Discount background toggle, range lookback |

### Signal Logic

```
BUY  = Bullish BOS + Price > EMA + RSI < 70 + Volume Spike
SELL = Bearish BOS + Price < EMA + RSI > 30 + Volume Spike

Entry  = Close price at signal bar
SL     = Entry ∓ ATR × Multiplier
TP1-5  = Entry ± Risk × R:R ratio (1R, 1.5R, 2R, 3R, 4R)
```

### Disclaimer

This indicator is for **educational and analytical purposes only**. It does not constitute financial advice. Always do your own research and manage your risk appropriately.
