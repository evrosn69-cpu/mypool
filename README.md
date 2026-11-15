# My Pool

A pool chemistry tracker that installs on your phone's home screen. It is free, needs no developer account, and works offline. All data stays on the phone.

## What it does

- **Today**: pool picture, next check date, chlorine and pH with gauges, what to add (dose worked out from your pool volume and product strength), monthly full test, "rain or heavy use" extra check.
- **Log a test**: type the reading or tap the colour that matches your kit; optional full test; record chemicals added (updates stock and charts).
- **Pool**: plan drawing, volume, surface type, target ranges, dimensions with steps, chemicals, equipment.
- **Reminders**: check schedule for summer (salt) and winter (chlorine), calendar export, maintenance tasks with how-to steps.
- **History**: charts with the target band and marks where a product was added.
- **Seasons**: set the start dates for summer and winter in Pool; the app switches mode by itself on those dates (you can still switch by hand on Today).
- **Backup**: export and restore everything as one file (Pool > Equipment).

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

## Data

Stored in the browser on that phone only. Deleting the app or clearing Safari/Chrome website data deletes it, so use **Export to a file** now and then.
