# InkFlow

**InkFlow** is a single-file finance dashboard that mixes budgeting controls, data visualization, and Supabase sync into one minimal page.

## Features
* **Date controls** – The year/month pickers automatically reload the selected snapshot, recalculating cards, fixed expenses, charts, and the calendar.
* **Cards** – Create a card with name, currency, due day, and whether it charges this or next month. The view shows logos (from `assets/`, via `renderExpenseName()`), debt/minimum chips with inline currency badges, and the due-cycle summary. Clicking ✎ opens inline inputs for editing the numeric values, day, and charge cycle.
* **Fixed expenses** – Track subscriptions, utilities, etc. by setting amount, currency, category, due day, and optional non-monthly frequency/month. Entries are grouped by category with the same currency chip styling plus logos where recognized.
* **Visualization** – `renderCharts()` produces per-currency bars for total debt vs. this-month payment, while `renderCalendar()` paints daily intensity and lets you tap any date to see per-currency totals plus item labels.
* **Cloud sync** – When `SUPABASE_URL`/`SUPABASE_ANON_KEY` are populated, the page reads/writes a `fin_snapshots` table via `loadFromSupabase()` and `saveToSupabase()`, storing both monthly snapshots (cards + fixed) and a global “year 0 / month all” record for shared data. Autosave debounces saves by 600ms.

## Layout notes
* The entire experience is self-contained in `index.html` (HTML + CSS + JS).
* Icons referenced in `renderExpenseName()` (Netflix, Apple One, YouTube Premium, Emirates Islamic/NBD, Tabby, Amex, Virgin, du, F1, Real Debrid) live under `assets/`.
* Currency badges now appear next to debt/minimum/amount chips for both cards and fixed rows to reinforce which totals use which money.

## Getting started
1. Open `index.html` in your browser or serve it from a static server.
2. If you want persistence, update the Supabase constants at the top of the file to match your project.
3. Add cards/fixed expenses via the drawers, use the edit toggle for inline adjustments, and watch the charts/calendar update instantly.
4. Click calendar cells to see the daily breakdown and which cards/expenses contribute.

## GitHub Pages
Publish from the `main` branch with the repository root as the Pages source. The site is then available at `https://<user>.github.io/finanzas/`.
