# Stickman Ping Pong 3D — remote config

`remote-config.json` is fetched by the game at boot (jsDelivr CDN first, raw GitHub as fallback) and cached on the device.
Only numbers, booleans and strings; nested objects become dotted keys (`ads.shopAdDailyCap`). Empty strings mean "keep the bundled value".
Bump `version` on every change. Published from the game repo with `tools/remote-config-push.sh` (also purges the jsDelivr cache).

| Key | Meaning |
|---|---|
| `ads.rewardedEnabled` / `interstitialEnabled` / `bannerEnabled` | Kill switches per format |
| `ads.interstitialAfterMatches`, `ads.interstitialEveryMatches`, `ads.interstitialMinIntervalSeconds`, `ads.interstitialSkipFirstMatchOfDay` | Interstitial policy |
| `ads.shopAdDailyCap` | Rewarded "watch ad for coins" per day |
| `ads.android.*`, `ads.ios.*` | Ad unit ids (banner / interstitial / rewarded); test ids still win in debug builds |
| `worldrally.freeAttempts`, `worldrally.maxExtraAttemptsPerDay` | World Rally daily attempts |
