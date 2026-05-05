# Gitwellarze
Helius WebSocket
      │
      ▼
 PoolMonitor            ← logsSubscribe filtered to Raydium AMM v4
      │ NewPoolEvent
      ▼
 Safety Filters          ← mint authority, freeze authority, RugCheck score
      │ (pass)
      ▼
 Executor.buy()          ← Jupiter /quote → /swap → Jito bundle
      │
      ▼
 PositionManager         ← DexScreener price polling (every N seconds)
      │ TP or SL hit
      ▼
 Executor.sell()         ← same Jupiter/Jito pipeline