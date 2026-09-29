# Privacy Policy — Naam Jaap & Mantra Counter

**Last updated:** September 29, 2026  
**Developer:** nik.dev  
**Contact:** nik.dev.acc@gmail.com

---

## 1. Overview

Naam Jaap & Mantra Counter ("the App") is a spiritual mantra and jaap counting application for Android. We are committed to protecting your privacy. This policy explains what information is collected, how it is used, and your rights regarding that information.

**In short:**
- **No account required for core use:** You do not need to sign in or register to use the App's counting features. An optional Google Sign-In is only used if you choose to turn on Google Drive backup (see Section 4.3).
- **Data remains local by default:** All your counting logs and app configuration remain exclusively on your device unless you explicitly choose to back them up to Google Drive. We do not operate any server that stores your personal data.
- **Anonymous analytics:** We collect only anonymous usage analytics to improve the App. Aside from the optional Google Drive backup feature, no personally identifiable information is collected.
- **Optional device features stay optional:** Features that touch your phone's settings (Auto-count, Do Not Disturb, battery-optimization exemption) are off by default, ask for your explicit approval, and never send any data anywhere. See Section 3.

---

## 2. Information We Collect

### 2.1 Information Stored Locally on Your Device

All counting data is stored exclusively on your device using a local SQLite database. This includes:

- Counter names and settings (such as cycle size, theme color, sound and haptic preferences)
- Daily counting logs (such as date and count totals per day)
- Goal settings (such as target count or cycles)
- Optional daily reminder times you choose to set, used only to schedule local notifications on your own device (see Section 3 for the permissions this uses)
- Your app preferences (such as theme, language, Keep Screen On, Fullscreen Mode, and Do Not Disturb)
- Optional pictures and sounds you choose yourself: a photo from your gallery used as a background or wallpaper, and an audio file used as a custom tap sound. See Section 3 for how these are selected. They are used only on your device, are never uploaded, and are not included in backups.

This data **never leaves your device** unless you explicitly choose to export or back it up using the in-app features described in Section 4. We have no access to this data.

### 2.2 Anonymous Analytics & Advertising Identifiers

The App uses **Firebase Analytics** and **Google AdMob** (both provided by Google LLC) to collect anonymous usage and device data. This helps us serve advertisements, measure ad performance, and analyze app interactions to improve the user experience.

**What is collected automatically:**

| Data | Purpose |
|---|---|
| Device model, OS version, and Device or Other IDs (e.g., Android Advertising ID) | Support ad delivery, attribution, and analytics |
| Country and language | Support localisation and geo-targeted ads |
| App version and build number | Track adoption of updates |
| Session duration and Custom events (interactions) | Analyze feature usage and engagement |
| First open and app remove events | Track install and uninstall trends |
| App performance metrics and diagnostics | Monitor app stability and load speeds |

Custom events record which features are used (for example, the wallpaper counter, backup, or the goal planner) and counting milestones (completing a cycle or reaching a goal). Milestone events include the cycle size, the number of cycles completed, or the goal value, together with a random internal counter ID that does not identify you. They never include your counter names or mantra text.

**What is NOT collected:**

- **No personal identity:** No name, email, phone number, physical address, or account information.
- **No religious content:** We do not collect the actual mantra or prayer text you are counting.
- **No precise location:** We do not access or collect your device's precise GPS coordinates. (Note: Google AdMob resolves your IP address to an **approximate location** to serve localized ads, but we do not track or store this location).
- **No camera, microphone, or sensor data:** The App never records audio or video. It only plays back a sound file if you choose one, and uses vibration for haptic feedback.
- **No access to your files, photos, or contacts:** The App cannot browse your photos, files, contacts, or calendar. It only receives a single photo or audio file when you pick one yourself using Android's own picker (see Section 3).
- **No notification content:** The App never reads, stores, or sends the notifications shown by other apps, even when the optional Do Not Disturb feature is on.

All analytics and ad-related data is transmitted securely to Google's servers over HTTPS and is governed by Google's Privacy Policy.

---

## 3. Device Permissions

The App requests the following Android permissions:

