# Build the CPI Android APK without Android Studio

This project includes a GitHub Actions workflow at `.github/workflows/build-apk.yml`.
It builds the debug APK in GitHub's cloud environment. You do not need Android Studio,
Java, Gradle, or the Android SDK installed on your Windows computer.

## Steps

1. Create or sign in to a GitHub account at https://github.com.
2. Create a new repository, for example `CPI-Offline-Android`. A private repository is fine.
3. Extract this ZIP on your computer.
4. Open the extracted `CPI_Offline_Android` folder in VS Code.
5. In VS Code, open Terminal > New Terminal and run these commands from the project folder:

   ```powershell
   git init
   git add .
   git commit -m "Add CPI offline Android project and cloud APK build"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/CPI-Offline-Android.git
   git push -u origin main
   ```

   Replace `YOUR-USERNAME` with your GitHub username. Git may ask you to sign in.

6. On GitHub, open your repository and select **Actions**.
7. Select **Build CPI Android APK**. If it has not started automatically, click **Run workflow**.
8. Wait for the workflow to finish with a green check mark.
9. Open the completed workflow run. Under **Artifacts**, download `CPI-Offline-Android-debug-APK`.
10. Extract the downloaded artifact ZIP. It contains `app-debug.apk`.
11. Transfer `app-debug.apk` to your Android phone and install it. Android may ask you to allow installation from that file source.

## Notes

- The first cloud build needs internet to download Gradle and Android SDK components.
- The installed application is intended to run locally/offline; building it in GitHub does not mean the app needs internet to operate.
- This workflow creates a **debug APK**, suitable for testing and direct installation. A signed release APK should be prepared separately before wider official distribution.
- Keep the GitHub repository private if the source or included reference data should not be public. Do not commit confidential or personal data.
