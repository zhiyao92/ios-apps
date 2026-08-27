<h2 align="center">Kelvin Tan — iOS Apps</h2>
<p align="center">
  Software engineer since 2016. 25 apps shipped, 9 still live.<br>
  <strong><a href="https://zhiyao92.github.io/ios-apps/">zhiyao92.github.io/ios-apps</a></strong>
</p>
<p align="center">
  <a href="https://apps.apple.com/us/developer/zhi-yao-tan/id1161829106"><img src="https://img.shields.io/static/v1?label=AppStore&message=Zhi Yao%20Tan&color=red&style=for-the-badge&logo=apple&logoColor=white"></a>&nbsp;
  <a href="https://www.linkedin.com/in/kelvin-tan-31119133/"><img src="https://img.shields.io/static/v1?label=LinkedIn&message=Kelvin Tan&color=blue&style=for-the-badge&logo=linkedin&logoColor=white"></a>&nbsp;
  <a href="https://medium.com/@kelvintanzy"><img src="https://img.shields.io/static/v1?label=Medium&message=Kelvin Tan&color=white&style=for-the-badge&logo=medium&logoColor=white"></a>
</p>

---

This repository hosts the public site for my apps — the landing page, the shared
legal documents, and the contact form.

| Page | URL |
|---|---|
| Landing page | [zhiyao92.github.io/ios-apps](https://zhiyao92.github.io/ios-apps/) |
| Privacy Policy | [privacy-policy.html](https://zhiyao92.github.io/ios-apps/privacy-policy.html) |
| Terms of Service | [terms-and-condition.html](https://zhiyao92.github.io/ios-apps/terms-and-condition.html) |
| Contact | [contact-us.html](https://zhiyao92.github.io/ios-apps/contact-us.html) |

The Privacy Policy and Terms are **portfolio-wide** — they apply to every app I
publish, current and future, so every App Store listing can point at the same
two URLs.

## Apps

Nine live, listed newest-first — the same order the landing page uses.

| App | App Store | Landing page |
|---|---|---|
| Bondify: The Couples Edition | [Open](https://apps.apple.com/us/app/bondify-the-couples-edition/id6761910667) | [bondify-landing](https://zhiyao92.github.io/bondify-landing/) |
| DishSpin: What to Eat Wheel | [Open](https://apps.apple.com/us/app/dishspin/id6760835509) | [dishspin-landing](https://zhiyao92.github.io/dishspin-landing/) |
| Beam: Learn Thai & Speak It | [Open](https://apps.apple.com/us/app/beam-learn-thai-speak-it/id6480093061) | [beam-landing](https://zhiyao92.github.io/beam-landing/) |
| Provision | [Open](https://apps.apple.com/us/app/provision/id1538554089) | [provision-landing](https://zhiyao92.github.io/provision-landing/) |
| InstantMessage: No-Save Chat | [Open](https://apps.apple.com/us/app/instantmessage-no-save-chat/id1540915370) | [quickapp-landing](https://zhiyao92.github.io/quickapp-landing/) |
| LDS Quotes: Daily Inspiration | [Open](https://apps.apple.com/us/app/lds-quotes-daily-inspiration/id1506121689) | [lds-quotes-landing](https://zhiyao92.github.io/lds-quotes-landing/) |
| Malaysia Pocket | [Open](https://apps.apple.com/us/app/malaysia-pocket/id1504421248) | [malaysia-pocket-landing](https://zhiyao92.github.io/malaysia-pocket-landing/) |
| LDS Priesthood: Ordinances | [Open](https://apps.apple.com/us/app/lds-priesthood-ordinances/id1502509285) | [lds-priesthood-landing](https://zhiyao92.github.io/lds-priesthood-landing/) |
| LDS Conferences | [Open](https://apps.apple.com/us/app/lds-conferences/id1483787977) | [lds-conferences-landing](https://zhiyao92.github.io/lds-conferences-landing/) |

Each landing page is its own repository — a change there is not a change here.

## The landing page

Plain static HTML in a single file, no build step and no dependencies. GitHub
Pages serves `main` from the repository root (`.nojekyll` keeps Jekyll out of it).

Three tabs share one layout: **Apps**, **Experience** and **Certificates** are all
vertical timelines with a year rail on the left, a dot on the line, and a card on
the right. Tabs deep-link — `/#experience` and `/#certificates` open straight to
that tab. Each app card also has its own anchor (`/#beam`, `/#lds-quotes`, …) for
linking straight to one app.

```
index.html                # the whole site: styles, markup and script in one file
privacy-policy.html       # portfolio-wide, shared by every app
terms-and-condition.html  # portfolio-wide, shared by every app
contact-us.html           # contact form
icons/                    # 256px app icons, used by the Apps timeline
icons/logos/              # employer and certificate-issuer logos
Screenshots/              # App Store marketing screenshots, not used by the site itself
avatar.jpg                # profile photo in the hero, also the JSON-LD image
og-image.png              # 1200x630 social preview card, composed from the same data
favicon.png               # tab icon
profile-picture.png       # unused by the site, kept for reuse elsewhere
app-ads.txt               # AdMob seller declaration, served at the domain root
robots.txt                # points crawlers at sitemap.xml
sitemap.xml               # the four pages, for search engines
.nojekyll                 # serve the files as-is
```

### Theming

Colours are CSS custom properties on `:root`, defined once for light and
overridden for dark. The page follows the visitor's system setting until they
press the toggle in the top right, which writes `light` or `dark` to
`localStorage`. A small script in `<head>` applies a stored choice before first
paint so the wrong theme never flashes.

Any new colour must be a token — a hard-coded hex will look correct in one theme
and wrong in the other.

Each app card also carries a one-off `--app-accent` colour as an inline style,
picked by hand from its icon — it tints the card's top border and hover glow.
It's deliberately not a CSS variable in `:root` since it doesn't change with
the theme.

### Fonts

Headings (`h1`, card/role/cert titles, tab labels, section labels) use
**Bricolage Grotesque** from Google Fonts, loaded in `<head>`. Body text stays on
the system font stack. If Google Fonts is ever dropped, those selectors fall back
to `-apple-system` and the page still reads fine.

### Adding an app

1. Export a 256px icon to `icons/`.
2. Copy a whole `<div class="timeline-row">` block in the Apps timeline and edit
   the icon, name, tag, rating, one-line description, `id`, `--app-accent` and
   links.
3. Put the release year in `<div class="timeline-year">`, or leave it empty when
   the app above it already shows that year.
4. Add a row to the table above, and to the `owns` list in the JSON-LD block in
   `<head>`.

Rows are ordered newest-first. The description is **one sentence** that names the
moment the app is for, not a feature list.

The legal pages already cover every app, so there is nothing else to update. If
the 25-shipped / 9-live figures in the hero, stats strip or `og-image.png` ever
change, regenerate `og-image.png` to match — it's composed from the same numbers,
not a static asset.