| Permission | Why it is needed |
|---|---|
| `INTERNET` | Required to send anonymous analytics data to Firebase, to load and measure ads, to check Google Play for app updates, and — only if you turn it on — to back up to Google Drive |
| `VIBRATE` | Required for haptic feedback when counting (vibration on tap/cycle) |
| `POST_NOTIFICATIONS` | Required to show the optional daily reminder notification, only if you choose to enable it, and the status notification shown while Auto-count mode is running. You are asked to grant this permission at the moment you turn a reminder on, not at install or app launch. |
| `RECEIVE_BOOT_COMPLETED` | Lets your enabled reminders continue to work after you restart your device. Used only to re-register the notification schedule already stored on your device — no data is sent anywhere. |
| `WAKE_LOCK` (Android only) | Keeps the device awake only while you have actively started the optional "Auto-count" mode, so it can keep incrementing your count at your chosen interval even with the screen locked. Released automatically the moment you pause or stop the session. |
| `FOREGROUND_SERVICE` (Android only) | Required by Android to run the foreground service that powers Auto-count mode. Only active while a session you started is running. |
| `FOREGROUND_SERVICE_SPECIAL_USE` (Android only) | Lets Auto-count mode keep running in the background or with the screen locked, only while you have explicitly started it. See "Auto-count mode" below for details. |
| `REQUEST_IGNORE_BATTERY_OPTIMIZATIONS` (Android only) | Lets the App show Android's own system dialog asking whether Auto-count may be exempt from battery optimization, so a battery saver does not pause a running session while the screen is locked. It is only shown when you use Auto-count, nothing changes unless you approve it in that dialog, and you can undo it any time in Android's battery settings. |
| `ACCESS_NOTIFICATION_POLICY` (Android only) | Used only by the optional **Do Not Disturb** setting (see below). Off by default. It is a special access that Android asks you to grant separately in system settings. |

The following permissions are added automatically by the Google libraries the App includes (Firebase Analytics, Google AdMob, Google Sign-In). The App itself does not use them for anything else:

| Permission | Why it is present |
|---|---|
| `ACCESS_NETWORK_STATE` | Lets Google's ads and analytics libraries check whether you are online before sending data |
| `com.google.android.gms.permission.AD_ID`, `ACCESS_ADSERVICES_AD_ID`, `ACCESS_ADSERVICES_ATTRIBUTION`, `ACCESS_ADSERVICES_TOPICS` | Let Google AdMob and Firebase read the Android Advertising ID and use Android's Privacy Sandbox ad services for ad delivery and measurement. If you reset or delete your advertising ID in Android settings, or opt out of personalised ads, this is respected. |
| `com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE` | Lets Firebase Analytics learn, in aggregate, which source (for example, the Play Store listing) an install came from |
| `USE_BIOMETRIC`, `USE_FINGERPRINT` | Declared by the Google Sign-In library used for the optional Google Drive backup. The App never asks for, reads, or stores fingerprint or face data. |

The App does **not** request access to: location, camera, microphone, contacts, phone, calendar, SMS, or storage/media permissions. Photos and audio files reach the App only when you choose them yourself through Android's own picker.

Reminder scheduling happens entirely on your device. No reminder times, content, or notification activity is sent to us, Google, or any other third party.

**Auto-count mode (optional, Android only):** If you start Auto-count mode, the App automatically increments your count at an interval you choose, without you needing to tap anything, including while the screen is locked. A persistent notification is shown the entire time a session is running, showing your live count with Pause and Stop controls, so you always know it is active and can stop it instantly. If you don't set a stop condition yourself, the session still can't run forever unattended: it automatically stops after 200,000 counts or 12 hours, whichever comes first. This feature does not collect, transmit, or share any data — your count is written to the same local database as a manual tap, and nothing about your Auto-count sessions ever leaves your device.

