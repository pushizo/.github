<p align="center">
  <a href="https://pushizo.com">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/pushizo/.github/main/profile/assets/banner-en-dark.svg">
      <img src="https://raw.githubusercontent.com/pushizo/.github/main/profile/assets/banner-en-light.svg" alt="Pushizo — reach your users on every channel" width="100%">
    </picture>
  </a>
</p>

<p align="center">
  <b>English</b> · <a href="https://github.com/pushizo/.github/blob/main/profile/README.tr.md">Türkçe</a>
</p>

<p align="center">
  <a href="https://pushizo.com"><b>pushizo.com</b></a> ·
  <a href="https://app.pushizo.com">Dashboard</a> ·
  <a href="https://docs.pushizo.com">Documentation</a> ·
  <a href="https://docs.pushizo.com/docs/api">API reference</a> ·
  <a href="https://docs.pushizo.com/docs/integrations/mcp">MCP</a> ·
  <a href="https://docs.pushizo.com/docs/sdk">SDKs</a>
</p>

**Pushizo** is a multi-channel customer messaging platform for web and mobile apps: push notifications (web, iOS,
Android, Huawei), email, SMS and WhatsApp, in-app messages, a notification inbox, live chat, segments, journey
automation, A/B testing and analytics. This organization hosts Pushizo's **open-source SDKs**, the **MCP server** and
the **API schema**.

## Quick start

**1. Web push in the browser** — add two tags to your site:

```html
<script src="https://api.pushizo.com/sdk-web/PushizoSDK.js" async></script>
<script>
  window.PushizoDeferred = window.PushizoDeferred || [];
  PushizoDeferred.push((Pushizo) => Pushizo.init({ appId: 'app_…' }));
</script>
```

**2. Send a notification from your server** — with the REST API, from any language:

```bash
curl -X POST https://api.pushizo.com/v1/notifications \
  -H "Authorization: Bearer $PUSHIZO_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "app_id": "app_…",
    "target": { "test_devices_only": true },
    "headings": { "en": "Hello", "tr": "Merhaba" },
    "contents": { "en": "Pushizo is working", "tr": "Pushizo çalışıyor" }
  }'
```

**3. Manage it from your AI assistant** — add the remote MCP server to Claude, Cursor or VS Code:

```bash
claude mcp add --transport http pushizo https://api.pushizo.com/mcp
```

Step by step: [quick start guide](https://docs.pushizo.com/docs/getting-started/quickstart).

## Client SDKs

| Platform | Repository | Install |
|----------|------------|---------|
| Web (browser) | [pushizo-web](https://github.com/pushizo/pushizo-web) | Script tag (`/sdk-web/PushizoSDK.js`) · `npm i @pushizo/web` |
| iOS (Swift) | [pushizo-ios](https://github.com/pushizo/pushizo-ios) | Swift Package Manager: `https://github.com/pushizo/pushizo-ios` · CocoaPods `Pushizo` |
| Android (Kotlin) | [pushizo-android](https://github.com/pushizo/pushizo-android) | `com.pushizo:pushizo-android` |
| Flutter | [pushizo-flutter](https://github.com/pushizo/pushizo-flutter) | `flutter pub add pushizo_flutter` |
| React Native / Expo | [pushizo-react-native](https://github.com/pushizo/pushizo-react-native) | `npm i @pushizo/react-native` |
| Capacitor (Ionic) | [pushizo-capacitor](https://github.com/pushizo/pushizo-capacitor) | `npm i @pushizo/capacitor` |
| Cordova | [pushizo-cordova](https://github.com/pushizo/pushizo-cordova) | `cordova plugin add cordova-plugin-pushizo` |
| .NET MAUI | [pushizo-maui](https://github.com/pushizo/pushizo-maui) | `dotnet add package Pushizo.Maui` |
| Unity | [pushizo-unity](https://github.com/pushizo/pushizo-unity) | UPM: `https://github.com/pushizo/pushizo-unity.git#0.1.0` |

## Server SDKs

| Language | Repository | Install |
|----------|------------|---------|
| Node.js / TypeScript | [pushizo-node](https://github.com/pushizo/pushizo-node) | `npm i @pushizo/node` |
| PHP / Laravel | [pushizo-php](https://github.com/pushizo/pushizo-php) | `composer require pushizo/pushizo-php` |
| Python | [pushizo-python](https://github.com/pushizo/pushizo-python) | `pip install pushizo` |
| Go | [pushizo-go](https://github.com/pushizo/pushizo-go) | `go get github.com/pushizo/pushizo-go` |
| Java | [pushizo-java](https://github.com/pushizo/pushizo-java) | `com.pushizo:pushizo-java` |
| .NET (C#) | [pushizo-dotnet](https://github.com/pushizo/pushizo-dotnet) | `dotnet add package Pushizo` |
| Ruby | [pushizo-ruby](https://github.com/pushizo/pushizo-ruby) | `gem install pushizo` |

The server SDKs are generated from the same [OpenAPI schema](https://github.com/pushizo/pushizo-openapi);
authentication, retries, idempotency, pagination and webhook signature verification behave the same in every language.

## Tools

| | Repository | |
|-|------------|-|
| **MCP server** | [pushizo-mcp](https://github.com/pushizo/pushizo-mcp) | Remote: `https://api.pushizo.com/mcp` (OAuth 2.1) · Local: `npx -y @pushizo/mcp-server` |
| **API schema** | [pushizo-openapi](https://github.com/pushizo/pushizo-openapi) | OpenAPI 3.1 schema, Postman collection, API guide |

> Publishing to package registries (npm, PyPI, Maven Central, CocoaPods, pub.dev, NuGet, RubyGems, Packagist) is
> rolling out; each repository's README shows its current status.

## Support

- **Documentation:** [docs.pushizo.com](https://docs.pushizo.com) (Turkish) · [API reference](https://docs.pushizo.com/docs/api)
- **Bug reports:** the Issues tab of the relevant SDK repository
- **Security:** [security@pushizo.com](mailto:security@pushizo.com) — see the [security policy](https://github.com/pushizo/.github/blob/main/SECURITY.md)
- **Help & sales:** [support@pushizo.com](mailto:support@pushizo.com)

<sub>All SDKs are MIT licensed. Moving from OneSignal? See the [migration guide](https://docs.pushizo.com/docs/migration/onesignal).</sub>
