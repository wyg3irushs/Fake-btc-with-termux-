# Fake-btc-with-termux-

The project consists of creating a fake BTC sending generator in the blockchain network that will confirm it in our wallet.

---

## Institutional Liquidity Premium — TradingView Indicator

A professional-grade Pine Script v5 indicator that identifies **institutional liquidity zones** and visually expresses them as **premium/discount institutional levels** on TradingView.

### Features

| Module | Description |
|---|---|
| **Market Structure** | Detects Break of Structure (BOS) and Change of Character (CHoCH) using swing pivots |
| **Premium / Discount Zones** | Highlights premium (overbought), discount (oversold), and equilibrium zones based on the institutional price range |
| **Order Blocks (OB)** | Identifies bullish and bearish order blocks — the last opposing candle before a significant impulse move |
| **Fair Value Gaps (FVG)** | Detects bullish and bearish imbalances (three-candle gaps). Supports auto-mitigation: FVGs are hidden once price fills them |
| **Liquidity Levels** | Finds equal highs (buy-side liquidity) and equal lows (sell-side liquidity) via configurable tolerance matching |
| **Liquidity Sweeps** | Detects when price wicks past a liquidity level and closes back inside — a classic institutional sweep pattern |
| **Info Table** | Real-time dashboard showing current zone, trend, swing high/low, and equilibrium price |
| **Alerts** | Built-in `alertcondition()` for BOS, CHoCH, Premium entry, and Discount entry |

### How to Install

1. Open [TradingView](https://www.tradingview.com/) and go to any chart.
2. Click **Pine Editor** (bottom panel).
3. Click **Open** → **New indicator**.
4. Delete the default code and paste the contents of [`Institutional_Liquidity_Indicator.pine`](./Institutional_Liquidity_Indicator.pine).
5. Click **Save**, then **Add to chart**.

### Configurable Inputs

All parameters are accessible via the indicator settings panel:

- **Structure**: Swing lookback length, toggle BOS/CHoCH labels
- **Premium / Discount**: Range lookback, zone colors
- **Order Blocks**: Max displayed OBs, colors
- **Fair Value Gaps**: Max displayed FVGs, colors, mitigation toggle
- **Liquidity**: Equal high/low tolerance (%), lookback, sweep colors
- **Display**: Toggle labels on/off, label size

### Trading Logic (ICT / Smart Money Concepts)

```
1. Identify the range → Premium (top 25%) vs Discount (bottom 25%)
2. Look for liquidity sweeps (equal highs/lows taken by wicks)
3. After a sweep, look for a BOS or CHoCH confirming reversal
4. Enter at an order block or FVG inside the discount/premium zone
5. Target the opposite liquidity pool
```

### Disclaimer

This indicator is for **educational and analytical purposes only**. It does not constitute financial advice. Always do your own research and manage your risk appropriately.