**Do Not Disturb (optional, Android only, off by default):** If you turn this on in Settings, Android asks you to grant "Do Not Disturb access" to the App in system settings. While the option is on and the App is open, the App switches your phone to Android's "Priority only" Do Not Disturb mode so other apps' notifications are silenced, and switches it back as soon as you leave the App. Your own Do Not Disturb rules apply, and if you already had Do Not Disturb on, the App leaves it alone. The App only changes the on/off state — it cannot see which apps send notifications or what they say, and no information about this feature is collected or sent anywhere. You can turn it off in the App at any time, or revoke the access in Android settings. Note that while it is on, the App's own reminder notifications are silenced too, unless your phone's Priority rules allow them.

**Keep Screen On and Fullscreen Mode (optional):** These settings only change how the App's own screen behaves (staying awake while the App is open, and hiding the status bar). They need no extra permission and collect nothing.

**Volume-button counting (optional):** If you choose volume-button counting for a counter, the App listens for volume up and down presses only while that mode is active in the App, and uses them only to change your count. No permission is needed and nothing is recorded or sent.

**Photos and audio you choose (optional):** To set a background or wallpaper picture, or a custom tap sound, the App opens Android's own photo or file picker. Only the single item you pick is shared with the App. A picked sound is copied into the App's private storage; for pictures, the App keeps a reference to the picture and your position and zoom settings. None of this is uploaded, and none of it is included in backups or exports.

---

## 4. Backup and Export Features

### 4.1 Local Backup

The App includes an optional backup feature that saves your counting data to a file on your device. Backup files are:

- Encrypted using AES-256 encryption before being saved, to prevent the exported file from being tampered with or edited outside the App — this does not make the file safe to share, as it still contains your personal counting data
- Saved to a location you choose via the Android file picker
- Never uploaded to any server by the App

### 4.2 Data Export (PDF / Excel)

The App can export your counting history as a PDF or Excel file. Exported files are:

- Saved to a location you choose via the Android file picker
- Not uploaded to any server

Both features are entirely optional and user-initiated. You are in full control of where these files are saved and who you share them with.

### 4.3 Google Drive Backup (Optional)

If you choose to enable **Backup to Google Drive** in Settings, the App uses Google Sign-In to authenticate you and uploads an encrypted copy of your counting data to your own Google Drive account. This feature is off by default and entirely optional.

**What we access:**
- Your Google account email address and basic profile information, used only to complete sign-in. The App does not access your Google contacts, photos, or any other files in your Drive.

**What is uploaded:**
- The same AES-256 encrypted backup file described in Section 4.1, uploaded to a hidden "app data" folder in your Google Drive (the `drive.appdata` scope). This folder does not appear in your regular Google Drive, cannot be browsed or accessed by any other app, and is not accessible to us — it exists solely within your own Google account.

**What happens to it:**
- We have no server-side access to this file; it is stored entirely within your Google account, subject to Google's own privacy and security practices ([https://policies.google.com/privacy](https://policies.google.com/privacy)).
- Each new backup overwrites the previous one — no history of past backups is kept.

**Your control:**
- Restore at any time via **Settings → Restore from Google Drive**.
- Revoke the App's access to your Google account at any time from **myaccount.google.com → Security → Third-party apps with account access**.

**Limited Use disclosure:** Naam Jaap & Mantra Counter's use and transfer of information received from Google APIs to any other app will adhere to the [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy), including the Limited Use requirements.

### 4.4 Android Automatic Backup

The App turns off Android's automatic app backup, so your counting data is not saved to Google's automatic device backups. To move your data to a new phone, use the App's own backup and restore (Sections 4.1 and 4.3).

---

## 5. Third-Party Services

The App uses the following third-party services:

### Firebase Analytics (Google LLC)

