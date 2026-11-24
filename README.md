# StudyFlow

برنامه‌ریز مطالعه‌ی لوکال و تک‌کاربره برای کنکور — برنامه‌ی روزانه، کتاب تست، آزمون‌های آزمایشی، تحلیل عملکرد و به‌روزرسانی یک‌کلیکی. بدون حساب کاربری، بدون سرور ابری؛ داده‌ها روی لپ‌تاپ خودت می‌مانند.

> **English version below.**

## امکانات

- **داشبورد:** فقط «امروز» — باکس‌های روز مطالعاتی (روز مطالعاتی از ۰۳:۳۰ بامداد شروع می‌شود)، تست‌های امروز و عقب‌افتادگی‌ها.
- **برنامه:** تقویم جلالی ماهانه، باکس‌های مطالعاتی با تیک انجام‌شده، ساعت، تعداد تست (انجام‌شده/درست) و دقت خودکار؛ ویرایش کامل هر باکس.
- **تکالیف:** همان کار تست‌زنی باکس‌ها از زاویه‌ی دیگر — بدون ذخیره‌ی تکراری.
- **کتاب تست:** کتاب‌های تست با فهرست واقعی فصل‌ها و بخش‌ها؛ وضعیت مطالعه، سطح تسلط، یادداشت و ورود تست (درست/غلط/بی‌پاسخ) برای هر بخش.
- **آزمون‌ها:** آزمون‌های آزمایشی (ماز، زودبیست، امتحانات مدرسه) با بودجه‌بندی ساخت‌یافته، زیرمبحث‌ها، نتیجه (تراز، رتبه، درست/غلط/بی‌پاسخ) و شاخص پیشرفت هر مبحث.
- **اتصال دستی به کتاب:** هر مبحث آزمون، تکلیف یا باکس برنامه را می‌شود به بخش‌های کتاب وصل کرد (چندانتخابی)؛ در صفحه‌ی کتاب، لینک‌های معکوس نشان داده می‌شوند. هیچ اتصالی خودکار ساخته نمی‌شود.
- **تاریخچه و تحلیل عملکرد:** آرشیو باکس‌ها به تفکیک ماه با جست‌وجو، نمودارهای روند و مقایسه‌ی دروس، تقویم فعالیت (هیت‌مپ)، تحلیل هر درس، فیلترهای مشترک، مقایسه‌ی دو بازه، گزارش هوشمند از روی داده‌ی واقعی و خروجی CSV و PDF.
- **تایمر مطالعه‌ی واقعی:** تایمر روی هر باکس (شروع/توقف/ادامه) + ورود دستی «دقیقه واقعی»؛ ساعت واقعی کنار ساعت برنامه‌ریزی‌شده نشان داده می‌شود، نه به‌جای آن.
- **همگام‌سازی تقویم گوگل (فقط خواندن):** آدرس خصوصی ICS تقویم را یک‌بار وارد کن؛ برنامه خودش تغییرها را می‌گیرد (باکس جدید، جابه‌جا‌شده، لغوشده). تیک‌ها و تست‌ها دست نمی‌خورند و باکسی که خودت حذف کرده‌ای برنمی‌گردد. وارد کردن دستی فایل `.ics` یا JSON هم هست (با پیش‌نمایش و تایید).
- **Gemini:** تحلیل پیشرفت با کلید API خودت + پنل تست مدل‌ها (کدام مدل‌ها با کلیدت واقعاً کار می‌کنند، با زمان پاسخ و نوع خطا).
- **بکاپ خودکار:** نسخه‌های لوکال (۳۰ نسخه‌ی اخیر هر فایل) + بکاپ ابری Backblaze B2 (۱۰ گیگابایت رایگان، بدون کارت) با بازگردانی نسخه‌ها.
- **به‌روزرسانی یک‌کلیکی:** از تب «پشتیبان»، بخش «به‌روزرسانی خودکار» — دکمه‌ی «بررسی به‌روزرسانی» مانیفست `latest.json` همین ریپو را می‌خواند؛ اگر نسخه‌ی جدیدتر بود، دکمه‌ی «دانلود و نصب» آن را دانلود و نصب می‌کند (هش SHA-256 بررسی می‌شود؛ نصب همیشه با کلیک و تایید تو انجام می‌شود، هیچ‌وقت خودکار نیست). نصب دستی با فایل zip یا لینک هم هست.
- **دو زبانه (فارسی/انگلیسی)، راست‌به‌چپ، تم روشن و تیره** با یک سیستم رنگی کامل (Design Tokens)؛ رنگ هر درس و هر دسته در همه‌ی صفحات و نمودارها ثابت است.

