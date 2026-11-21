# Property Finance — website

Static website for the Property Finance Android app: home page, privacy
policy, terms of use and `app-ads.txt`. Plain HTML/CSS — no build step.

Published from this folder to
<https://github.com/Property-Finance-Manager/propertyfinance> (GitHub Pages).

## Publish with GitHub Pages

1. The repository must be **public** — GitHub Pages is not available for a
   private repository on a free plan.
2. Repository → **Settings → Pages**.
3. Source: **Deploy from a branch** → Branch **main**, folder **/ (root)** → Save.
4. After a minute the site is live. Paste the privacy-policy URL into
   Play Console → App content → Privacy policy.

### The repository name decides the URL — and whether AdMob can verify

| Repository name | Site URL | `app-ads.txt` found by AdMob? |
|---|---|---|
| `propertyfinance` | `https://property-finance-manager.github.io/propertyfinance/` | ❌ no — it is a sub-path |
| `property-finance-manager.github.io` | `https://property-finance-manager.github.io/` | ✅ yes |
| custom domain (e.g. `propertyfinance.app`) | `https://propertyfinance.app/` | ✅ yes |

AdMob only ever fetches `https://<domain>/app-ads.txt` at the **root** of the
domain, never a sub-path. So either

* rename the repository to **`property-finance-manager.github.io`** (Settings →
  General → Repository name) — nothing else changes, or
* add a custom domain (Settings → Pages → Custom domain) and a `CNAME` file.

Without one of those, this `app-ads.txt` is published but unverifiable and the
app gets limited ad serving.

## app-ads.txt

`app-ads.txt` holds the AdMob publisher ID **pub-2458076513370174**, which must
match AdMob → Settings → Account → Publisher ID. Two rules:

* the developer website on the Play store listing must be the **domain this
  file is served from**, and
* if the same domain also serves other Google ad products, list every line in
  the one file — one line per publisher ID, not one file per product.

Verify with AdMob → Apps → Property Finance → App settings → app-ads.txt.

## Before the app goes live on Play

Replace the two "Coming soon" blocks in `index.html` (hero button and the
`#download` section) with the real store link:
`https://play.google.com/store/apps/details?id=com.propertyfinance`

## Preview locally

```bash
python3 -m http.server 8650
```

Then open <http://localhost:8650>.
