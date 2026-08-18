PAYNEST ANDROID BUILD

Source:
PayNest-v1-main.zip -> web-source/

Android:
Trusted Web Activity (TWA)
Application ID: com.paynest.smartinstallment
Target SDK: 36
Version: 1.0.0

IMPORTANT:
- This project uses the current PayNest web deployment as its single web source.
- Before Google Play production, create a release/upload key and configure Play App Signing.
- The final Digital Asset Links file must contain the real SHA-256 fingerprint of the certificate used by the installed Play build.
- The assetlinks.json file belongs at the domain root:
  https://eknutthasakpetluanoio-rgb.github.io/.well-known/assetlinks.json
- Do not publish the placeholder fingerprint.

BUILD:
Open the PayNest-Android folder in current Android Studio.
Let Android Studio sync Gradle.
Build > Build Bundle(s) / APK(s) > Build APK(s) for test.
After testing, configure release signing and Build > Generate Signed Bundle / APK > Android App Bundle.

This archive intentionally does not contain a release keystore or signed AAB.
