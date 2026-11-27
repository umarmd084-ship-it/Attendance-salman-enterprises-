# Android conversion starter

The existing website is packaged with Capacitor rather than rewritten.

### Requirements
- Node.js 22 or newer
- Android Studio + Android SDK

### Commands
```bash
npm install
npx cap add android
npx cap sync android
npx cap open android
```

In Android Studio, use Build > Build Bundle(s) / APK(s) > Build APK(s) for a local test APK.

Set the exact Vercel origin in `www/config.js` first. Review `ANDROID_CONVERSION_STATUS.md` before deploying or distributing.


### Configured Vercel API
The Android web bundle is configured to call:
`https://salmanenterprisesattendancexmohduma.vercel.app`

The API endpoint could not be independently verified from this environment. Before installing for staff, test `https://salmanenterprisesattendancexmohduma.vercel.app/api/health` in a browser and confirm it returns a healthy response.
