# Training Log

A private workout tracker that runs in the phone browser and installs to the home screen. No account, no server, no build step: plain HTML, CSS and JavaScript.

- **Landing screen** with a greeting that uses your preferred name, your week so far and what's up next.
- **Exercise guides**: tap any exercise name (or How to) for step-by-step form, safety tips and a front/back muscle map showing main and helping muscles. Browse them all in the Coach tab.
- **Log** a 3-day full-body plan (A, B, C) or build your own. Sets are prefilled from last time; tick each one when done.
- **Flexible exercises**: weight and reps, reps only, hold time, weight and time, or cardio. Add your own.
- **Joint rest markers** (knee, elbow) flag exercises and swap them automatically in new workouts.
- **Diary** notes by day, plus a note on every workout.
- **Progress** charts: body weight against your goal, strength per exercise, active days per week.
- **Coach**: tips from your own numbers (pace, ready to add weight, stuck lifts) and answers to common questions. Works offline.

## Publish on GitHub Pages

1. Create a new repository on GitHub and upload everything in this folder to the top level of the repo.
2. In the repo, open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, and save.
3. After a minute the app is live at `https://<your-username>.github.io/<repo-name>/`.

All file paths are relative, so it works under any repo name.

## Install on a phone

- **iPhone (Safari):** open the page, tap Share, then **Add to Home Screen**.
- **Android (Chrome):** open the page, tap the menu, then **Install app**.

Using the installed version also protects your data better, because browsers clear storage for sites you haven't opened in a while.

## Your data

Everything is stored in your browser's local storage on that one device. Nothing is sent anywhere, and nothing about you is in this repo. Because of that:

- Use **Me → Download backup** about once a month and keep the file somewhere safe (iCloud Drive, Google Drive, email it to yourself).
- Use **Me → Restore from backup** to move to a new phone or recover after a reset.
- A repo that is public only exposes the app's code, not your log. Even so, don't put personal numbers in the source files.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app |
| `manifest.webmanifest`, `icon*.png`, `icon.svg`, `apple-touch-icon.png` | Home screen install |
| `sw.js` | Offline support. Network first, so updates appear when you're online |

To update the app later, replace `index.html` in the repo. To force devices to refresh the offline cache, change `V` in `sw.js`.
