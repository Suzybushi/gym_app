[中文](README.md) | [English](README.en.md)

# 铁馆 (Iron Gym) · Workout Log

A zero-dependency, single-file workout log web app (PWA-style) that works out of the box. All data stays in the browser's `localStorage` — no account, no backend, no data upload. The page itself must be loaded over the network the first time.

> The app UI is currently in Chinese.

## Features

- **Two built-in programs**
  - Push / Pull / Legs / Rest four-day strength program (231 protocol)
  - Left AIC + Right BC rehab plan (B1 / B2 / Rest cycle + daily Plan A minimum-dose fallback)
- **Workout logging**: weighted exercises log weight / reps; rehab exercises use per-set completion. Saved by date.
- **Exercise alternatives**: switch variations without mixing up records
- **Reuse last session**: weighted exercises show previous numbers and can fill them in with one tap
- **Rehab-specific tools**: full technique notes, timed-drill countdowns (holds, stretches, carries), per-set completion
- **Daily nutrition estimate**: calories and macros based on bodyweight and goal (bulk / maintenance & shaping / cut)
- **Plan import**: paste training plan text (tables, numbered lists, bullets, and Markdown headings are supported); it is parsed into days and exercises
- **JSON backup**: export / import all data for device migration
- **Cross-platform**: runs in modern browsers on Windows, iOS, and Android; add to home screen in iOS Safari and Android Chrome

## Compatibility

- **Windows**: Chrome / Edge / Firefox
- **iOS**: Safari (add to home screen)
- **Android**: Chrome / Edge / Firefox (add to home screen)
- No native client required — just open it in a browser.

## Program Philosophy

The built-in rehab plan draws on concepts from:

- **CES (Corrective Exercise Specialist, NASM)**: inhibit → lengthen → activate → integrate
- **PRI (Postural Restoration Institute)**: Left AIC / Right BC, ZOA (Zone of Apposition), left rib sink / right chain release

This is a personal training program. It is not an official NASM or PRI program, certification, or treatment, and it is not medical advice.

## Online

https://suzybushi.github.io/gym_app/

## Run Locally

Opening `index.html` directly usually works. If your browser restricts `localStorage` on `file://`, use the local server below:

```bash
python -m http.server 8000
```

Then open http://localhost:8000/

## Usage

1. On first launch, choose a built-in program or paste your own plan.
2. Use the date strip at the top to calibrate "which day is today": Day A/B/C/D for the strength program, B1/B2/Rest for the rehab plan.
3. Tap an exercise card to expand it: enter weight / reps for weighted exercises, or mark sets complete for rehab exercises.
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

> GitHub Pages may require a paid plan for private repositories. If it is unavailable, drag `index.html` into a static host such as Netlify Drop.

## Disclaimer

This is a personal workout-logging tool and is not medical advice. The built-in program draws on CES and PRI concepts but is not affiliated with, endorsed by, or certified by NASM, the Postural Restoration Institute, or any other organization. Stop training and consult a professional if you experience pain or discomfort.
