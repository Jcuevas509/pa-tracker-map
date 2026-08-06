# Shared notes & status setup (5 minutes)

The map page is static (GitHub Pages), so shared notes/status need a free **Firebase Realtime Database**.

## Steps

1. Go to https://console.firebase.google.com/ and **Create a project** (name it `pa-tracker`).
2. Click the **Web** icon (`</>`) to add a web app. Register app (no hosting needed).
3. Copy the `firebaseConfig` object (apiKey, authDomain, databaseURL, projectId, …).
4. In the left menu: **Build → Realtime Database → Create Database**.
   - Pick a region close to you (e.g. `us-east1`).
   - Start in **test mode** for now (open read/write for 30 days), or use rules:

```json
{
  "rules": {
    "paTracker": {
      ".read": true,
      ".write": true
    }
  }
}
```

5. Open the live map → **Share setup** → paste your name + the config → **Save & sync**.
6. To make sync work for **everyone with the link** (not just your phone), send the same `firebaseConfig` so it can be embedded in the published page as `EMBEDDED_FIREBASE_CONFIG`.

## Using it

- Tap a person → set **Status** (Open / Contacted / Scheduled / Visited / Done / Issue) and **Notes**.
- Changes appear live for everyone on Live sync.
- Your name is stored on edits (“Updated by …”).
