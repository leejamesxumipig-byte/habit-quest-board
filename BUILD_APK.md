# Build the Habit Quest Board APK

The app is fully offline (no internet needed). Pick ONE method:

## A) Android Studio / command line (needs Node 18+, Java 17, Android SDK)
    npm install
    npx cap add android
    npx cap sync android
    cd android && ./gradlew assembleDebug      (Windows: gradlew.bat assembleDebug)

APK: android/app/build/outputs/apk/debug/app-debug.apk
Copy it to your phone and install (allow "Install unknown apps").
(Or run `npx cap open android` and use Build > Build APK(s) in Android Studio.)

## B) No setup: GitHub Actions
1. Create a free GitHub repo and upload everything in this folder
   (including the hidden .github folder).
2. Open the Actions tab > "Build APK" > Run workflow.
3. Download "habit-quest-board-apk" from the finished run and install it.

## Notes
- Accounts and habit data live on the phone (localStorage). Uninstalling the app erases them.
- Passwords are salted + SHA-256 hashed; there is no password recovery since there is no server.
- To edit the app, change www/index.html, then run `npx cap sync android` and rebuild.
