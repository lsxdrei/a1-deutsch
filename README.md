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

## Not built yet
Lessons for units 3 to 12, recording your voice in Sprechen, more than one mock exam, and app icon.
