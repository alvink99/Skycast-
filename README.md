# SkyCast — GitHub Pages

A single-page weather dashboard designed for a wide/landscape screen.

## Publish for free with GitHub Pages

1. Sign in to GitHub and create a **public** repository named `skycast`.
2. Upload `index.html` to the top level of the repository.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Choose branch `main` and folder `/(root)`, then Save.
6. Wait for GitHub Pages to publish. The site address will appear in the Pages section.

Official guide: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## Live data and important limitations

- Current conditions, hourly forecast, 10-day forecast, sunrise/sunset, geocoding and local time are loaded live from Open-Meteo.
- The Met Office warnings panel links to the official live warning page. It does **not** yet parse the Met Office NSWWS feed inside the page.
- Met Office's detailed site-specific forecast APIs require a subscription/API key. Never put a private API key in `index.html` or any public GitHub repository.
- Met Office documents a public UK warnings Atom feed, but a production integration should verify the exact feed endpoint, browser access/CORS, and geographic matching before showing an all-clear. Do not show “no warnings” unless the feed was successfully checked.
- Forecast data are not a substitute for official warnings or emergency advice.

## Privacy

This is a front-end demo, not a real account system. Names/usernames are used only in the browser session and are not transmitted or saved. The DOB field is only a demo form field and is not stored. Consider removing DOB collection entirely before sharing publicly, especially for a site used by children. Do not add passwords or collect personal information without proper security and privacy arrangements.

## Landscape

The layout is optimized for landscape. Phones may need to be rotated; small screens use a stacked layout so content remains readable.


## Improvements in this version
- Prevents older weather searches from overwriting newer results.
- Cancels superseded network requests and supports pressing Enter to search.
- Uses the searched location time zone to select the correct hourly forecast.
- Corrects the current precipitation unit label (millimetres, not percent).
- Caches forecast responses in memory for five minutes to reduce repeat loading.
