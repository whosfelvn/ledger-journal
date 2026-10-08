# Ledger trading journal

A private futures trading journal that runs entirely in your browser. No server, no account, no sample data.

## Run it

**Option A: GitHub Pages (easiest, works on any device)**
1. Create a new repo and upload `index.html` and this README.
2. Repo → Settings → Pages → Source: `Deploy from a branch`, branch `main`, folder `/root`.
3. Open the URL GitHub gives you.

The code is public if the repo is public. Your trades are not: they live in your browser's storage on each device, never on GitHub.

**Option B: fully local**
- Double-click `index.html` (works in Chrome, Edge, Firefox), or
- In the folder run `python3 -m http.server 8000` and open `http://localhost:8000`.

Pick one address and stick with it. Data is saved per address, so `localhost:8000` and your GitHub Pages URL are two separate journals.

## Install as an app
Upload **all** the files (including the `icons` folder, `manifest.webmanifest` and `sw.js`) to GitHub, turn on Pages, then open your Pages link in Chrome or Edge and click **Install app** (sidebar) or the install icon in the address bar. It gets its own window, a dock/taskbar icon, and works offline.

iPhone/iPad: open the link in Safari → Share → Add to Home Screen.

Installing needs a web address (GitHub Pages or `http://localhost:8000`). Double-clicking `index.html` still works but can't be installed.

After uploading a new `index.html`, also change `VERSION` in `sw.js` (e.g. `ledger-v2`) so installed copies pick up the update.

**Your data is tied to the address.** The installed app shares data with the same address in the browser. If you've been using a different address (e.g. a local file), download a backup there first and restore it in the app, or connect the same auto-save folder.

## First 5 minutes
1. **Settings → Futures contracts / CFD symbols**: tap NQ, MNQ, NAS100, XAUUSD etc. Set your commission. For CFDs, check the contract size against MT5 (right-click symbol → Specification).
2. **Settings → Prop accounts** (optional): start balance, daily loss limit, max drawdown, target.
3. **Import**: drop your broker CSV. Map columns once; it's remembered for that export format.
4. Or log trades on the **Trades** page. Enter saves, and the contract/side/size stay filled.

Screenshots: paste with Ctrl/Cmd+V on a trade, on a journal day, or anywhere in the app.

## Discipline score and ranks
Each trading day gets a 0–100 score for process, not profit: entries in your kill zones, respecting your max daily loss, trade count, size, mistake tags, journaling and your rules. Streaks, ranks and achievements are all built from that score, so profit never earns points. Set your max trades and max daily loss in Settings → Discipline score, and tick which sessions count as kill zones.

## Keep your data safe
**Keep your journal on this computer (Chrome or Edge).** On first open, click **Create journal folder** and pick a location (Documents is fine). Ledger makes a `Ledger Journal` folder there. Pick a spot inside Google Drive, OneDrive, iCloud Drive or Dropbox to also get a cloud copy. Every change writes:
- `ledger-data.json` (trades, journal, settings)
- `images/` (screenshots)
- `daily-backups/ledger-YYYY-MM-DD.json` (one per day, last 30 kept)

If the browser asks for permission again after a restart, click **Reconnect** and choose **Allow on every visit** if offered.

If the folder has newer data than the browser (e.g. you used another computer), Ledger stops and asks before writing anything.

New computer or browser: open the journal, choose the same folder, pick **Load the folder's journal**.

Undo a bad day: Settings → Restore from backup → pick a file from `daily-backups`. Screenshots already in the browser are kept.

**Manual backup (any browser).** Settings → Download backup saves one JSON file with everything, screenshots included.

## Supported imports
Futures: Tradovate performance report, NinjaTrader trade export, TopstepX/ProjectX trade export.
CFDs: MT5 history report saved as HTML (Toolbox → History → right-click → Report → HTML). MT5 uses broker server time, so use "Shift times by" on the import page to line sessions up with UK time.
Any CSV with a date, instrument and either prices or P&L also works. Unsure? Download the blank template from the Import page.