- **Purpose:** Anonymous usage analytics
- **Data sent:** Anonymous device and usage events as described in Section 2.2.
- **Privacy policy:** [https://policies.google.com/privacy](https://policies.google.com/privacy)

### Google AdMob (Google LLC)

- **Purpose:** Display advertisements
- **Data sent:** Device identifiers and usage data to serve relevant ads. You can opt out of personalized ads through your device settings under Google → Ads.
- **Privacy policy:** [https://policies.google.com/privacy](https://policies.google.com/privacy)

### Google Sign-In & Google Drive API (Google LLC)

- **Purpose:** Optional account sign-in and encrypted backup storage, used only if you enable Google Drive backup (Section 4.3)
- **Data sent:** Your Google account email/basic profile (for sign-in) and your encrypted backup file (uploaded to your own Drive's hidden app data folder)
- **Privacy policy:** [https://policies.google.com/privacy](https://policies.google.com/privacy)

### Google Play (Google LLC)

- **Purpose:** Checking whether a newer version of the App is available (Google Play In-App Updates), showing a "new version available" notice, and opening the App's Play Store page when you choose to rate it or update
- **Data sent:** These requests go directly between your device and Google Play. The App sends no personal data of its own, and Google Play handles them under its own terms.
- **Privacy policy:** [https://policies.google.com/privacy](https://policies.google.com/privacy)

### GDPR and UK Privacy Compliance (EU User Consent)
For users residing in the European Economic Area (EEA), the European Union (EU), and the United Kingdom (UK):
- The App implements Google's User Messaging Platform (UMP) to obtain explicit consent before initializing Google Mobile Ads (AdMob) or processing analytics.
- You can revoke or change your consent choices at any time from the settings within the App.

### India's Digital Personal Data Protection Act, 2023 (DPDP Act)
For users residing in India, this policy is intended to serve as the notice required under the DPDP Act:
- As a Data Principal, you have the right to access, correct, and request erasure of any personal data processed about you, and to withdraw consent at any time (see Section 6 for how to do so, since the App holds no server-side account data to begin with).
- The only personal data processed is the anonymous device/usage data described in Section 2.2, processed by our Data Processors (Google LLC, via Firebase Analytics and Google AdMob) for the purposes stated there.
- Grievances or DPDP-related requests can be raised via the contact details in Section 11.

### CCPA/CPRA Privacy Compliance (California Residents)
Under the California Consumer Privacy Act (CCPA) / California Privacy Rights Act (CPRA), California residents have the right to opt-out of the "sale" or "sharing" of their personal information (which includes device identifiers for personalized advertising). You can manage your ad personalization settings through your device's Google settings under **Google → Ads**.

---

## 6. Data Retention and Deletion

**Local data:** Stored on your device until you delete the App or clear its data. You can also delete all data from within the App via **Settings → Danger Zone → Clear All Data**.

**Analytics data:** Retained by Google for up to 14 months per Firebase Analytics' standard retention policy, after which it is automatically deleted.

**Google Drive backup data:** If you enabled Google Drive backup, your encrypted backup file is retained in your own Google Drive until you delete it or revoke the App's access (see Section 4.3). We do not store this data ourselves and cannot delete it on your behalf.

**Account and Data Deletion Requests:** We do not operate any servers that store your personal data — all data either stays on your device or, for the optional Drive backup, in your own Google account. There is no account with us to delete. You are in full control of your data and can delete it locally at any time by uninstalling the App or clearing the App's storage in your Android system settings, and can remove your Drive backup as described in Section 4.3.

---

## 7. Children's Privacy

The App is suitable for all ages and does not knowingly collect any personal information from children under the age of 13 (or the applicable age in your region). Since the App does not collect personal information from any user, it is safe for children to use.

---

## 8. Your Rights

Since the App does not collect personally identifiable information, most data subject rights (access, correction, deletion of personal data) apply to your local device data, which you control directly.

---

## 9. Data Security

- All counting data is stored locally on your device and protected by Android's application sandboxing
- Backup files are encrypted with AES-256 before being saved
- Analytics data is transmitted to Firebase over HTTPS (TLS encryption)
- We do not operate any servers that store your data

---

## 10. Changes to This Policy

We may update this privacy policy from time to time. When we do, we will update the "Last updated" date at the top of this page. For significant changes, we will notify users via an in-app notice or a Play Store update description.

Continued use of the App after changes are posted constitutes acceptance of the updated policy.

---

## 11. Contact Us

If you have any questions or concerns about this privacy policy, please contact us:

**Email:** [nik.dev.acc@gmail.com]  
**Developer:** nik.dev  

---

*This privacy policy was last reviewed on September 29, 2026.*
