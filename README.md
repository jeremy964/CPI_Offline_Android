# CPI Price Form – Offline Android Project

This is an Android Studio project that packages the CPI/Rice data-entry interface and reference data into an Android WebView application. The HTML, CSS, JavaScript, logos, and reference datasets are bundled inside the APK. The app does not make network requests and is designed to work offline after installation.

## Included in this conversion

- Android launcher application named **CPI Price Form**.
- CPI Price Entry with Outlet, Store, Month, Year, Phase, commodity search, Price, and Remarks.
- Rice Price Entry for Outlets 1–6, with three Variety/Brand + Price/Kg boxes per classification.
- Local on-device saving using WebView localStorage.
- Backup export/import in JSON format.
- A4 landscape printing through Android's system Print service.
- PSA and Bagong Pilipinas logos bundled in the app.
- Reference datasets extracted from the supplied Excel workbooks.

## Important source-file coverage

The supplied ZIP contains CPI commodity reference workbooks for **Outlet 1, Outlet 2, and Outlet 4**. The CPI screen offers Outlets 1–6, but Outlets 3, 5, and 6 will be empty until their commodity reference workbooks are provided and imported in a future update. Rice reference data is included for all six outlets.

## Build the APK (free)

An Android SDK/Gradle build environment is required to compile an APK. This workspace did not contain the Android SDK or Gradle, so an APK binary could not be compiled here. The complete Android Studio source project is provided.

1. Install Android Studio on a Windows, Mac, or Linux computer (free).
2. Extract `CPI_Offline_Android_Project.zip`.
3. In Android Studio choose **Open** and select the extracted `CPI_Offline_Android` folder (the folder containing `settings.gradle`).
4. Allow Gradle sync to download the Android Gradle Plugin and SDK components. This is a one-time build setup and requires internet.
5. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
6. Android Studio creates the APK under `app/build/outputs/apk/debug/app-debug.apk`.
7. Copy the APK to your Android phone, allow installation from that file manager if prompted, and install it.
8. Turn off Wi-Fi/mobile data and open **CPI Price Form** to test offline operation.

## Printing

Choose a specific store in CPI Price Entry before printing. In Rice Price Entry choose an outlet. Tap the print button, then select an available printer or save to PDF in Android's print screen. Confirm A4 and Landscape in the print settings. Printer options vary by Android device and installed print services.

## Local data and backup

Price entries are stored in the app's private WebView local storage on that phone. They are not synchronized to another phone. Use **Backup & Data > Export Backup** regularly. Keep the JSON backup in a safe location. Import it after reinstalling or moving to another phone.

## Current limitations / next development items

- This is the first Android conversion source package, not a byte-for-byte reproduction of the desktop Swing screen or its exact printed form geometry. Review the printed A4 output against the official form before operational use.
- The original desktop Excel workbook import dialog is not yet implemented in this Android conversion. The reference data from the supplied workbooks is preloaded; JSON backup import/export is available.
- CPI commodity reference coverage is limited to the three outlet workbooks present in the uploaded ZIP (1, 2, and 4).
- Verify all prices, remarks, and printed output before using the app for official collection. Keep the original desktop project and backups unchanged.

## Project structure

- `app/src/main/java/ph/psa/cpiandroid/MainActivity.java` – Android WebView shell and Android print bridge.
- `app/src/main/assets/index.html` – application pages.
- `app/src/main/assets/app.js` – local data-entry and backup logic.
- `app/src/main/assets/style.css` – responsive mobile and print styling.
- `app/src/main/assets/data/` – bundled CPI and rice reference datasets.
- `app/src/main/assets/logos/` – PSA and Bagong Pilipinas logos.
