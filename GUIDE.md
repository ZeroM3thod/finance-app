# 📱 iOS Finance App — Build Guide (Free, No Mac, No Xcode)
### Uses GitHub free Mac servers → Sideloadly installs on iPhone

---

## How it works
Your Code on GitHub → GitHub free Mac server builds IPA → You download IPA → Sideloadly installs on iPhone
No Apple Developer account. No Mac. Completely free.

---

## STEP 1 — Create GitHub Account
Go to https://github.com/signup and create a free account.

---

## STEP 2 — Create Repository
1. Go to https://github.com/new
2. Name it: finance-app
3. Set to PUBLIC (more free build minutes)
4. Click Create repository

---

## STEP 3 — Upload Files to GitHub (No Git needed)

Upload these files using GitHub website (Add file → Upload files):
- App.js
- app.json
- package.json
- eas.json
- babel.config.js
- .gitignore

For the workflow file — use Add file → Create new file:
- Filename: .github/workflows/build-ios.yml
- Paste the contents of build-ios.yml
- Click Commit new file

---

## STEP 4 — Watch the Build

1. Click the Actions tab on your GitHub repo
2. See "Build iOS IPA" running (yellow = building)
3. Takes 15-25 minutes
4. Green checkmark = done

---

## STEP 5 — Download the IPA

1. Click the completed build
2. Scroll to Artifacts section
3. Click finance-ipa → downloads a ZIP
4. Unzip it → finance.ipa is inside

---

## STEP 6 — Install on iPhone 7 Plus

Download Sideloadly from https://sideloadly.io

1. Connect iPhone via USB → trust computer
2. Open Sideloadly
3. Drag finance.ipa into the window
4. Enter Apple ID: rakib.404.dev@gmail.com
5. Enter Apple ID password
6. Enter 2FA code from iPhone
7. Click Start → wait 2 minutes

Trust the app:
Settings → General → VPN & Device Management → tap your Apple ID → Trust

---

## STEP 7 — Updating the App

To change design:
1. Go to your GitHub repo
2. Click App.js → click pencil icon to edit
3. Save → GitHub auto-rebuilds IPA
4. Download new IPA → re-sideload

No terminal needed for updates!

---

## Adding Offline Storage

Add to package.json dependencies:
"@react-native-async-storage/async-storage": "1.23.1"

Use in App.js:
import AsyncStorage from '@react-native-async-storage/async-storage';
await AsyncStorage.setItem('key', 'value');        // save
const val = await AsyncStorage.getItem('key');     // read

Data stored permanently on iPhone. Re-sideloading does NOT delete data.

---

## 7-Day Refresh (Free Apple ID)

Every 7 days app shows "Unable to Verify":
- Plug iPhone → open Sideloadly → drag same IPA → Start
- Takes 2 minutes, data is safe

To avoid this: install AltServer from https://altstore.io (auto-refreshes over Wi-Fi)

---

## Troubleshooting

Build fails at CocoaPods → click Re-run jobs on GitHub Actions
Build fails with scheme error → check app.json has "name": "finance"
Sideloadly device not found → use different USB cable, install iTunes
App wont open → Settings → VPN & Device Management → Trust