## نصب (ویندوز)

1. آخرین نسخه را از بخش [Releases](../../releases) دانلود کن (`studyflow-vX.Y.Z.zip`) و بازش کن.
2. روی `start.bat` دابل‌کلیک کن — مرورگر با آدرس `http://localhost:8765` باز می‌شود.
3. برای خاموش کردن، پنجره‌ی سرور را ببند.

نیازها: **Python 3** (از python.org؛ هنگام نصب تیک **Add Python to PATH** را بزن). هیچ نصب دیگری لازم نیست — سرور فقط از کتابخانه‌ی استاندارد پایتون استفاده می‌کند.

برنامه با **برنامه‌ی خالی** می‌آید. برای پر کردنش: در تب «پشتیبان»، بخش «همگام‌سازی تقویم گوگل»، آدرس خصوصی ICS تقویمت را وارد کن (Google Calendar → Settings → تقویم → Secret address in iCal format) یا یک فایل خروجی `.ics`/JSON تقویم را دستی وارد کن؛ یا از تب «تکالیف» تکلیف بساز (ساختن تکلیف، باکس برنامه را هم می‌سازد).

## داده‌ها کجا می‌روند؟

همه‌ی داده‌ها (تیک‌ها، تست‌ها، کتاب‌ها، آزمون‌ها، کلید جمینای، تنظیمات بکاپ) بیرون از پوشه‌ی برنامه ذخیره می‌شوند:

