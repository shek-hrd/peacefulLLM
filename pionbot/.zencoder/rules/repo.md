# PionBot - Crypto Trading Analysis Platform

## Project Overview
A client-side web application for real-time cryptocurrency trading analysis with predictive modeling, technical indicators, and multi-exchange data integration.

## Tech Stack
- **Frontend**: HTML5, CSS3, vanilla JavaScript (no frameworks)
- **Charting**: Canvas API + Chart.js for performance
- **Data Sources**: 
  - Pionex WebSocket API: `wss://ws.pionex.com/wsPub`
  - Binance WebSocket API: `wss://stream.binance.com:9443`
  - CoinGecko REST API (free): https://api.coingecko.com
  - Trading Economics Correlations: https://tradingeconomics.com/crypto/correlations

## Key Features Implemented
1. **Real-time Data Streaming**
   - Multiple WebSocket connections
   - Failover between Pionex and Binance
   - Periodic data fetching from CoinGecko

2. **Technical Indicators**
   - MACD (Moving Average Convergence Divergence)
   - RSI (Relative Strength Index)
   - Stochastic RSI
   - ATR (Average True Range)
   - Bollinger Bands
   - Moving Averages (SMA, EMA)

3. **Prediction Engine**
   - Trend prediction using indicator confluence
   - High/Low turnover prediction with accuracy tracking
   - Automated parameter optimization based on historical accuracy
   - Dashed prediction lines with boundary constraints
   - Historical prediction data persistence

4. **Pattern Recognition**
   - Fractal detection (5-bar patterns)
   - Multi-timeframe pattern matching
   - Pattern similarity scoring using normalized correlation
   - Visual fractal marking on charts

5. **Correlation Analysis**
   - On-demand peer correlation calculation
   - Pearson coefficient for pair analysis
   - Bitcoin-altcoin correlation tracking
   - Pause/stop controls per analysis

6. **Charting System**
   - Multiple timeframes: 1m, 13m, 29m, 229m, 997m
   - Golden ratio scaling for historical view
   - Dark coloring for older candles
   - Hover tooltips with timestamps
   - Arrow markers for predicted highs/lows
   - Prediction accuracy overlay

7. **User Interface**
   - Switchable timeframe views
   - Expandable/collapsible parameter panels per chart
   - Debug console with:
     - Memory usage tracking
     - CPU time per operation
     - Number of active parameters
     - API call statistics
   - Control buttons: Analyze, Pause, Stop, Export

8. **External Service Integration**
   - Links to TradingView charts
   - Links to CoinGecko predictions
   - Comparison with other prediction services
   - Overlay of external predictions in different colors

## Data Structures
```javascript
{
  asset: "BTC",
  pair: "BTCUSDT",
  exchange: "PIONEX",
  timeframes: {
    "1m": { candles: [], indicators: {} },
    "13m": { candles: [], indicators: {} },
    // ...
  },
  prediction: {
    trend: "up|down|neutral",
    confidence: 0-1,
    nextHighPrice: 0,
    nextLowPrice: 0,
    predictionLine: [],
    accuracy: { totalPredictions: 0, correctPredictions: 0 },
    parameters: { /* indicator settings */ }
  },
  patterns: {
    fractals: [],
    similarities: []
  },
  correlations: {
    status: "idle|analyzing|paused|stopped",
    pairs: [{ symbol: "ETH", coefficient: 0.85 }]
  }
}
```

## File Structure
```
pionbot/
├── index.html          # Main application
├── styles.css          # All styling
├── app.js              # Application logic
├── modules/
│   ├── websocket.js    # Data streaming
│   ├── indicators.js   # Technical calculations
│   ├── prediction.js   # Prediction engine
│   ├── patterns.js     # Pattern recognition
│   └── correlation.js  # Correlation analysis
└── utils/
    ├── storage.js      # LocalStorage management
    └── math.js         # Mathematical utilities
```

## API Integration Notes
- **Pionex WebSocket**: Subscribe to ticker, kline, trade streams
- **Binance WebSocket**: Kline streams with multiple intervals
- **CoinGecko**: Historical data via /coins/{id}/market_chart
- **No CORS issues**: All APIs are public and CORS-enabled

