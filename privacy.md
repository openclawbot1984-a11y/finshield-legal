---
layout: default
title: FinShield Privacy Policy
---

# FinShield Privacy Policy

**Last updated:** 2026-08-24  
**App:** FinShield — Financial Fraud Protection  
**Developer:** Vigilo Labs

---

## Who we are

FinShield is an Android app developed by Vigilo Labs. On your phone it appears as **Second Look** — the app was renamed and the store listing has not yet caught up. It scans the apps installed on your phone for signals associated with financial fraud — things like dangerous permission combinations, sideloaded APKs, and known malicious packages. All threat analysis happens on your device. FinShield has no user accounts.

---

## What data FinShield handles

### 1. Installed app list

When you open FinShield or tap Rescan, the app reads the list of apps installed on your device — including their names, package names, declared permissions, and install sources. This is required for the app to do its job.

**Where it goes:** Your device only. This information is never transmitted to us or any third party.

**How long it is stored:** Scan results are saved locally on your device in a local database (Room). The snapshot is reused when you reopen the app within 30 minutes of the last scan; after that, a fresh scan runs instead. The stored data remains on disk until it is overwritten by the next scan or until you clear app data — it is not automatically deleted at the 30-minute mark.

---

### 2. VirusTotal checks

FinShield can check whether a specific app has been flagged by antivirus engines. These checks use the [VirusTotal](https://www.virustotal.com) service.

**What is sent:** the SHA-256 hash of the app's APK file. The app's package name (e.g.
`com.example.app`) is sent **only when the hash cannot answer the question** — either the hash could
not be computed from the APK, or VirusTotal has no record of that hash and a lookup by package name
is the only remaining way to recognise a repackaged version of known malware. When the hash is enough,
the package name is not sent at all.

**When it is sent:**
- **Automatically**, after a scan completes, for apps that are either sideloaded (not installed from the Play Store) or classified as High risk. This check is cache-aware: if a result for the same app was fetched recently, the network request is skipped.
- **Manually**, when you tap "Check with VirusTotal" on any app card.

**How it is sent:** Requests go to a Vigilo Labs backend proxy hosted on Supabase, which forwards the hash or package name to VirusTotal's API. The proxy exists to protect the VirusTotal API key and to maintain a shared server-side cache. The proxy receives only the hash and/or package name — it does not receive your device identifier, IP address, or any personal information beyond what your network connection inherently carries.

**VirusTotal** is a service operated by Google. Their privacy policy governs how they handle data received: [virustotal.com/gui/privacy-policy](https://www.virustotal.com/gui/privacy-policy).

**VirusTotal results are cached** both on our server (Supabase) and locally on your device (Room) so repeated checks for the same app do not make unnecessary network requests.

---

### 3. Crash reports

FinShield includes Firebase Crashlytics, a crash-reporting SDK operated by Google. If the app crashes, a crash report is automatically sent to Google Firebase. This report includes the stack trace, device model, Android version, and app version. It does not include your name, phone number, installed app list, or any other personal information.

You can find Google's privacy policy at [policies.google.com/privacy](https://policies.google.com/privacy).

---

### 4. Alert wording updates

FinShield uses Firebase Remote Config, a Google service, to update the wording of its fraud-warning
messages without requiring an app update. This lets us improve a confusing or ineffective warning quickly.

**What is sent:** to fetch new wording, the Firebase SDK sends a Firebase installation identifier — a
random ID generated on your device for this app — along with your app version and language, to Google.
This identifier is not linked to your name, phone number, or Google account, and it is reset if you clear
the app's data or uninstall the app.

**What is not sent:** Remote Config never sends your scan results, the list of apps on your phone, or any
warning you were shown. The wording travels *to* your device; nothing about what triggered a warning
travels back.

---

### 5. Guardian phone number

If you choose to set a guardian contact in Settings, that phone number is stored locally on your device in the app's private encrypted storage. It is never transmitted to us or any server.

If you tap the "Alert guardian" action on a FinShield notification, FinShield opens your default SMS app with the alert message pre-filled. You review and tap Send yourself — FinShield never sends SMS silently and does not route messages through any server.

**Clearing it:** Go to Settings inside FinShield and remove the guardian number at any time.

---

### 6. Ignored apps

If you tap "Ignore this app" on a risk card, that app's package name is saved locally on your device (in Room) so FinShield does not flag it again. This list never leaves your device and you can restore ignored apps via Settings → Ignored Apps.

---

### 7. App usage analytics

FinShield records how the app itself is used, so we can see which parts help people and which parts
confuse them. This is our own measurement. It is not shared with any advertising network or analytics
company.

**What is sent:** a small set of events describing your use of the app — when you open it, which setup
step you reached, whether you granted Usage Access, whether you finished setup, when a scan finished and
how many risks it found, when a scan failed, when an alert was raised, when you acted on a warning and
which action you chose, whether a risk was later resolved, and when you turned monitoring on or off.
Counts, durations and scores are grouped into ranges rather than sent exactly.

Each event also carries your phone's make and model (for example, "realme RMX3998"), its Android version
and the FinShield version. These describe the *kind* of phone, not your particular phone, and we use them
for one purpose: to see whether a problem affects one brand or Android version more than others. Android
phones differ a great deal between manufacturers, and without this a fault that only happens on one brand
is invisible to us.

Each event carries a random identifier created when FinShield is installed. It is not linked to your
name, phone number, email address or Google account, it is not an advertising ID, and it is deleted with
the app when you uninstall — a reinstall creates a new identifier that cannot be connected to the old one.

**What is not sent:** the names or package names of the apps on your phone, your messages, your contacts,
your guardian's phone number, or anything from inside your banking apps. No hardware serial number, IMEI,
Android ID or advertising ID is sent, and neither is your Wi-Fi network name. Section 2 describes the only
circumstance in which a package name leaves your device.

**About your internet (IP) address:** FinShield never puts your IP address inside an event, and it is never
stored next to your activity. But like every app that talks to a server, the connection itself carries it.
Our server uses it for one purpose — making sure a single connection cannot flood the service — and deletes
it automatically after a few minutes. It is not used to identify you, to work out where you are, or to link
your events together.

**Where it goes:** a Vigilo Labs server (Supabase). It is not shared with third parties.

**How long it is stored:** 90 days. After that the records are deleted permanently. We do not keep a
summary, a copy, or any other version of them.

**Can it be turned off:** No. This measurement is part of how the app works and there is no setting to
disable it. Uninstalling the app stops it and deletes the identifier described above.

---

## What FinShield does NOT collect

- Your name, email address, or any identity information
- Your location
- Your contacts, call log, or SMS messages
- Any information from inside your banking or UPI apps

---

## Data retention and deletion

All data FinShield stores locally lives on your device only. You can delete all of it at any time by going to Android Settings → Apps → FinShield → Storage → Clear Data.

| Data | Location | Retention |
|---|---|---|
| Scan results | Room (local) | Reused within 30-minute window; remains on disk until next scan or app data clear |
| VirusTotal verdicts | Room (local) + Supabase (server cache) | Local: until app data is cleared. Server: until TTL expires (7–30 days depending on verdict) |
| Ignored apps | Room (local) | Until you remove them or clear app data |
| Guardian phone number | Encrypted local storage | Until you clear it in Settings or clear app data |
| Crash reports | Firebase Crashlytics (Google) | Per Google's Firebase data retention policy |
| Firebase installation ID (alert wording updates) | Firebase (Google) | Until you clear app data or uninstall, which resets it |
| App usage events (Section 7) | Vigilo Labs server (Supabase) | 90 days, then permanently deleted — no aggregate or summary is kept |

---

## Third-party services

FinShield contacts the following external services:

| Service | Purpose | Operator |
|---|---|---|
| Vigilo Labs proxy (Supabase) | Forwards APK hash / package name to VirusTotal; maintains shared result cache; receives the app usage events in Section 7 | Vigilo Labs / Supabase Inc. |
| VirusTotal | Malware intelligence — returns verdict for a given APK hash or package name | Google LLC |
| Firebase Crashlytics | Automatic crash reporting | Google LLC |
| Firebase Remote Config | Updates fraud-warning wording without an app update (see Section 4) | Google LLC |

FinShield contains no advertising network and no third-party analytics SDK. The app usage analytics described in Section 7 are collected by Vigilo Labs directly, on our own server, and are not passed to any advertising or analytics company.

---

## Children's privacy

FinShield is not directed at children under 13. We do not knowingly collect personal information from children.

---

## Changes to this policy

If the app's data handling changes in a material way, this policy will be updated and the "Last updated" date at the top will change. For beta users, changes will be communicated directly.

---

## Contact

Questions about this privacy policy or FinShield's data handling:

**Email:** open.claw.bot.1984@gmail.com  
**Developer:** Vigilo Labs

---

*FinShield performs all threat analysis on your device. It does not have access to your banking credentials, UPI PINs, or transaction history.*