- ویندوز: `%APPDATA%\KonkurApp\` (یعنی `C:\Users\<نام کاربری>\AppData\Roaming\KonkurApp\`)

پس جایگزین کردن پوشه‌ی برنامه با نسخه‌ی جدید هیچ‌وقت به داده‌ها دست نمی‌زند، و **به‌روزرسانی فقط کد برنامه را جایگزین می‌کند**. نسخه‌های انتشار (`releases/`) فقط کد هستند و هیچ داده‌ی شخصی‌ای در آن‌ها نیست.

## محدودیت‌های صادقانه

- نسخه‌ی لوکال فقط وقتی کار می‌کند که لپ‌تاپ روشن و سرور در حال اجراست.
- همگام‌سازی با تقویم گوگل **یک‌طرفه** است (فقط خواندن): تغییرهای این برنامه به تقویم گوگل برنمی‌گردد؛ برای دوطرفه به OAuth Clientای نیاز است که خودت در Google Cloud بسازی.
- نسخه‌ی لوکال **تک‌کاربره** است و ورود/حساب کاربری ندارد.
- تحلیل با Gemini به کلید API خودت نیاز دارد (از Google AI Studio بگیر).
- نسخه‌ی ابری (Space) جداگانه است و در این ریپو نیست.

## ساخت نسخه‌ی انتشار

```bash
python3 tools/make_release.py --tree <پوشه‌ی برنامه> --out <پوشه‌ی خروجی>
```

یک zip فقط-کد می‌سازد (`studyflow-v<VERSION>.zip`) و هش SHA-256 و متن `latest.json` را چاپ می‌کند. فایل‌های `data.json` (برنامه‌ی شخصی)، `testbook.json`، `state.json` و فایل‌های پوشه‌ی داده‌ها هیچ‌وقت وارد zip نمی‌شوند.

## لایسنس

MIT — فایل [LICENSE](LICENSE) را ببین.

---

# StudyFlow (English)

A local, single-user study planner for Konkur (the Iranian university entrance exam): daily programme, test books, mock exams, performance analytics, and one-click self-updates. No accounts, no cloud server — your data stays on your own laptop.

## Features

- **Dashboard:** today only — boxes of the study day (a study day starts at 03:30 AM), today's tests, and overdue items.
- **Programme:** Jalali monthly calendar; study boxes with done tick, time, test counts (done/correct) and automatic accuracy; full box editing.
- **Assignments:** the same test work as the programme boxes, seen from another angle — never stored twice.
- **Test books:** real chapter/section tables of contents; per-section study status, mastery, notes, and test entry (correct/wrong/unanswered).
- **Exams:** mock exams (Maz, Zoodbist, school exams) with structured budgets, subtopics, results (score, rank, correct/wrong/unanswered) and a progress indicator per topic.
- **Manual book linking:** link any exam topic, assignment, or programme box to book sections (multi-select); each book section shows its reverse links. Nothing is linked automatically.
- **History & performance analytics:** monthly box archive with search, trend and subject-comparison charts, activity heatmap, per-subject analysis, shared filters, two-period comparison, smart reports from real data only, CSV and PDF export.
- **Real study timer:** per-box timer (start/pause/resume) + manual "actual minutes" entry; actual time is shown next to scheduled time, never instead of it.
- **Google Calendar sync (read-only):** paste your calendar's private ICS address once; the app pulls changes (new/moved/cancelled boxes). Ticks and tests are never touched, and boxes you deleted stay deleted. Manual `.ics`/JSON file import (with preview + confirm) is also available.
- **Gemini:** progress analysis with your own API key + a model test panel (which models actually work with your key, with latency and error kind).
- **Automatic backup:** local versioned backups (last 30 versions per file) + Backblaze B2 cloud backup (10 GB free, no card) with version restore.
- **One-click updates:** in the Backup tab, "Automatic updates" — "Check for updates" reads this repo's `latest.json` manifest; if a newer version exists, "Download and install" downloads and installs it (SHA-256 verified; installing always needs your click and confirmation, never automatic). Manual install from a zip file or link is also available.
- **Bilingual (Persian/English), RTL, light and dark themes** with a complete colour Design System; each subject and category keeps one fixed colour across all pages and charts.

## Install (Windows)

1. Download the latest release from [Releases](../../releases) (`studyflow-vX.Y.Z.zip`) and extract it.
2. Double-click `start.bat` — the browser opens at `http://localhost:8765`.
3. To stop it, close the server window.

Requirements: **Python 3** (from python.org; tick **Add Python to PATH** during install). Nothing else — the server uses only the Python standard library.

The app ships with an **empty programme**. To fill it: in the Backup tab, "Google Calendar sync", paste your calendar's private ICS address (Google Calendar → Settings → calendar → Secret address in iCal format) or manually import an `.ics`/JSON calendar export; or create assignments from the Assignments tab (creating an assignment also creates a programme box).

## Where does the data go?

All data (ticks, tests, books, exams, Gemini key, backup settings) lives outside the app folder:

- Windows: `%APPDATA%\KonkurApp\` (i.e. `C:\Users\<username>\AppData\Roaming\KonkurApp\`)

So replacing the app folder with a new version never touches your data, and **an update only replaces the app's code**. Release zips (`releases/`) are code-only and contain no personal data.

## Honest limitations

- The local version only works while the laptop is on and the server is running.
- Google Calendar sync is **one-way** (read-only): changes in this app never go back to Google Calendar; two-way sync needs an OAuth Client you create yourself in Google Cloud.
- The local version is **single-user** and has no login/accounts.
- Gemini analysis needs your own API key (from Google AI Studio).
- The cloud (Space) version is separate and not in this repo.

## Building a release

```bash
python3 tools/make_release.py --tree <app-folder> --out <output-folder>
```

Builds a code-only zip (`studyflow-v<VERSION>.zip`) and prints its SHA-256 and the `latest.json` text. `data.json` (personal programme), `testbook.json`, `state.json`, and data-dir files never go into the zip.

## License

MIT — see [LICENSE](LICENSE).
