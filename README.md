# Owner Web Page – Hosting & Use

Files (keep all 4 together):

| File | Purpose |
|---|---|
| `index.html` | The whole web page (billing + settings + Bluetooth) |
| `manifest.webmanifest` | Lets the owner "Add to Home screen" like an app |
| `sw.js` | Makes the page work offline after the first visit |
| `icon.svg` | Home-screen icon |

Web Bluetooth only works on **https://** pages, so host the files on GitHub Pages (free).

## 1. Put it on GitHub Pages (one time, ~5 minutes)

1. Sign in at https://github.com (create a free account yourself).
2. Click **+ → New repository**. Name it `upi-display`, choose **Public**, then **Create repository**.
3. Click **uploading an existing file**, drag in the 4 files above, then **Commit changes**.
4. Open **Settings → Pages**. Under *Branch*, choose **main** and **/ (root)**, then **Save**.
5. After 1–2 minutes your page is live at:
   `https://<your-github-username>.github.io/upi-display/`

To update later: upload the changed file again. If you changed `index.html`, also change `CACHE = 'upi-display-v1'` to `v2` in `sw.js`, so phones get the new version.

## 2. Owner's phone (Android + Chrome)

1. Turn on **Bluetooth** and **Location** (Android needs Location for Bluetooth scanning).
2. Open the link in **Chrome**.
3. Chrome menu **⋮ → Add to Home screen** gives an app icon.
4. **First time:** hold **BOOT** on the display for 3 s, tap **Connect**, choose **UPI-QR-xxxx**, then type the 6-digit code shown on the display.
5. Go to **Settings**, create your **admin PIN**, then set your UPI ID, name and texts.
6. **Daily:** open the icon, tap **Connect**, type the amount, then tap **Show on display**.

Works on: Chrome / Edge / Samsung Internet on Android, and Chrome / Edge on Windows and Mac.
Does **not** work on: iPhone (Safari) or Firefox.

## 3. Troubleshooting

| Problem | Fix |
|---|---|
| Display not in the Connect list | Bluetooth + Location on? Display powered? Is another phone already connected? (Only one at a time.) |
| "Pairing failed" | Hold BOOT 3 s on the display first, then connect within 60 s. |
| Connects, then drops after ~10 s | This phone isn't paired. Hold BOOT 3 s and connect again. |
| Worked before, fails after factory reset / "Remove all paired phones" | Android Settings → Bluetooth → UPI-QR-xxxx → **Forget**, then pair again. |
| "Settings are locked" | Enter the admin PIN. It locks again after 10 min without use. |
| "LOCKED 600s" | 5 wrong PINs. Wait 10 minutes. |
