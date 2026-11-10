# SYNC APP

A wellness web app for Yoga and Contrast Therapy bookings, member rewards and daily studio operations.

**[Open the live demo](https://sync-wellness.vercel.app/)**

## Latest update: quieter, clearer studio interface

The `codex/unslop-sync` branch applies [unslop](https://github.com/heydamir/unslop) to the existing member and staff workspaces. Shared neutral surfaces, SYNC's original pale-lime accent, consistent spacing, readable labels and simpler motion put bookings, pass balances and studio operations first. English and Traditional Chinese labels are included.

- The overview leads with the next visit, followed by pass balances and membership progress.
- Sign-in, booking cards, wallet, rewards and staff tools share the same controls and surface hierarchy.
- Decorative glow, glass effects and pointer-following card motion have been removed.

[Overview](docs/reviews/unslop/overview-desktop.png) · [Booking](docs/reviews/unslop/booking-desktop.png) · [Staff schedule](docs/reviews/unslop/schedule-desktop.png) · [Sign-in](docs/reviews/unslop/sign-in.png)

Verified member sign-in, booking and cancellation with pass deduction/restoration, and reward redemption with persisted points/pass balances. Member and admin screens were reviewed at 390 and 1440px, including Traditional Chinese member views. All 15 JavaScript files passed syntax checks and all 25 stylesheets passed PostCSS parsing. Camera scanning was not completed because the browser handed control to the user at the camera permission prompt; front-desk and instructor sessions were not separately exercised. This is not a full accessibility audit.

Design method: **unslop by Damir Sokolovsky**, used under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The method has been adapted to SYNC's existing product and brand.

## Previous update: member experience improvements

Deployed on 7 November 2026 ([implementation commit](https://github.com/ikigaiwif606-acc/SYNC-APP/commit/c9ca1a049c14de674433cad95d9112dae73b3695)).

- **More readable bookings:** supporting text is now 13–14px, with a direct “Book a session” heading.
- **One clear overview action:** “Book a class” replaces two links to the same booking screen.
- **Compact reward cards:** reward names, points costs and redemption actions come first; small service icons replace large decorative illustrations.
- **Simpler headings:** redundant uppercase captions have been removed from member page introductions.
- **Consistent styling:** shared color and surface tokens retain SYNC’s forest-green identity while reducing feature-specific overrides.
- **Traditional Chinese support:** translations cover the updated labels.

Verified demo booking and reward redemption, Traditional Chinese labels, and booking and rewards layouts at 320, 390, 768 and 1440px. This was a targeted usability update, not a complete accessibility audit.

## Features

- **Book classes** — browse sessions, check availability and manage bookings.
- **Wallet** — view Yoga and Contrast Therapy passes, expiry dates and redeemed rewards.
- **Rewards** — redeem points and track visit-based Plus, Core and Luxe membership progress.
- **Account** — edit your profile, view purchases and points activity, and show your check-in QR code.
- **People & staff tools** — browse people by role, manage sessions, book for members and scan check-in codes.
- **Admin controls** — create accounts, edit profiles, change roles, activate/deactivate access and review change history.
- **Attendance reports** — weekly and monthly dashboards with filters and CSV export.

Responsive layouts support English and Traditional Chinese.

## Demo accounts

Use **Try a demo account** on the sign-in page, or enter one of these accounts. All use the demo password: `SyncDemo2026!`

| Role | Email | Workspace |
| --- | --- | --- |
| Member | `jamie@sync.demo` | Bookings, wallet, rewards and profile |
| Admin | `admin@sync.demo` | Studio management, account creation, passes, points and reports |
| Front desk | `frontdesk@sync.demo` | Member assistance, bookings, check-in and reports |
| Instructor | `instructor@sync.demo` | Assigned classes, preparation, attendance and reports |

One sign-in form opens the workspace assigned to each account. Admin can create accounts for all four roles.

## Run locally

No build step or package installation is required. With Python 3 installed:

```sh
git clone https://github.com/ikigaiwif606-acc/SYNC-APP.git
cd SYNC-APP
python3 -m http.server 4173 --bind 127.0.0.1
```

Open [localhost:4173](http://127.0.0.1:4173/).

## Demo scope

Data is saved in the current browser using local storage. Accounts and records are not shared across devices. Sign-in and purchases are simulated; no real payments or emails are sent. Use sample details when exploring.

Membership benefits and booking policies are prototype settings.

## Project structure

- `index.html` — app entry point.
- `src/core/` — shared app logic, translations and membership rules.
- `src/styles/` — global styles, shared theme tokens (`theme.css`) and visuals.
- `src/features/` — JavaScript and CSS grouped by feature.
- `assets/logos/` — SYNC brand assets.
- `vendor/` — bundled QR libraries and their licenses.
- `docs/` — workflow diagrams, review notes and future planning.

Future consideration: [Invite to SYNC referral program](docs/planning/referral-program.md).

## Built with

HTML, CSS and vanilla JavaScript, hosted on Vercel. QR tools are bundled locally: [jsQR license](vendor/jsQR-LICENSE.txt) and [QRCode.js license](vendor/qrcode-LICENSE.txt).
