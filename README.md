**Simple Ads** is a plugin for Unity to boost ad networks integration. It provides a unified interface to show ads with no need learing SDK docs.

Install ad network plugins, setup app keys and placement IDs. And then just show ads with 1 call. You don't need to learn SDK docs, initialize plugins, load and reload ads, subscribe to events an other boring things. The wrapper hides low-level things and provides unified high-level functions like showing ads. Moreover, it supports waterfalls based on **Remote Config** (optional), so you can ad priority at runtime based on eCPM data.

### Features
* Supported networks: `IronSouce/LevelPlay`, `UnityAds (Advertisement Legacy)`, `AdMob`, `Vungle`, `YandexAds`
* Basic formats: `Interstitial`, `Rewarded` and `Banner`
* AdManager, an unified wrapper for all ad networks
* You can add new networks support by adding new adapters
* Remote waterfalls using `Remote Config` (separate for each ad type)
* Gathering **user consent** with Google User Messaging Platform (AdMob only)

### Setup steps
1. Choose ad networks you want to use. Start from [LevelPlay](https://developers.is.com/ironsource-mobile/unity/unity-plugin/) or [AdMob](https://developers.google.com/admob/unity/quick-start) if you're new with ads.
2. Visit ad provider websites and register, add your app, create ad placements (rewarded, interstitial, banner). Get `App Key` and `Placement IDs`.
3. Download and import official ad packages for Unity (for chosen networks).
4. Add `AdManger` component to your scene and enable ad networks.
5. Adapter components will be added next to `AdManager`. Setup App Key and Placement IDs for each adapter.
6. Check if ad availability with `AdManager.Instance.IsReadyInterstitial`, `IsReadyRewarded` and `IsReadyBanner`.
7. Show ads with `AdManager.Instance.ShowInterstitial`, `ShowRewarded` and `ShowBanner`.
8. If `Managed Stripping Level` and `Minify` are used in `Player Settings`, enable `Custom Proguard File` option to keep java libs (proguard-user.txt included, just in case).
9. Check device logs with `adb logcat` to make sure that everything works fine.

### Recommended setup (simple)
The most simple way to display ads in your app is to use `LevelPlay` with `UnityAds` mediation. Easy to register, setup and get payouts.

### Waterfall setup steps (optional)
1. Import `Remote Config` from `Package Manager`.
2. Enable `Use Remote Waterfall` in `AdManager`.
3. Open `Remote Config` and create string keys: `AdManager.Waterfall.Interstitial`, `AdManager.Waterfall.Rewarded`, `AdManager.Waterfall.Banner`.
4. Set comma-separated values `IronSource,AdMob,UnityAds,Vungle` (change priority if needed), press `Push`.
5. Run and check logs in Console.

### Mediation
1. Choose a primary mediation plugin: [AdMob](https://developers.google.com/admob/unity/mediate) or [LevelPlay](https://developers.is.com/ironsource-mobile/unity/mediation-networks-unity).
2. Enable mediation and choose ad networks (for example, AdColony or AppLovin).
3. Setup apps and placements (find instructions in AdMob or LevelPlay docs).
3. Install adapters for selected ad networks via AdMob or LevelPlay plugins for Unity.

### Verified plugin versions
* IronSouce/LevelPlay 8.0.0
* UnityAds (Advertisement Legacy) 4.4.2
* AdMob 8.7.0
* Vungle ?
* YandexAds 6.0.1

<strong>Links</strong>:
* [IronSource/LevelPlay](https://developers.is.com/ironsource-mobile/unity/unity-plugin/)
* [UnityAds (Advertisement Legacy)](https://unity.com/products/unity-ads)
* [AdMob](https://admob.google.com/)
* [Vungle](https://app.vungle.com/)
* [YandexAds](https://ads.yandex.com/monetization/)

### Support
[Discord](https://discord.gg/4ht2AhW)
[Bugs](https://github.com/hippogamesunity/SimpleAds/issues)
