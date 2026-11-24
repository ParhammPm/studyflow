# StudyFlow

> **A local-first study planner for Iranian Konkur students.**

[![License: MIT](https://img.shields.io/github/license/ParhammPm/studyflow)](https://github.com/ParhammPm/studyflow/blob/main/LICENSE)
[![Version](https://img.shields.io/badge/version-1.11.5-blue)](https://github.com/ParhammPm/studyflow/blob/main/latest.json)
[![Python](https://img.shields.io/badge/python-3-blue)](https://www.python.org/)
[![Stars](https://img.shields.io/github/stars/ParhammPm/studyflow)](https://github.com/ParhammPm/studyflow)
[![Forks](https://img.shields.io/github/forks/ParhammPm/studyflow)](https://github.com/ParhammPm/studyflow/network/members)

**استادی‌فلو** یک برنامه‌ریز مطالعه‌ی لوکال برای کنکور است: برنامه‌ی روزانه، کتاب تست، آزمون‌های آزمایشی و تحلیل عملکرد — بدون حساب کاربری و بدون سرور ابری؛ داده‌ها روی لپ‌تاپ خودت می‌مانند.

Konkur is a year-long marathon, and generic to-do apps don't understand it: a Jalali calendar, mock-exam budgets, test books with hundreds of questions per chapter, and a study day that doesn't end at midnight. StudyFlow is built for exactly that — a single-user web app that runs on your own computer, plans your days, tracks every test you solve, and shows you, with real numbers, what you actually did.

Persian-first · Jalali calendar · Local-first · RTL · Light & dark themes

---

## 📷 Demo

Screenshots of the current UI are coming soon — they will live in `docs/screenshots/`.

Until then, here is the tour:

| Area | What you see |
| --- | --- |
| **Dashboard** | Today only: the boxes of the current study day, today's tests, overdue items, and an upcoming-exams strip. |
| **Programme** | A Jalali monthly calendar. Every day shows its study boxes with done ticks, times, test counts and accuracy. |
| **Test Books** | Real chapter/section tables of contents, with study status, mastery, notes and test results per section. |
| **Exams** | Mock exams (Maz, Zoodbist, school exams) with structured budgets, subtopics and per-topic progress. |
| **History & Analytics** | A monthly archive, activity heatmap, trend charts, per-subject analysis and smart reports — all from your real data. |

👉 **[Download the latest release](https://github.com/ParhammPm/studyflow/tree/main/releases)** — `studyflow-v1.11.5.zip` (current version; see [`latest.json`](https://github.com/ParhammPm/studyflow/blob/main/latest.json)).

---

## What is StudyFlow?

StudyFlow is a local, single-user study planner for Konkur — the Iranian university entrance exam. It is a plain web app served by a small Python server (standard library only, no pip installs, no build step) on your own machine at `http://localhost:8765`.

There are no accounts, no cloud server, no tracking and no advertising. Your programme, ticks, test results, exam data and settings are stored on your own computer, outside the app folder, so replacing the app with a new version never touches your data.

The app ships with an **empty programme**. You fill it by importing your Google Calendar, importing an `.ics`/JSON export, or by creating assignments — each assignment also creates a programme box.

---

## ✨ Features

### 📅 Smart Planning

- **Jalali monthly calendar** — one shared month state: navigate between months, jump back to today, year rollover handled.
- **Daily study boxes** — done tick, time, test counts (done / correct) and automatic accuracy; full editing of every box.
- **A study day runs 03:30–03:30** (Asia/Tehran) — applied everywhere: boxes, assignments, stats, calendar, reports and overdue items. Exam countdowns still use real calendar dates.
- **Real study timer** — start / pause / resume on any box, plus manual "actual minutes". Actual time is shown next to scheduled time, never instead of it.
- **Activity types** — mark a box as class, study, test or homework. Class boxes get a small `کلاس` badge in the daily list, and History & Analytics can filter by activity type.
- **Upcoming-exams strip** on the dashboard, and a **Remaining tests** view for what is still open.

### 📚 Test Books

- **Real chapter/section structure** — study status, mastery level and notes per section.
- **Test entry per section** — total / correct / wrong / unanswered, with automatic accuracy.
- **Manual multi-select linking** — link any exam topic, assignment or programme box to book sections; each book section shows its reverse links. Nothing is ever linked automatically.

### 📝 Exams

- **Mock exams: Maz, Zoodbist and school exams** — with structured budgets, subtopics and a progress indicator per topic.
- **Results** — score (taraz), rank, correct / wrong / unanswered per exam.
- **Topic progress** — see per-topic completion and copy a ready-made prompt to analyse a topic with Gemini.

### 📊 History & Analytics

- **Monthly archive** of boxes, with search.
- **Activity heatmap**, trend charts and per-subject dashboards.
- **One activity-type filter** (all / class / study / test / homework / other) driving every KPI, chart, table, daily/weekly/monthly stat, period comparison, heatmap and insight.
- **Two-period comparison** and smart reports built only from real data — no invented numbers.
- **CSV export** and print-friendly PDF (via the browser).

### 🤖 Gemini

- **Progress analysis with your own Gemini API key** (from Google AI Studio).
- **Model picker + test panel** — see which models actually work with your key, with per-model latency (ms) and error classification; known models are annotated with their status (stable / deprecated / shut down).

### 🔄 Google Calendar

- **One-way ICS pull** — paste your calendar's private ICS address once; the app pulls new / moved / cancelled events. Your ticks and tests are never touched, and boxes you deleted stay deleted.
- **Manual `.ics` / JSON import** with preview and confirm.
- **Optional two-way sync** via your own Google Cloud OAuth client (Desktop app, PKCE): edits in the app push to Google, and in a conflict Google Calendar stays the source of truth. Tokens are stored locally only.

### 💾 Data & Backup

- **Everything local** — state, test books, the Gemini key, and B2 / calendar settings live in `%APPDATA%\KonkurApp` (Windows), outside the app folder.
- **Automatic versioned local backups** (~30 recent versions per file) with verified restore; corrupt data is auto-restored from the newest verified backup.
- **Optional Backblaze B2 cloud backup** (S3-compatible, your own private bucket) with version restore.
- **One-click self-updates** — the app reads this repo's [`latest.json`](https://github.com/ParhammPm/studyflow/blob/main/latest.json) manifest, verifies the zip's SHA-256, backs up the current code, then installs. Installing always needs your click and confirmation, never happens automatically. Manual install from a zip file or a link, and rollback, are built in.

### 🌐 Language & Design

- **Bilingual (Persian/English), RTL, light and dark themes**, with a complete colour design system — each subject and category keeps one fixed colour across all pages and charts.

---

## Why StudyFlow?

Generic task managers treat every task the same. A Konkur student doesn't need another to-do list — they need a tool that understands the exam itself:

- **Persian / RTL first** — built in Persian, not translated as an afterthought.
- **Jalali calendar** — the programme lives in Jalali months, with real Jalali↔Gregorian conversion.
- **Iranian exam structure** — Maz, Zoodbist and school exams, with chapter-level budgets and taraz/rank results.
- **Test-book tracking** — progress per chapter and section, not just a checkbox.
- **Mock-exam budgeting** — every exam topic is budgeted, linked to book sections, and tracked to completion.
- **A study day that starts at 03:30** — late-night study counts towards the day it belongs to.
- **Analytics that answer "what did I actually do?"** — real hours, real tests, real trends; nothing invented.
- **Local-first data ownership** — your data stays on your machine. No account, no subscription, no tracking.

---

## 🚀 Quick Start

**Windows**

1. Download the latest zip from **[releases/](https://github.com/ParhammPm/studyflow/tree/main/releases)** (e.g. `studyflow-v1.11.5.zip`) and extract it.
2. Double-click **`start.bat`** — your browser opens at `http://localhost:8765`.
3. To stop, close the server window.

**Requirements:** **Python 3** (from [python.org](https://www.python.org/); tick **Add Python to PATH** during install). Nothing else — the server uses only the Python standard library.

**macOS / Linux:** run `python3 server.py` and open `http://localhost:8765`.

**First run:** the app ships with an empty programme. Fill it from the Backup tab → Google Calendar sync (paste your calendar's private ICS address: Google Calendar → Settings → calendar → *Secret address in iCal format*), import an `.ics`/JSON export, or create assignments from the Assignments tab.

---

## 🏗️ Architecture

```
StudyFlow
├── server.py            # Python stdlib-only HTTP server (no pip installs)
├── b2.py                # Backblaze B2 client (stdlib SigV4)
├── start.bat            # Windows launcher (opens http://localhost:8765)
├── version.json         # current version
├── public/
│   ├── index.html       # single-page app shell
│   ├── app.js           # dashboard, programme, books, exams, sync, backup
│   ├── analytics.js     # history & analytics (charts, heatmap, reports)
│   ├── i18n.js          # Persian/English strings + Jalali helpers
│   ├── styles.css       # design tokens, light & dark themes
│   ├── data.json        # programme seed (empty in releases)
│   ├── exams.json       # exam budget seeds
│   └── testbook-seed.json
├── tools/
│   └── make_release.py  # builds the code-only release zip + latest.json
└── data (outside the app folder)
    └── %APPDATA%\KonkurApp\   # state.json, testbook.json, keys & configs
```

One Python process serves the single-page app and a JSON API (`/api/state`, `/api/testbook`, `/api/boxes`, `/api/calendar/*`, `/api/gemini*`, `/api/backup/*`, `/api/update/*`). The frontend is plain HTML/CSS/JavaScript — no framework, no build step. Release zips contain code only; personal data never leaves the data directory.

---

## 🔒 Data & Privacy

**Your data stays yours.** Your study programme, test results, exam data and settings are stored only on your own computer — and, if you enable it, in your own private Backblaze B2 bucket for backup. Nothing is sent to the project author or to any third party. There is no analytics, no tracking and no advertising.

- **Gemini:** if you enter a Gemini API key, it is stored only on your own computer (the app never returns the full key to the browser) and used only to call Google's Gemini API on your behalf.
- **Google Calendar:** if you connect your Google account, the app accesses your calendar only to synchronise your study programme. Access happens only after you sign in with your own Google account (OAuth 2.0); access and refresh tokens are stored only on your own computer. You can disconnect at any time from the app's Backup tab, which revokes the access.
- **Backblaze B2:** if you enable cloud backup, your B2 credentials are stored server-side in the data directory — never shipped, never sent to the browser in full.

See [PRIVACY.md](https://github.com/ParhammPm/studyflow/blob/main/PRIVACY.md) for the full policy. No secrets, API keys or personal data are ever committed to this repository.

---

## 🗺️ Roadmap

### Completed

- **v1.5.0** — Gemini model picker; programme from 2 Aban; light theme; multi-select exam↔book linking; in-app updates with rollback.
- **v1.6.0** — Gemini model test panel; backlog cleanup rule.
- **v1.7.0** — History & Analytics: archive, charts, heatmap, per-subject dashboards, period comparison, smart reports, CSV + print/PDF export.
- **v1.8.0** — Google Calendar ICS pull; real study-time tracking (per-box timer, actual minutes).
- **v1.9.0** — Colour design system; 03:30 study-day boundary; book linking for assignments and boxes.
- **v1.10.0** — One-click auto-update from this repo's manifest; renamed to StudyFlow.
- **v1.11.0** — Two-way Google Calendar sync (OAuth 2.0, PKCE, Google-wins conflicts, internal box API).
- **v1.11.1** — Full-app audit fixes (data-loss and sync bugs).
- **v1.11.2–1.11.4** — Dashboard density for 1920×1080; one shared Jalali monthly calendar; OAuth connect and auto-update fixes.
- **v1.11.5** — Explicit "class" activity type for tasks, with a 5-way activity filter across History & Analytics.

### Planned

- **Screenshots of the current UI** for this README (`docs/screenshots/`).
- **Simpler two-way Google Calendar setup** — today it needs a Google Cloud OAuth client you create yourself (the sync code works; the setup is manual). Note: if the OAuth consent screen stays in Google's *Testing* mode, refresh tokens expire after 7 days and the app needs a weekly reconnect.

---

## ⚠️ Honest limitations

- The local version only works while the laptop is on and the server is running.
- Single-user, no login or accounts.
- Gemini analysis needs your own API key (from Google AI Studio).
- The cloud (Space) version is separate and not in this repo.

---

## 🤝 Contributing

Issues and feature requests are welcome.

1. Fork the repo.
2. Create a branch for your change.
3. Make your changes and test them locally (run the app, check the change in the browser).
4. Open a pull request describing what changed and why.

## Building a release (maintainers)

```bash
python3 tools/make_release.py --tree <app-folder> --out <output-folder>
```

Builds a code-only zip (`studyflow-v<VERSION>.zip`) and prints its SHA-256 and the `latest.json` manifest text. `data.json` (personal programme), `testbook.json`, `state.json` and data-directory files never go into the zip.

---

## License

MIT — see [LICENSE](https://github.com/ParhammPm/studyflow/blob/main/LICENSE). Copyright (c) 2026 ParhammPm.
