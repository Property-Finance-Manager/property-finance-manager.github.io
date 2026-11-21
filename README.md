# Property Finance — website

Static website for the Property Finance Android app: home page, privacy
policy, terms of use and `app-ads.txt`. Plain HTML/CSS — no build step.

**Live at <https://property-finance-manager.github.io/>** via GitHub Pages
(Settings → Pages → Deploy from a branch → `main` / `/ (root)`). Every push to
`main` redeploys it.

| Page | URL |
|---|---|
| Home | <https://property-finance-manager.github.io/> |
| Privacy policy | <https://property-finance-manager.github.io/privacy-policy.html> |
| Terms of use | <https://property-finance-manager.github.io/terms.html> |
| app-ads.txt | <https://property-finance-manager.github.io/app-ads.txt> |

## Why the repository is named `property-finance-manager.github.io`

AdMob only ever fetches `https://<domain>/app-ads.txt` at the **root** of the
domain, never a sub-path. A repository named `propertyfinance` would publish to
`property-finance-manager.github.io/propertyfinance/`, where AdMob would never
find the file. Naming the repository after the organisation makes it the
organisation's GitHub Pages site, served at the domain root.

Renaming the repository, or adding a custom domain, would move `app-ads.txt`
again — re-check it in AdMob afterwards.

## app-ads.txt

Holds the AdMob publisher ID **pub-2458076513370174**, which must match
AdMob → Settings → Account → Publisher ID. Two rules:

* the developer website on the Play store listing must be
  **property-finance-manager.github.io**, the domain this file is served from, and
* if this domain ever serves other Google ad products too, add one line per
  publisher ID to this same file — never a second file.

Verify in AdMob → Apps → Property Finance → App settings → app-ads.txt.

## Before the app goes live on Play

Replace the two "Coming soon" blocks in `index.html` (the hero button and the
`#download` section) with the real store link:
`https://play.google.com/store/apps/details?id=com.propertyfinance`

## Preview locally

```bash
python3 -m http.server 8650
```

Then open <http://localhost:8650>.
