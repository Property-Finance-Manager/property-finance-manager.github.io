# Property Finance — website

Static website for the Property Finance Android app (home page, privacy
policy, terms of use). Plain HTML/CSS — no build step.

## Publish with GitHub Pages

1. Repository → **Settings → Pages**.
2. Source: **Deploy from a branch** → Branch **main**, folder **/ (root)** → Save.
3. After a minute the site is live at:
   - Home: `https://sabbir1107.github.io/property-finance/`
   - Privacy policy (paste into Play Console → App content → Privacy policy):
     `https://sabbir1107.github.io/property-finance/privacy-policy.html`
   - Terms: `https://sabbir1107.github.io/property-finance/terms.html`

## Before ads go live

- Update `privacy-policy.html` section 6 to say the app shows ads, and change
  the "Last updated" date.
- AdMob asks for an `app-ads.txt` on the developer website listed in Google
  Play. Add a file named `app-ads.txt` at the site root with the line AdMob
  gives you, e.g. `google.com, pub-XXXXXXXXXXXXXXXX, DIRECT, f08c47fec0942fa0`.
  (AdMob checks the root of a domain; a `github.io/<repo>/` sub-path may not
  verify. A custom domain or a `sabbir1107.github.io` user site fixes that.)
- When the app is on Google Play, replace the "Coming soon" button link in
  `index.html` with
  `https://play.google.com/store/apps/details?id=<your application id>`.

## Preview locally

```bash
python3 -m http.server 8650
```

Then open http://localhost:8650.
