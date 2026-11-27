# Salman Enterprises Android conversion — Stage 1

This package is a Capacitor-ready copy of the uploaded website source. It preserves the existing HTML interface and changes the two cloud-sync calls so the Android app can be pointed at the existing Vercel API using `www/config.js`. The original website files and API files are retained.

## Before generating an APK

1. Replace `https://YOUR-VERCEL-DOMAIN.vercel.app` in `www/config.js` with the exact deployed Vercel origin.
2. Install Node.js 22+ and Android Studio with Android SDK.
3. Run `npm install`.
4. Run `npx cap add android` once.
5. Run `npx cap sync android`, then `npx cap open android`.

## Important: not production-ready yet

The uploaded source currently has security blockers that must be fixed before employees install a distributable APK:

- `api/state.js` permits unauthenticated GET and POST access to the entire shared ERP state.
- User records (including passwords) are part of the client-side shared state. The README also documents a default admin login. Rotate any credentials that may have been used outside development.
- The current frontend stores login session in localStorage and does not use a server-issued authenticated session/token.
- A native app request to the Vercel API will require a carefully restricted CORS policy and authenticated API design. Do not solve this by allowing every origin or exposing database credentials in the app.
- The current code captures GPS once at check-in, check-out and shop visit. No continuous tracking endpoint or tracking-history collection exists yet.
- No Android native foreground location service is included in this Stage 1 package. Continuous background tracking must be added as a transparent, user-visible native feature with explicit permission and a persistent notification.

## Existing functionality confirmed in the uploaded source

- Single-page HTML/JavaScript frontend.
- Office check-in and check-out use a 50m geofence.
- Shop visit stores GPS coordinates, sale, collection, note and timestamp.
- Browser sync reads/writes the entire shared state through `/api/state` every 12 seconds.
- MongoDB connection is server-side in `api/_db.js` using `MONGODB_URI`.

## Current build limitation

This is a source conversion starter, not a signed APK. Android Studio/SDK and a device/emulator build are required to compile and test the Android package.