## Performance Considerations
1. Limit simultaneous WebSocket connections (max 3)
2. Debounce chart redraws (60fps target)
3. Use Web Workers for heavy calculations
4. LocalStorage for prediction history (capped at 100MB)
5. Memory-efficient candle storage (ring buffer pattern)

## Testing Plan
- [ ] WebSocket connection and data parsing
- [ ] Indicator calculations accuracy (against known values)
- [ ] Prediction accuracy tracking
- [ ] Pattern recognition edge cases
- [ ] UI responsiveness with 6 simultaneous analyses
- [ ] Memory usage under load
- [ ] API failover scenarios

## Future Enhancements
1. Machine learning model training (TensorFlow.js)
2. Frequency analysis using FFT
3. AI-driven parameter optimization
4. Export analysis reports as PDF/CSV
5. Mobile responsive design
6. Dark/Light theme toggle

## External Service Links
- TradingView Charts: https://www.tradingview.com/chart
- CoinGecko Predictions: https://www.coingecko.com/en
- Trading Economics: https://tradingeconomics.com/crypto
- Crypto Fear & Greed: https://alternative.me/crypto/fear-and-greed-index/

## Current Status
- [x] Project structure created
- [x] WebSocket integration implemented (Pionex + Binance)
- [x] Core UI framework built
- [x] Technical indicators implemented (MACD, RSI, ATR, Bollinger Bands, SMA, EMA)
- [x] Prediction engine integrated (trend + high/low prediction)
- [x] Pattern recognition completed (fractal detection)
- [ ] Correlation analysis working (on-demand, pause/stop controls)
- [x] Debug console functional (memory, CPU time, parameter tracking)
- [x] External service links added (TradingView, CoinGecko, etc.)

## Completed Features
1. **Real-time WebSocket Streaming**
   - Pionex: wss://ws.pionex.com/wsPub
   - Binance: wss://stream.binance.com:9443
   - Auto-reconnection on failure
   
2. **Multiple Timeframe Support**
   - 1m, 13m, 29m, 229m, 997m
   - Golden ratio historical view
   - Switchable timeframe buttons
   
3. **Technical Indicators**
   - MACD with signal line
   - RSI (14-period)
   - ATR for volatility
   - Bollinger Bands
   - SMA/EMA moving averages
   
4. **Prediction Engine**
   - Trend prediction (up/down/neutral)
   - High/Low price prediction
   - Dashed prediction lines
   - Confidence scoring
   - Parameter optimization ready
   
5. **Charting System**
   - Canvas-based rendering (high performance)
   - Candlestick display with color coding
   - Older candles darker for visual hierarchy
   - Grid background
   - Hover tooltips with timestamps
   
6. **Pattern Recognition**
   - Fractal detection (5-bar patterns)
   - Up/down fractal markers (▲ ▼)
   - Ready for similarity scoring
   
7. **User Interface**
   - Dark theme with orange accents
   - Collapsible parameter panels
   - Real-time OHLC display
   - Multiple chart support (grid layout)
   - Responsive design
   
8. **Debug & Monitoring**
   - Expandable debug console
   - Memory usage tracking
   - Active chart counter
   - Parameter count display
   - Real-time log display

## How to Use
1. **Open the Application**
   - Start Python HTTP server: `"C:\Users\frhrd\AppData\Local\Programs\Python\Python313\python" -m http.server 8080 --directory "c:\Users\frhrd\Documents\projects\pionbot" -b 127.0.0.1`
   - Or use shorthand: `py -m http.server 8080 --directory "c:\Users\frhrd\Documents\projects\pionbot" -b 127.0.0.1`
   - Open browser: http://localhost:8080
   
## System Information
- **Python Location**: C:\Users\frhrd\AppData\Local\Programs\Python\Python313\python
- **Project Root**: c:\Users\frhrd\Documents\projects\pionbot
- **Development Server**: http://localhost:8080
   
2. **Add a Chart**
   - Enter trading pair (e.g., BTCUSDT, ETHUSDT)
   - Click "Add Chart" button
   - Wait for data to load from CoinGecko
   
