# My Pool

A pool chemistry tracker that installs on your phone's home screen. It is free, needs no developer account, and works offline. All data stays on the phone.

## What it does

- **Today**: the top stays fixed while you scroll: title, settings menu, and the animated pool picture with your skimmers and jets. A badge on the picture says "All good" or how many things need doing, and the water turns greenish when chlorine or pH is off. Below: chlorine and pH tiles with a + for quick entry, "What to add" with the dose and an Added button for chlorine and pH (after Added the water in the picture goes back to blue until the next reading is out of range), the filter pressure gauge with + and a Backwash timer button (green, orange or red by state, like the Cleaned today button), and a Pool cleaning card with "Cleaned today" (robot and skimmer baskets).
- **Log a test** (button on Today): type the reading or tap the colour that matches your kit; optional full test; record chemicals added (updates stock and charts).
- **Filter pressure**: a gauge on Today drawn like the real one (psi 0 to 40, blue FILTER and red CLEAN zones). Type the reading in Log a test. Clean pressure is 13 psi and the app asks for a backwash at 18 psi; both can be changed in Equipment, where you can also switch to bar.
- **Maintenance**: tasks with icons and due rings, step-by-step guide with timers (backwash 2 min and 30 s), pressure reading at the end of a backwash.
- **History**: charts with the target band and marks where a product was added.
- **Pool**: plan drawing (drag the skimmers and jets), volume, surface type, season dates, target ranges.
- **Reminders**: check schedule for summer (salt) and winter (chlorine), calendar export.
- **Settings menu** (top right on every screen): What I test, My chemicals, Equipment and backup, Pool dimensions.
- **Seasons**: set the start dates for summer and winter in Pool; the app switches mode by itself on those dates (you can still switch by hand on Today).

## Put it online with GitHub Pages (free)

1. On github.com create a new **public** repository, for example `mypool`.
2. Upload every file from this folder (`index.html`, `manifest.webmanifest`, `sw.js` and the three `icon-...png` files). There are no folders.
3. In the repository open **Settings > Pages**. Under "Build and deployment" choose **Deploy from a branch**, branch **main**, folder **/ (root)**, then Save.
4. After a minute the app is at `https://YOUR-USERNAME.github.io/mypool/`.

## Install on the phone

- **iPhone**: open the link in **Safari**, tap Share, then **Add to Home Screen**.
- **Android**: open the link in **Chrome**, tap the menu, then **Install app** (or Add to Home screen).

Open it from the new icon. It then works without internet.

## Reminders

A free web app cannot send scheduled notifications by itself on iPhone. In **Reminders** tap **Add to phone Calendar**: this creates repeating calendar events with alerts for the water check, the monthly full test and each maintenance task that is switched on. If you change the schedule or the season, add again and delete the old events in the Calendar app.

## Updating the app

Upload the new files to the same repository, replacing the old ones. The phone picks up the new version the next time the app is opened with internet (close and reopen it once). Your data is not touched.

## Notes on the numbers

- Chlorine dose: grams = (target − reading) × volume in m³ × 100 ÷ active chlorine %. The target is the middle of your range.
- Dichlor adds about 0.9 ppm stabiliser for each 1 ppm chlorine; the app keeps an estimate from the chemicals you log and resets it whenever you log a real stabiliser test.
- The pH minus amount is a rule of thumb only. Follow your product label.
- All pool sizes are entered in centimetres. Volume = length × width × water depth, minus the steps. Water depth is measured from the floor to the water surface; leave it empty if the water is at the top edge. Steps are listed from the top one down; each step's Height is how tall that step is by itself. Only the part of a step that is under water is subtracted.

## Sync between devices (optional, free)

The app can keep a copy of your data in a second, private GitHub repository. Every device that is connected shows the same data, and nothing is lost if a phone is replaced.

1. On github.com create a new repository named `mypool-data`. Set it to **Private** and tick "Add a README file".
2. Open github.com/settings/personal-access-tokens and choose **Generate new token** (fine-grained).
3. Token name: `My Pool`. Expiration: the longest offered (up to one year).
4. Repository access: **Only select repositories**, then pick `mypool-data`.
5. Permissions: Repository permissions > **Contents: Read and write**. Leave the rest alone. Generate and copy the token (it starts with `github_pat_`). Keep a copy somewhere safe; GitHub shows it only once.
6. In the app: settings menu (top right) > Equipment and backup > **Sync with GitHub**. Type your GitHub username, `mypool-data`, paste the token, tap **Connect**.
7. On a second device do step 6 with the same token and choose **Use the GitHub data on this device**.

When the token expires, make a new one the same way and paste it in after tapping Disconnect.

If two devices change something at the same moment, the later change wins.

## Data

Stored in the browser on that phone only. Deleting the app or clearing Safari/Chrome website data deletes it, so use **Export to a file** now and then.

## Push notifications (optional, free)

Needs GitHub sync to be on. One-time setup:

1. In your private data repository (mypool-data) create the file `.github/workflows/notify.yml` with the content of the notify.yml that came with this build.
2. On the phone, open My Pool from the Home Screen icon, go to Reminders and tap "Turn on notifications".
3. To test, open the Actions tab of the data repository, choose "Pool notifications" and press "Run workflow".

GitHub then checks every day around 8:30 and 17:30 (Cyprus time) and sends a notification only when something is due. The app saves a list of due items inside mypool.json, and a file push.json with the phone's push address and the sending key, both in your private repository.
