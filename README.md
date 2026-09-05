# Vertex Trader — iPhone PWA

A static GitHub Pages paper-trading dashboard using Bybit public market data.

## Upload to GitHub Pages

1. Create/open a GitHub repository.
2. Upload **all files in this folder** to the repository root.
3. In GitHub: **Settings → Pages → Deploy from branch → main → /(root)**.
4. Open the resulting HTTPS address on iPhone Safari.
5. Safari Share → **Add to Home Screen**.

No API key is required because this version uses public Bybit market data only. It does NOT place real orders.

## Strategy

- Timeframe: 45 minutes
- Chandelier Exit: ATR length 4, multiplier 2
- ZLSMA: 38
- MACD: 5 / 35 / 5
- ATR TP: 4×
- ATR SL: 2×
- Paper starting balance: $1,000
- Default leverage: 5×

### 45-minute candle construction

Bybit's native kline intervals currently do not include 45 minutes. The app therefore loads 15-minute klines and aggregates three consecutive 15-minute candles into one 45-minute candle. Live updates are received from Bybit's 15-minute WebSocket stream.

Strategy entries/exits are evaluated only on confirmed/closed 45-minute candles. Current ticker price is used for paper P&L and TP/SL monitoring.

## Important limitations

- Paper trading only.
- Browser localStorage stores the paper account locally on the device/browser.
- This is not a financial execution engine and does not guarantee TradingView/Pine numerical identity in every edge case.
- Background push notifications after the PWA is fully suspended/closed require a push backend. This version provides browser notifications when supported/permissioned.
- For real Bybit order execution, a secure backend is required; never put private API secrets into a GitHub Pages client.

## Official Bybit documentation

https://bybit-exchange.github.io/docs/v5/ws/connect
https://bybit-exchange.github.io/docs/v5/websocket/public/kline
https://bybit-exchange.github.io/docs/v5/market/kline
