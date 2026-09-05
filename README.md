# Vertex Trader PWA v3

Upload the contents of this folder to the root of a GitHub Pages repository.

Features:
- BTC/USDT.P, ETH/USDT.P, SOL/USDT.P, XRP/USDT.P, DOGE/USDT.P
- Live Bybit linear public WebSocket
- REST fallback for prices
- 45m candles built from 3 x 15m candles
- Chandelier Exit ATR 4 x 2
- ZLSMA 38
- MACD 5/35/5
- ATR TP 4x / SL 2x
- TradingView-style candle chart
- ZLSMA + Chandelier line
- BUY/SELL markers
- 45m countdown
- Paper trading $1,000
- Local trade history
- Browser alerts

Important: This is paper trading only. Do not place private Bybit API keys in GitHub Pages. Real execution requires a secure backend.

Bybit's current public kline intervals include 15m but not 45m, and `confirm=true` indicates a closed candle. The app therefore aggregates three 15m candles and evaluates the strategy on closed 45m candles.
