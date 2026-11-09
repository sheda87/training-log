# Training Log

A private workout tracker that runs in the phone browser and installs to the home screen. No account, no server, no build step: plain HTML, CSS and JavaScript.

- **Landing screen** with a greeting that uses your preferred name, your week so far and what's up next.
- **Exercise guides**: tap any exercise name (or How to) for step-by-step form, safety tips and a front/back muscle map showing main and helping muscles. Browse them all in the Coach tab.
- **Log** a 3-day full-body plan (A, B, C, each with two core moves) or build your own. Sets are prefilled from last time; tick each one when done.
- **Flexible exercises**: weight and reps, reps only, hold time, weight and time, or cardio. Add your own.
- **Swap suggestions**: when a joint is resting, a flagged exercise shows a suggested replacement with a one-line reason and a one-tap swap. The Swap sheet lists suggestions first.
- **Joint rest markers** (knee, elbow, ankle, shoulder) flag exercises and swap them automatically in new workouts. Me shows exactly which exercises in your plan would change, and a banner swaps an already-started workout in one tap.
- **Notes that help**: words like "sore knee", "shoulder tweak", "tired" or "leg press felt easy" in your diary and workout notes can suggest resting a joint, resuming it, a light walk day, or a weight change on that exercise. Nothing changes until you tap, it all stays on your device, and you can turn it off in Me.
- **Mobility and core**: a 10 minute warm-up, a 6 minute core finisher and a 5 minute cooldown you can add to any workout with one tap, plus a 25 minute mobility + core day that counts as an active day. Each move has a form guide. Optionally start every workout with the warm-up (Me tab).
- **Weekly goal**: pick your active days per week (1 to 7) in the profile. It applies right away.
- **Timer**: every timed set (planks, stretches, carries, cardio) has a play button. Get-ready countdown, seconds-to-goal, a beep at your goal, a Pause button, an automatic switch-sides cue for "each side" holds, and the screen stays awake. Done saves the time and ticks the set.
- **Diary** notes by day, plus a note on every workout.
- **Progress** charts: body weight against your goal, strength per exercise, active days per week.
- **Heart rate and effort**: log minutes, average and peak heart rate on any workout, or import them from Apple Health (Me tab). You get a zone gauge and plain-language feedback on whether the effort was too low, typical or too high for the kind of workout, plus progress charts.
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

## Heart rate import

Me tab, Watch and heart rate. On an iPhone: Health app, tap your picture, Export All Health Data, then choose the export.zip here. It is read on your device and never uploaded. A CSV with columns like Date, Type, Duration, Avg Heart Rate, Max Heart Rate also works. Zones use your max heart rate (set it in Me, or it is estimated as 208 minus 0.7 times age).

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

## Exercise diagrams
Each free-weight, bodyweight and mobility exercise has simple stick-figure drawings (start and end positions) at the top of its guide sheet. They are drawn in code, work offline, and follow the written steps. They are sketches, not a substitute for the steps or a coach.
