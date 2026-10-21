<p align="center">
  <a href="https://pushizo.com">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/pushizo/.github/main/profile/assets/banner-tr-dark.svg">
      <img src="https://raw.githubusercontent.com/pushizo/.github/main/profile/assets/banner-tr-light.svg" alt="Pushizo — kullanıcılarınıza her kanaldan ulaşın" width="100%">
    </picture>
  </a>
</p>

<p align="center">
  <a href="https://github.com/pushizo">English</a> · <b>Türkçe</b>
</p>

<p align="center">
  <a href="https://pushizo.com"><b>pushizo.com</b></a> ·
  <a href="https://app.pushizo.com">Panel</a> ·
  <a href="https://docs.pushizo.com">Dokümantasyon</a> ·
  <a href="https://docs.pushizo.com/docs/api">API referansı</a> ·
  <a href="https://docs.pushizo.com/docs/integrations/mcp">MCP</a> ·
  <a href="https://docs.pushizo.com/docs/sdk">SDK'lar</a>
</p>

**Pushizo**, web ve mobil uygulamalar için çok kanallı müşteri mesajlaşma platformudur: push bildirimleri (Web, iOS,
Android, Huawei), e-posta, SMS ve WhatsApp, in-app mesajlar, bildirim kutusu, canlı sohbet, segmentler, journey
otomasyonları, A/B testleri ve analitik. Bu organizasyonda Pushizo'nun **açık kaynak SDK'ları**, **MCP sunucusu** ve
**API şeması** bulunur.

## Hızlı başlangıç

**1. Tarayıcıda push** — sitenize iki satır ekleyin:

```html
<script src="https://api.pushizo.com/sdk-web/PushizoSDK.js" async></script>
<script>
  window.PushizoDeferred = window.PushizoDeferred || [];
  PushizoDeferred.push((Pushizo) => Pushizo.init({ appId: 'app_…' }));
</script>
```

**2. Sunucudan bildirim gönderin** — herhangi bir dilden REST API ile:

```bash
curl -X POST https://api.pushizo.com/v1/notifications \
  -H "Authorization: Bearer $PUSHIZO_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "app_id": "app_…",
    "target": { "test_devices_only": true },
    "headings": { "tr": "Merhaba", "en": "Hello" },
    "contents": { "tr": "Pushizo çalışıyor", "en": "Pushizo is working" }
  }'
```

**3. Yapay zekâ asistanınızdan yönetin** — Claude, Cursor veya VS Code'a uzak MCP sunucusunu ekleyin:

```bash
claude mcp add --transport http pushizo https://api.pushizo.com/mcp
```

Ayrıntılı adımlar: [Hızlı başlangıç rehberi](https://docs.pushizo.com/docs/getting-started/quickstart).

## İstemci SDK'ları

| Platform | Depo | Kurulum |
|----------|------|---------|
| Web (tarayıcı) | [pushizo-web](https://github.com/pushizo/pushizo-web) | Script etiketi (`/sdk-web/PushizoSDK.js`) · `npm i @pushizo/web` |
| iOS (Swift) | [pushizo-ios](https://github.com/pushizo/pushizo-ios) | Swift Package Manager: `https://github.com/pushizo/pushizo-ios` · CocoaPods `Pushizo` |
| Android (Kotlin) | [pushizo-android](https://github.com/pushizo/pushizo-android) | `com.pushizo:pushizo-android` |
| Flutter | [pushizo-flutter](https://github.com/pushizo/pushizo-flutter) | `flutter pub add pushizo_flutter` |
| React Native / Expo | [pushizo-react-native](https://github.com/pushizo/pushizo-react-native) | `npm i @pushizo/react-native` |
| Capacitor (Ionic) | [pushizo-capacitor](https://github.com/pushizo/pushizo-capacitor) | `npm i @pushizo/capacitor` |
| Cordova | [pushizo-cordova](https://github.com/pushizo/pushizo-cordova) | `cordova plugin add cordova-plugin-pushizo` |
| .NET MAUI | [pushizo-maui](https://github.com/pushizo/pushizo-maui) | `dotnet add package Pushizo.Maui` |
| Unity | [pushizo-unity](https://github.com/pushizo/pushizo-unity) | UPM: `https://github.com/pushizo/pushizo-unity.git#0.1.0` |

## Sunucu SDK'ları

| Dil | Depo | Kurulum |
|-----|------|---------|
| Node.js / TypeScript | [pushizo-node](https://github.com/pushizo/pushizo-node) | `npm i @pushizo/node` |
| PHP / Laravel | [pushizo-php](https://github.com/pushizo/pushizo-php) | `composer require pushizo/pushizo-php` |
| Python | [pushizo-python](https://github.com/pushizo/pushizo-python) | `pip install pushizo` |
| Go | [pushizo-go](https://github.com/pushizo/pushizo-go) | `go get github.com/pushizo/pushizo-go` |
| Java | [pushizo-java](https://github.com/pushizo/pushizo-java) | `com.pushizo:pushizo-java` |
| .NET (C#) | [pushizo-dotnet](https://github.com/pushizo/pushizo-dotnet) | `dotnet add package Pushizo` |
| Ruby | [pushizo-ruby](https://github.com/pushizo/pushizo-ruby) | `gem install pushizo` |

Sunucu SDK'ları aynı [OpenAPI şemasından](https://github.com/pushizo/pushizo-openapi) üretilir; kimlik doğrulama,
yeniden deneme, idempotency, sayfalama ve webhook imza doğrulaması her dilde aynı davranır.

## Araçlar

| | Depo | |
|-|------|-|
| **MCP sunucusu** | [pushizo-mcp](https://github.com/pushizo/pushizo-mcp) | Uzak: `https://api.pushizo.com/mcp` (OAuth 2.1) · Yerel: `npx -y @pushizo/mcp-server` |
| **API şeması** | [pushizo-openapi](https://github.com/pushizo/pushizo-openapi) | OpenAPI 3.1 şeması, Postman koleksiyonu, API kullanım kılavuzu |

> Paket kayıt defterlerine (npm, PyPI, Maven Central, CocoaPods, pub.dev, NuGet, RubyGems, Packagist) yayın aşamalı
> olarak sürüyor; güncel durum her deponun README'sinde ve [SDK sayfasında](https://docs.pushizo.com/docs/sdk) yer alır.

## Destek

- **Dokümantasyon:** [docs.pushizo.com](https://docs.pushizo.com)
- **Hata bildirimi:** ilgili SDK deposunun Issues sekmesi
- **Güvenlik açığı:** [security@pushizo.com](mailto:security@pushizo.com) — ayrıntı: [Güvenlik politikası](https://github.com/pushizo/.github/blob/main/SECURITY.md)
- **Destek ve satış:** [support@pushizo.com](mailto:support@pushizo.com)

<sub>Tüm SDK'lar MIT lisanslıdır. OneSignal'dan geçiş: [geçiş rehberi](https://docs.pushizo.com/docs/migration/onesignal).</sub>
