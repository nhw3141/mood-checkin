# mood-checkin
# Mood Check-In (4-Hour Emotion Tracker)

A cute, friendly web app that helps you track how you feel throughout the day, without losing the “I was happy earlier” moments.

It prompts check-ins every **4 hours during your awake time only** (based on your sleep schedule), lets you pick an emotion (including **Neutral**), and saves a quick note so you can remember what happened later. All entries are stored with **real local date and time**.

## Features

- **4-hour check-ins (awake time only)**  
  Set your sleep start and sleep end. The app generates check-in slots only while you’re awake.

- **Emotion selection + notes**  
  Choose an emotion and optionally write notes about what happened.

- **Neutral option included**  
  For moments where nothing special is happening.

- **Real date/time stamping**  
  Every entry is saved with a real local timestamp and day grouping.

- **Color-based emotions**  
  Bright colors for positive feelings and darker tones for heavier moods.

- **Calendar review**
  Pick any date and review your emotions + notes for that day.

- **Insights (last 7 days)**
  Simple weekly visualization of average mood score per day.

- **One-year storage (IndexedDB)**
  Data is stored in your browser using IndexedDB, which can hold entries for a year or more.

- **Export for backup**
  Export your data as **JSON** or **CSV** anytime.

## How Scheduling Works

You set:
- **Sleep starts** (bedtime)
- **Sleep ends** (wake time)

The app considers everything outside your sleep window as awake time, then creates check-in slots every **4 hours**, anchored from the start of each awake interval.

Example:
- Sleep: **23:00 → 07:00**
- Awake: **07:00 → 23:00**
- Slots: **07:00, 11:00, 15:00, 19:00**

If you open the app during sleep time, it shows the **next check-in** after you wake up.

## Storage Notes (Important)

This app uses **IndexedDB**, so your data is saved **only in the browser/device you use**.

- Opening the site on a different browser/device will not show your old entries.
- Clearing browser data can remove your entries.

Recommended:
- Use **Export JSON** or **Export CSV** for backups.
- Upgrade to cloud sync later if you want multi-device support.

## Run Locally

1. Download/clone this repository
2. Open `index.html` in your browser

That’s it. No build tools needed.

## Deploy with GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Source: **Deploy from a branch**
4. Branch: **main**, Folder: **/ (root)**
5. Save

Your website will be available at:

`https://YOUR_USERNAME.github.io/REPO_NAME/`

## Cloud Sync Upgrade Path (Optional)

The UI and entry format are already designed for easy cloud sync later.

To upgrade:
1. Add user login (email/password or Google)
2. Replace the `DataStore` functions (IndexedDB) with Firebase/Supabase calls
3. Keep the same entry object format (timestamp, emotionKey, note, slotLabel)

## Tech Stack

- HTML
- CSS
- Vanilla JavaScript
- IndexedDB (local storage)

## License

MIT (or choose your preferred license)
