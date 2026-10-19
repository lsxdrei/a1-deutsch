# A1 Deutsch

A mobile app (React Native + Expo) that prepares you for the **Goethe-Zertifikat A1: Start Deutsch 1** exam.
Everything is free right now and works offline.

## What is inside
- **Units 1 and 2**: words, grammar, dialogue with audio, 10 exercises each (units 3 to 12 are listed but their lessons are not written yet).
- **Exam practice**: Lesen (15 items), Hören (15 items, audio plays twice in exam mode), Schreiben (form + short message), Sprechen (10 cards).
- **Mock exam**: all four modules with timers, scores out of 100, pass mark 60, best scores saved.
- **Flashcards**: spaced repetition (Leitner) over all learned words.
- Progress, XP and streak are saved on the phone.

The exam material is practice content in the style of the real exam. It is **not** official Goethe content.
Item counts and scoring are approximations: compare with the free official Modelltest on goethe.de.
Have a German teacher review the German before you publish the app.

## Run it on your phone, fastest way (Expo Go)
1. Install **Node.js 20+** and the **Expo Go** app on your phone.
2. In this folder run:
   ```bash
   npm install
   npx expo install --fix
   npx expo start
   ```
3. Scan the QR code with Expo Go (Android) or the Camera app (iPhone). Phone and computer must be on the same Wi-Fi.

## Get an installable Android app (APK) from GitHub, no Expo account needed
1. Create a GitHub repository and upload everything in this folder (see below).
2. Open the **Actions** tab, choose **Build Android APK**, click **Run workflow**.
3. After about 10 to 20 minutes, open the finished run and download **a1-deutsch-apk** under *Artifacts*. Unzip it.
4. Send the `.apk` to your phone and open it. Android will ask you to allow "install unknown apps" once.

This APK is signed with a debug key, which is fine for testing and sharing with friends but **not** for the Play Store.

## Other ways to build
- **EAS Build** (free Expo account): `npm i -g eas-cli`, then `eas login` and `eas build -p android --profile preview`. You get a download link for the APK. For the Play Store use `--profile production` (an AAB file).
- **iPhone**: Expo Go works for testing. A standalone iOS app needs a paid Apple Developer account ($99 a year) and `eas build -p ios`.

## Upload to GitHub
```bash
git init
git add .
git commit -m "A1 Deutsch"
git branch -M main
git remote add origin https://github.com/YOUR-NAME/a1-deutsch.git
git push -u origin main
```

## Free mode and the paywall
`src/config/plan.ts` has `PAYWALL_ENABLED = false`, so everything is unlocked. Set it to `true` to bring back the Free/Pro limits.
The paywall purchase is simulated. Real subscriptions need RevenueCat (`react-native-purchases`) in a development build, and the Pro check must come from the store, not a local flag.

## Package versions
`package.json` uses `latest` and the setup runs `npx expo install --fix` so every package matches your Expo SDK.
Once the app runs well, commit the generated `package-lock.json` and replace `latest` with the real versions for reproducible builds.

## Not built yet
Lessons for units 3 to 12, recording your voice in Sprechen, more than one mock exam, an app icon, and real in-app purchases.

## Project layout
```
app/            screens (Expo Router): home, unit, module, exam, flashcards, paywall
src/data/       units, exam material, exam structure
src/components/ lesson steps, exercise runner, exam runners
src/store/      progress, exam scores, subscription state
src/config/     plan.ts (free/pro switch)
```
