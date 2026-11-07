# CPI Offline Android – Store and Export Enhancements

## Included in this update
- Store Management UI: add/edit stores, address, contact, outlet assignment, active/inactive status, search and filters.
- Outlet overview for outlets 1–6.
- Local audit log for store creation, edits and status changes.
- Export Center with outlet/store/date/month/year/phase filters and preview counts.
- Multi-worksheet Excel-compatible SpreadsheetML workbook export (opens in Microsoft Excel as `.xls`).
- Existing CPI entry, Rice three-box entry, local backup and A4 printing are retained.
- GitHub Actions workflow avoids `android-actions/setup-android@v3`, which previously failed due to sdkmanager version mismatch.

## Important format note
The current export implementation creates a multi-sheet Excel-compatible `.xls` SpreadsheetML workbook. It is **not** an Office Open XML `.xlsx` file. A true `.xlsx` exporter still needs to be implemented and validated before representing this as the requested `.xlsx` deliverable.

## Storage note
This project currently persists application records in WebView localStorage on the device, not in a native SQLite database. Store directory and audit entries are stored locally in the same origin. The current changes do not migrate the application to SQLite. Back up the app data before uninstalling or clearing application storage.

## Build with GitHub Actions
1. Upload the contents of this project folder to the root of the existing repository (including `.github/workflows/build-apk.yml`).
2. Commit and push to `main`, or use Actions > Build CPI Android APK > Run workflow.
3. Download the `CPI-Offline-Android-debug-APK` artifact after a successful run.

## Validation
The source changes were reviewed for structure, but a complete Android APK build and on-device functional test have not been performed in this environment. Verify the GitHub Actions result and test on a device before official PSA use.
