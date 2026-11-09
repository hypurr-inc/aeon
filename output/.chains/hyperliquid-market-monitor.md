## Hyperliquid watch: no new alerts

**Verdict:** `HL_WATCH_REPEAT`. Several markets are still past a threshold, but the previous run already reported every one of them, so I did not send a notification.

**Log line:**
```
HL_WATCH coins=BTC,ETH,SOL,HYPE,xyz:XYZ100 hits=BTC:move-,BTC:fund+,ETH:move-,ETH:fund+,SOL:move-,SOL:fund-,HYPE:move-,HYPE:fund-,xyz:XYZ100:move+,xyz:XYZ100:fund+ new=0 unknown=0 unreadable=0 move>=0.5 funding>=0.0001/h
```

**Notification sent:** no.

**Watch settings used:** coins `BTC,ETH,SOL,HYPE,xyz:XYZ100`, `move=0.5` (absolute 24h move in %), `funding=0.0001` (absolute hourly funding in %). The `xyz:XYZ100` market is a HIP-3 perp and resolved with no unknown or unreadable markets.

## Summary

- **Ran:** `node skills/hyperliquid-market-monitor/x.mjs BTC,ETH,SOL,HYPE,xyz:XYZ100 move=0.5 funding=0.0001`. I passed the watch string as arguments rather than relying on `SKILL_VAR`.
- **Files created or modified:** none. This is a read-only skill, and I did not write to `memory/logs/`.
- **Follow-up:** none. The next run will alert again only for thresholds that newly cross or drop back under and re-cross.
