# Pocket — Privacy Policy

_Last updated: 2026-07-28._

## Plain summary

Pocket is an iOS and macOS companion for AI agent runtimes (Claude Code, Codex, Hermes, OpenClaw) that run on **a Mac you operate**. The apps connect from your device to your own Mac. **We do not run any server that receives your data, and we do not sell, share, or monetise your information.** Everything the apps work with stays on your device or on the Mac you configured.

There is no analytics SDK, no advertising identifier, and no third-party tracker in either app.

## Apps covered

- **Pocket (iOS)** — iPhone/iPad companion. Distributed via TestFlight and the App Store.
- **Pocket (macOS)** — desktop app that pairs your phone with your Mac. Distributed as a notarized direct download.

## The data involved, and where it lives

### Stays on your device

- **Conversation copies.** Messages you exchange with your agents and personas are cached locally so the app opens instantly and works offline. You can erase this at any time: Account → Local data → *Clear local chat history*.
- **Credentials.** Connection tokens and (if you use the SSH feature) an SSH private key are stored in the iOS Keychain, marked `AfterFirstUnlockThisDeviceOnly` — unreachable while the device is locked and **never synced to iCloud**.
- **Preferences.** Appearance, language, notification and behaviour settings.
- **Diagnostics awaiting upload.** See *Diagnostics* below.

### Stays on your Mac

Your agent sessions, personas, memories, files and command history live on your Mac, under your control. Neither app copies them anywhere else.

### Synced via your own iCloud account (optional)

If you sign in with Apple, a small set of preferences (appearance, behaviour defaults) roams between your own devices through **your** iCloud account using Apple's CloudKit. We cannot read it. Conversations and credentials are **not** included.

## Accounts and sign-in

Two mutually exclusive modes:

- **Sign in with Apple** — Apple gives the app an opaque identifier and, if you allow it, your name and email. Used to associate your own devices and (in future) a subscription entitlement. You can revoke it at any time in iOS Settings → Apple ID → Sign-In & Security.
- **Private mode** — no account at all. You pair with your Mac by scanning a QR code; nothing about your identity is stored or transmitted.

There is also a built-in **Demo Mode** (offered on the sign-in screen) that runs entirely on bundled sample data and makes **no network requests whatsoever**.

## Push notifications

Push notifications are **active** in current builds. When you enable them:

- Apple issues a device token to the app, and the app sends that token **only to your own Mac**, so your Mac can address notifications back to your phone.
- Notification content (for example, a persona's reply preview, or a request for your approval) is generated on your Mac and delivered through Apple's APNs infrastructure. Apple processes the delivery; **we never see it**, because we do not operate the sending server — your Mac does.
- You can turn off message previews (Account → Notifications) so notifications show only the sender's name, and you can disable notifications entirely in iOS Settings.

## Diagnostics and problem reports

Two things, both optional and both sent **only to your own Mac** — never to us or any third party:

- **Automatic diagnostics.** With *Diagnostics & usage data* enabled (Account → Diagnostics; on by default), Apple's MetricKit crash and performance reports are uploaded to your Mac so you can inspect them. Payloads contain crash stacks, app version, device model, OS version, and a short excerpt of the app's own error log. **They never contain conversation content.** Turn the switch off to stop all automatic uploads.
- **Report a problem.** When you tap *Report a problem*, your description plus the same technical metadata is sent to your Mac. Nothing is sent unless you tap send.

Because these go to your own machine, we have no copy of them and no way to obtain one.

## What the apps do NOT do

- **No analytics or telemetry.** No event tracking, no install counters, no "improve our product" beacons, no third-party analytics SDK.
- **No advertising.** IDFA/IDFV are never read. No ad networks, no ad identifiers, no profiling.
- **No selling or sharing of personal data**, for any purpose, ever.
- **No developer-operated server.** There is no account database, no message store, no cloud backup on our side — because there is no "our side".

## Network connections

The apps connect to:

1. **Your Mac** — over your local network, over your private network (for example Tailscale), or over an HTTPS address you configured. All agent, persona, media, report and diagnostic traffic goes here.
2. **Apple** — Sign in with Apple (only if you choose it), APNs push delivery, CloudKit preference roaming (your own account), and App Store/TestFlight distribution.
3. **A weather service** — the dashboard shows the day's forecast. The request is made **by your Mac**, not by your phone, and carries no identifier of you.

That is the complete list. In Demo Mode, the app makes no network requests at all.

## Security

- Keychain items use `AfterFirstUnlockThisDeviceOnly`; no iCloud Keychain sync.
- Traffic to your Mac is authenticated with a bearer token established during QR pairing; SSH connections use standard strict host-key verification and key-based authentication.
- The macOS app is notarized by Apple on every release.
- The iOS app runs in the standard iOS sandbox.

## Children's privacy

Neither app is directed at children under 13, and we do not knowingly collect data from them.

## Your rights

Because we hold no data about you on any server we control, there is nothing for us to export, correct, or delete on your behalf. To remove app-held data:

- **iOS**: Account → Local data → *Clear cache* / *Clear local chat history*, or delete the app (iOS purges the Keychain group and app container).
- **macOS**: delete the app from `/Applications`, then remove its Application Support and Preferences folders if you wish.

Data on your Mac remains yours to manage. If you signed in with Apple and want the roamed preferences gone, sign out in the app and delete the app's data in iOS Settings → Apple ID → iCloud → Manage Storage.

## TestFlight beta

If you join via TestFlight, Apple shares anonymised crash reports and the email you used to redeem the invitation with the developer. Apple's [TestFlight terms](https://www.apple.com/legal/internet-services/itunes/testflight/) govern that data.

## Third-party components

Pocket is built on open-source software. Attribution is listed in the app's Credits and in the repository's `CREDITS.md`.

## Changes

Material changes will be published on this page with a new "Last updated" date. Continued use after a change means you accept the updated policy.

## Contact

Questions, privacy requests, or security reports: [m@tsai.cash](mailto:m@tsai.cash).
