# Homefin — Public information

The English/Swedish website for Homefin, a household finance app for iPhone and Mac. It follows the look and structure of Stjärnjakten’s website, with Homefin’s production artwork and teal accents. Plain HTML, shared CSS and a small language selector; no build step, external dependencies or analytics.

## Pages and languages

| Page | English | Swedish |
| --- | --- | --- |
| Home | `/en/` | `/sv/` |
| Privacy policy | `/en/privacy/` | `/sv/privacy/` |
| Support | `/en/support/` | `/sv/support/` |

The app’s `/privacy` and `/support` links resolve to directory entry pages. These, and `/`, select a language using an explicit `?lang=en` or `?lang=sv` value (also `#english` or `#svenska`), then a saved choice, then the browser language, with English as the fallback. Explicit `/en/` and `/sv/` pages always keep their language. The dropdown opens the same page in the other language and saves only that explicit choice in `homefin.language` in local storage. If storage is unavailable, navigation still works. Without JavaScript, ordinary links let visitors choose a language.

Each localized page has its own title, description, canonical URL and alternate-language metadata. Update English and Swedish together. Edit the HTML directly; keep this site free of framework and build requirements. Update availability text when Homefin launches and the privacy-policy date when its content changes.

`assets/app-icon.png` is copied unchanged from the production app artwork at `../homefin/Apps/Shared/Resources/AppIcon.icon/Assets/icon.png`. It supplies the header, home-page artwork, favicon and Apple touch icon. Keep the copy aligned with production artwork and do not use the Dev icon.

Support instructions and privacy text follow the app’s actual iCloud sharing, local storage, automatic and exported backups, App Lock, smart suggestions and app notices. Keep them aligned as the app changes. Contact is Stay Sweet at `info@staysweet.dev`.

## Local preview and verification

From this repository:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open `http://127.0.0.1:8000/`. Check all six localized pages at desktop and mobile widths, the language selector, browser Back, navigation and email destinations. Verify `/`, `/privacy/` and `/support/`, saved language choices, and the language links with JavaScript unavailable. Static sanity checks are `node --check language.js` and `git diff --check`.

## Git identity

The repository-local author and committer identity is:

```text
Stay Sweet <info@staysweet.dev>
```

For a fresh clone, configure it before committing:

```sh
git config --local user.name "Stay Sweet"
git config --local user.email "info@staysweet.dev"
```

This is commit metadata, not a change to repository ownership or a GitHub account. These settings apply only to this repository.

## GitHub Pages

The site is prepared for `stay-sweet/homefin-web` at `https://homefin.staysweet.dev`. Publish the `main` branch’s repository root using **Settings → Pages → Deploy from a branch**. `.nojekyll` keeps the site static, and `CNAME` contains the intended custom domain. Set `homefin.staysweet.dev` as the custom domain in Pages settings, then point the `homefin` DNS CNAME to `stay-sweet.github.io`. Retain the organization’s domain-verification record and enable HTTPS when available. See GitHub’s [publishing-source instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) and [custom-domain instructions](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).

Paths are root-relative for the custom domain. Use that domain or the local preview, rather than the unconfigured `/homefin-web/` project subpath. Repository files alone do not enable Pages or configure DNS. Publishing and domain setup are separate steps.

After publication, the language-specific metadata URLs are:

| Field | English | Swedish |
| --- | --- | --- |
| Privacy Policy URL | `https://homefin.staysweet.dev/en/privacy/` | `https://homefin.staysweet.dev/sv/privacy/` |
| Support URL | `https://homefin.staysweet.dev/en/support/` | `https://homefin.staysweet.dev/sv/support/` |
| Marketing URL | `https://homefin.staysweet.dev/en/` | `https://homefin.staysweet.dev/sv/` |

Existing in-app links to `/privacy` and `/support` continue to select the visitor’s language. App Store Connect metadata is managed separately.

## Project knowledge and work

North Production is the source of truth for current work, decisions and verification evidence: **Homefin (HOM)**, the StaySweet workspace (Project ID `6dc7aecd-aac9-4546-97ff-a18df20be2a7`). Read its Project context and [AGENTS.md](AGENTS.md) before starting. Existing technical references remain useful; keep new planning and status in North rather than parallel local files.
