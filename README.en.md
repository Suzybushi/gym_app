[中文](README.md) | [English](README.en.md)

# 铁馆 (Iron Gym) · Workout Log

A zero-dependency, single-file, open-and-use workout log PWA. All data stays in the browser's `localStorage` — no account, backend, or network requests required.

> The app UI is currently in Chinese.

## Features

- **Two built-in programs**
  - Push / Pull / Legs / Rest four-day strength program (231 protocol)
  - Left AIC + Right BC rehab plan (B1 / B2 / Rest cycle + daily Plan A minimum-dose fallback)
- **Workout logging**: weight, reps, and completion state, saved by date
- **Exercise alternatives**: switch variations without mixing up records
- **Reuse last session**: shows previous numbers and fills them in with one tap
- **Rehab-specific tools**: full technique notes, hold / stretch countdowns, per-set completion
- **Daily nutrition estimate**: calories and macros based on bodyweight and goal (bulk / body recomposition / cut)
- **Plan import**: paste an AI-generated training plan and parse it into days and exercises
- **JSON backup**: export / import all data for device migration
- **Mobile-first**: works well on iPhone and can be added to the home screen

## Online

https://suzybushi.github.io/gym_app/

> If you see a 404, enable GitHub Pages first in **Settings → Pages**: choose the `main` branch and the `/ (root)` folder, save, and wait 1–3 minutes for the build.

## Run Locally

Open `index.html` directly in a browser.

Or serve it locally:

```bash
python -m http.server 8000
```

Then open http://localhost:8000/

## Usage

1. On first launch, choose a built-in program or paste your own plan.
2. Use the date strip at the top to calibrate "which day is today": Day A/B/C/D for the strength program, B1/B2/Rest for the rehab plan.
3. Tap an exercise card to expand it, then enter weight / reps or mark sets complete.
4. The rehab plan includes a daily "Plan A" fallback card; it is expanded by default on rest days.
5. The `＋` button switches built-in plans or imports a new plan; `⬇` exports a full backup.

## Data & Privacy

- Stored in browser `localStorage` under the key `gymlog.v1`
- No server uploads, no account, no tracking
- To move devices or URLs, use the in-app "Export backup / Import backup" flow
- Clearing browser site data will delete your workout history

## Project Structure

```
index.html      # all UI, styles, data, and logic
.quality-pass   # local pre-push quality-gate credential; not needed to run the app
README.md       # Chinese README
README.en.md    # this English README
```

No build step, no npm dependencies.

## Deploy to GitHub Pages

1. Open the repository's **Settings → Pages**
2. Set **Source** to `Deploy from a branch`
3. Choose branch `main` and folder `/ (root)`
4. Click **Save** and wait 1–3 minutes
5. Visit https://suzybushi.github.io/gym_app/

## Disclaimer

This is a personal workout-logging tool, not medical advice. Stop training and consult a professional if you experience pain or discomfort.
