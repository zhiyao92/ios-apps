<h2 align="center">Kelvin Tan — iOS Apps</h2>
<p align="center">
  Independent iOS developer. Nine apps on the App Store.<br>
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

| App | App Store | Landing page |
|---|---|---|
| Beam: Learn Thai & Speak It | [Open](https://apps.apple.com/us/app/beam-learn-thai-speak-it/id6480093061) | [beam-landing](https://zhiyao92.github.io/beam-landing/) |
| Odin Finance: Loans & Budget | [Open](https://apps.apple.com/us/app/odin-finance-loans-budget/id1538554089) | [provision-landing](https://zhiyao92.github.io/provision-landing/) |
| Malaysia Pocket | [Open](https://apps.apple.com/us/app/malaysia-pocket/id1504421248) | [malaysia-pocket-landing](https://zhiyao92.github.io/malaysia-pocket-landing/) |
| LDS Quotes: Daily Inspiration | [Open](https://apps.apple.com/us/app/lds-quotes-daily-inspiration/id1506121689) | [lds-quotes-landing](https://zhiyao92.github.io/lds-quotes-landing/) |
| Bondify: The Couples Edition | [Open](https://apps.apple.com/us/app/bondify-the-couples-edition/id6761910667) | — |
| DishSpin: What to Eat Wheel | [Open](https://apps.apple.com/us/app/dishspin/id6760835509) | [dishspin-landing](https://zhiyao92.github.io/dishspin-landing/) |
| InstantMessage: No-Save Chat | [Open](https://apps.apple.com/us/app/instantmessage-no-save-chat/id1540915370) | [quickapp-landing](https://zhiyao92.github.io/quickapp-landing/) |
| LDS Priesthood: Ordinances | [Open](https://apps.apple.com/us/app/lds-priesthood-ordinances/id1502509285) | — |
| LDS Conferences | [Open](https://apps.apple.com/us/app/lds-conferences/id1483787977) | — |

## Editing the site

Plain static HTML, no build step. GitHub Pages serves `main` from the repository
root.

```
index.html                # landing page — one <article class="card"> per app
privacy-policy.html       # portfolio-wide, shared by every app
terms-and-condition.html  # portfolio-wide, shared by every app
contact-us.html           # contact form
icons/                    # 256px app icons used by the landing page
avatar.jpg                # profile photo used by the landing page
```

To add an app: drop a 256px icon in `icons/`, copy an `<article class="card">`
block in `index.html`, and add a row to the table above. Nothing else to update —
the legal pages already cover it.
