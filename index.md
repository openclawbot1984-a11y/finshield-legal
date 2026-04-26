---
layout: default
title: FinShield Privacy Policy
---

# FinShield Privacy Policy

**Last updated:** April 2026
**App:** FinShield — Financial Fraud Protection
**Developer:** Vigilo Labs

---

## Who we are

FinShield is an Android app developed by Vigilo Labs. It scans the apps installed on your phone for signals associated with financial fraud — things like dangerous permission combinations, sideloaded APKs, and known malicious packages. All scanning happens on your device. FinShield has no user accounts and no backend servers.

---

## What data FinShield handles

### 1. Installed app list

When you open FinShield or tap Rescan, the app reads the list of apps installed on your device — including their names, package names, declared permissions, and install sources. This is required for the app to do its job.

**Where it goes:** Your device only. This information is never transmitted to us or any third party.

**How long it is stored:** Scan results are saved locally on your device in a local database (Room). The snapshot is reused when you reopen the app within 30 minutes of the last scan; after that, a fresh scan runs instead. The stored data remains on disk until it is overwritten by the next scan or until you clear app data — it is not automatically deleted at the 30-minute mark.

---

### 2. VirusTotal checks

FinShield can check whether a specific app has been flagged by antivirus engines. These checks use the [VirusTotal](https://www.virustotal.com) service.

**What is sent:** FinShield sends only the SHA-256 hash of the app's APK file, or the app's package name (e.g. `com.example.app`) if the APK hash cannot be computed, in the request.

**When it is sent:**
- **Automatically**, after a scan completes, for apps that are either sideloaded (not installed from the Play Store) or classified as High risk. This check is cache-aware: if a result for the same app was fetched recently, the network request is skipped.
- **Manually**, when you tap "Check with VirusTotal" on any app card.

**Where it goes:** Directly to VirusTotal's API (`virustotal.com`). VirusTotal is a service operated by Google. Their privacy policy governs how they handle data received: [virustotal.com/gui/privacy-policy](https://www.virustotal.com/gui/privacy-policy).

**VirusTotal results are cached locally** on your device (in Room) so repeated checks for the same app do not make unnecessary network requests.

**We do not receive or store VirusTotal data on our servers.** The request goes from your phone directly to VirusTotal.

---

### 3. Guardian phone number

If you choose to set a guardian contact in Settings, that phone number is stored locally on your device in the app's private storage (SharedPreferences). It is never transmitted to us or any server.

The number is used only to send an SMS alert if you tap the "Alert guardian" action in a FinShield notification. The SMS is sent by your device's messaging system directly to that contact — FinShield does not route it through any server.

**Clearing it:** Go to Settings inside FinShield and remove the guardian number at any time.

---

### 4. Ignored apps

If you tap "Ignore this app" on a risk card, that app's package name is saved locally on your device (in Room) so FinShield does not flag it again. This list never leaves your device and you can restore ignored apps via Settings → Ignored Apps.

---

## What FinShield does NOT collect

- Your name, email address, or any identity information
- Your location
- Your contacts, call log, or SMS messages
- Any information from inside your banking or UPI apps
- Crash reports or analytics (no third-party analytics SDK is included)

---

## Data retention and deletion

All data FinShield stores lives on your device only. You can delete all of it at any time by going to Android Settings → Apps → FinShield → Storage → Clear Data.

| Data | Location | Retention |
|---|---|---|
| Scan results | Room (local) | Reused within 30-minute window; remains on disk until next scan or app data clear |
| VirusTotal verdicts | Room (local) | Until app data is cleared |
| Ignored apps | Room (local) | Until you remove them or clear app data |
| Guardian phone number | SharedPreferences (local) | Until you clear it in Settings or clear app data |

---

## Third-party services

The only external service FinShield contacts is **VirusTotal** (see Section 2 above). No other third-party SDK, analytics service, or advertising network is included in FinShield.

---

## Children's privacy

FinShield is not directed at children under 13. We do not knowingly collect personal information from children.

---

## Changes to this policy

If the app's data handling changes in a material way — for example, if a backend server is added — this policy will be updated and the "Last updated" date at the top will change. For beta users, changes will be communicated directly.

---

## Contact

Questions about this privacy policy or FinShield's data handling:

**Email:** open.claw.bot.1984@gmail.com
**Developer:** Vigilo Labs

---

*FinShield performs all threat analysis on your device. It does not have access to your banking credentials, UPI PINs, or transaction history.*
