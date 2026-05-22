# SPSMUN 3.0 · Delegate QR System

Two files. No backend. No database. Fully static — works on GitHub Pages.

---

## Files
- `index.html` — HOD Dashboard (admin use only)
- `delegate.html` — Delegate personal page (linked from QR codes)

---

## Deploy to GitHub Pages (5 minutes)

1. Create a new GitHub repo named `spsmun` (must be public)
2. Upload both files (`index.html` and `delegate.html`) to the repo root
3. Go to **Settings → Pages → Source → Deploy from branch → main → / (root)**
4. Your site is live at: `https://YOUR_USERNAME.github.io/spsmun`

---

## Set the Base URL in the Dashboard

1. Open `https://YOUR_USERNAME.github.io/spsmun`
2. Click **✎ Change** next to the BASE URL in the top-right
3. Enter: `https://YOUR_USERNAME.github.io/spsmun`
4. It saves automatically in browser storage

All QR codes will now point to the correct delegate URLs.

---

## How QR Security Works

Each delegate URL looks like:
```
https://YOUR_USERNAME.github.io/spsmun/delegate.html?id=001&t=3GH7F2A
```

The `t=` token is a hash of `SPSMUN3-HOD-2025` + the delegate ID.
- Nobody can guess another person's token without knowing the secret
- No backend required — verification happens in the browser
- Changing the secret in the code invalidates all old QRs

---

## Printing QR Cards

1. Open the HOD dashboard
2. Click **Select All** (or select specific delegates)
3. Click **🖨 Print QR Cards**
4. Set print layout to **2 columns** for best results
5. Cut and attach to the back of each ID card

---

## To Update Delegate Data

Edit the `DELEGATES` array in **both** `index.html` and `delegate.html`.
Both files must have identical data.