3. **Analyze a Chart**
   - Click "Analyze" button on any chart
   - System calculates all indicators
   - Prediction line appears on chart
   - Parameters panel shows current values
   
4. **Switch Timeframes**
   - Click timeframe buttons (1m, 13m, 29m, etc.)
   - Chart data recalculates for that timeframe
   
5. **Monitor Performance**
   - Open Debug Console (📋 button in footer)
   - Check Memory, CPU time, parameter count
   - Monitor WebSocket connections

## Next Priority Features to Implement
1. **Correlation Analysis** (HIGH PRIORITY)
   - On-demand correlation calculation between pairs
   - Pearson coefficient computation
   - Pause/Stop controls per analysis
   - Visual correlation overlay
   - Bitcoin correlation tracking for altcoins

2. **Frequency Analysis** (MEDIUM PRIORITY)
   - FFT implementation for frequency domain analysis
   - Periodicity detection
   - Toggle on/off due to CPU intensity
   - User-initiated start

3. **External Service Integration** (MEDIUM PRIORITY)
   - TradingView data overlay (if API available)
   - CoinGecko predictions comparison
   - Color-coded overlays for different services
   - Prediction accuracy comparison

4. **Enhanced Prediction** (HIGH PRIORITY)
   - Historical prediction accuracy tracking
   - Parameter auto-optimization
   - Boundary constraint enforcement
   - Multi-timeframe consensus prediction

5. **Stochastic RSI** (MEDIUM PRIORITY)
   - Calculate %K and %D lines
   - Overbought/Oversold detection
   - Integration with prediction engine

6. **Pattern Similarity** (MEDIUM PRIORITY)
   - Multi-scale pattern matching
   - Historical pattern comparison
   - Similarity scoring (0-1)
   - Pattern frequency analysis

## Known Limitations & Fixes Needed
1. **CoinGecko Free Tier**
   - Limited historical data (90 days max for some endpoints)
   - Consider implementing hourly refresh from Pionex/Binance REST API
   
2. **Canvas Rendering**
   - Current implementation may lag with 6+ simultaneous charts
   - Solution: Implement requestAnimationFrame instead of 1-second interval
   
3. **Data Persistence**
   - Predictions not saved between sessions
   - Implement LocalStorage for prediction history
   
4. **Correlation Performance**
   - Calculating correlation for many pairs will be slow
   - Solution: Use Web Workers for background calculation

## Testing Checklist
- [ ] Load BTCUSDT chart - verify candlesticks render
- [ ] Load ETHUSDT chart - verify data independence
- [ ] Click Analyze - verify indicators calculate
- [ ] Switch timeframes - verify chart updates
- [ ] Hover over chart - verify tooltip appears
- [ ] Open Debug Console - verify logs display
- [ ] Monitor Memory - verify stays under 200MB with 6 charts
- [ ] Test WebSocket reconnection - stop server, restart, verify reconnect
- [ ] Load 6 different pairs - verify grid layout and performance

## Performance Benchmarks (Target)
- Chart rendering: 60 FPS
- Indicator calculation: <100ms per chart
- Prediction generation: <50ms per chart
- Memory per chart: <20MB
- Total app memory: <200MB with 6 charts
- WebSocket latency: <100ms

## Architecture Notes
```
Data Flow:
WebSocket (Pionex/Binance) → TradingChart.updateFromStream()
                          → addCandle() → Candle Storage
                          
Analysis Flow:
TradingChart.autoAnalyze() → calculateIndicators()
                          → generatePrediction()
                          → recognizePatterns()
                          → render()

Rendering Flow:
render() → drawGrid()
        → drawCandlesticks()
        → drawIndicators()
        → drawPrediction()
        → drawPatterns()
        → drawHoverInfo()
```

## Notes for Continuation
When resuming this project in a new session:
1. Check current implementation status above (Completed Features)
2. Verify WebSocket connections establish (check Debug Console logs)
3. Test with sample pair (BTCUSDT) to ensure data flows
4. Review "Next Priority Features" for remaining work
5. Check Performance Benchmarks - optimize if needed
6. Implement next feature from priority list
7. Run Testing Checklist before committing changes
8. Update this file with new progress