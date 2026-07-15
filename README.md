# Money Tracker — Living Expenses Ledger

A single-file, no-build web app for tracking recurring payments (e.g. living
expense transfers from parents) against a calendar. Add a payment once, mark
it received when it lands, and see at a glance what's outstanding for the
month.

**Deployment target:** GitHub Pages can publish this repository directly from `main`;
enable Pages in repository settings to create the public demo URL.

![No backend](https://img.shields.io/badge/backend-none-lightgrey)
![Storage](https://img.shields.io/badge/storage-localStorage-blue)

## Features

- **Calendar view** — each payment renders as a band across the days it
  covers. Amber = due now, faded green = upcoming, solid green = received.
- **Payment list** — searchable table with status toggle, quick "repeat"
  (adds the next payment of the same length right after the last one), and
  delete.
- **Monthly summary** — received / added / still-to-receive totals for the
  month in view.
- **CSV export** for spreadsheets or record-keeping.
- **Backup / restore** to a local JSON file.

## Running it

There's nothing to install or build. Download `index.html` and open it in
any modern browser:

```bash
git clone https://github.com/SXT2918/money-tracker.git
cd money-tracker
open index.html   # or just double-click the file
```

You can also serve it with any static file server if you prefer, e.g.
`python -m http.server`.

## Privacy — your data stays on your device

This app has **no backend and makes no network requests**. All payment data
is written to your browser's `localStorage` and never leaves your machine.
Nothing is uploaded, synced, or sent anywhere — including to this
repository. Clearing your browser's site data for this page will erase your
records, so use **Back up** periodically if you want a portable copy.

Because storage is per-browser-profile, data doesn't automatically follow
you between devices or browsers — use **Back up** / **Restore** to move it.

## Tech

Plain HTML, CSS, and vanilla JavaScript — no frameworks, no dependencies,
no build step.

## Data format and limitations

Backups use a versioned JSON envelope and restored records are schema-validated. The app
does not sync across devices, recover cleared browser storage, or provide multi-user
access. See [SECURITY.md](SECURITY.md) for safe backup handling.

## License

MIT — see [LICENSE](LICENSE).
