# ScopeWeaver Mail — OAuth branding site

Static site used as the **Homepage URL** and **Privacy Policy URL** for the
Google OAuth app `ScopeWeaver Mail` (formerly `ScopeWeaver Gmail`).

## Files

| file | purpose |
|---|---|
| `index.html` | Homepage URL — what the app is and does |
| `privacy.html` | Privacy Policy URL — Google API Limited Use disclosure |
| `terms.html` | Terms of Use |
| `404.html` | Not-found page |
| `style.css` | Shared stylesheet (auto light/dark) |
| `.nojekyll` | Stops GitHub Pages from running Jekyll |

## Publish steps

1. Create a **public** GitHub repo named `scopeweaver-mail`.
2. Push these files to the repo root (commands below).
3. Settings → Pages → Source: *Deploy from a branch* → Branch `main`, folder `/ (root)` → Save.
4. Wait ~1 min. Site appears at `https://<username>.github.io/scopeweaver-mail/`.

```bash
cd site
git init -b main
git add -A
git commit -m "ScopeWeaver Mail OAuth branding site"
git remote add origin git@github.com:<username>/scopeweaver-mail.git
git push -u origin main
```

## Then, in Google Cloud Console

5. **Search Console** (search.google.com/search-console) → add property →
   *URL prefix* `https://<username>.github.io/` → verify by **HTML file**
   (download `googleXXXX.html`, drop it in this `site/` folder, commit, push).
6. **Auth Platform → Branding**: App name `ScopeWeaver Mail`, homepage
   `https://<username>.github.io/scopeweaver-mail/`, privacy policy
   `https://<username>.github.io/scopeweaver-mail/privacy.html`,
   authorized domain `<username>.github.io`.
7. **Auth Platform → Audience → Publish app**.

> Why the rename: Google's OAuth branding policy prohibits app names that
> contain Google trademarks such as "Gmail". A name containing "Gmail" fails
> validation, which greys out **Save** with no error message.
