# JBR Logistics Flutter app

This package contains the provided Flutter UI source and a GitHub Actions workflow that builds a release Android APK in the cloud.

## Build an APK for free using GitHub Actions

1. Create a GitHub repository and upload the contents of this folder to it (keep the `.github/workflows/build-apk.yml` file).
2. Open the repository's **Actions** tab.
3. Select **Build Android APK** and press **Run workflow**. Alternatively, push the files to the `main` branch.
4. When the workflow completes, open that run and download **jbr-logistics-release-apk** from **Artifacts**. The ZIP artifact contains `app-release.apk`.

## Build locally

Install Flutter and the Android SDK, then run:

```bash
flutter create --platforms=android --project-name=jbr_logistics_mobile_app --org=com.jbrlogistic .
flutter pub get
flutter build apk --release
```

The APK output path is `build/app/outputs/flutter-apk/app-release.apk`.

## Important notes

- The supplied UI currently uses sample shipment data and placeholder tracking information. It is not connected to a live dispatch, GPS, payment, or backend service.
- This environment does not have the Flutter SDK or Android SDK installed, so an APK could not be compiled and tested here. The included workflow performs the build on GitHub-hosted runners.
