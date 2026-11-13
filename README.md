# Time Circuits

A dependency-free retirement countdown, independently implemented from the
observable behavior of the [reference site](https://time-circuits.magicbullet.workers.dev/).
No source code, fonts, images, or other assets were copied from that site.

## Run

Open [index.html](./index.html) in a modern browser. No installation, build, account,
or backend is required. All CSS, JavaScript, and original SVG digit graphics are
inside that file.

For a stable local origin and consistent saved settings:

```powershell
python -m http.server 8080 --bind 127.0.0.1
```

Then open <http://127.0.0.1:8080>. Stop the server with Ctrl+C.
Browser storage behavior for directly opened files varies between browsers.

## Features

- Centered brushed-metal enclosure, dark instrument windows, red label strips,
  and glowing red, green, and amber displays matching the reference's visual style.
- Original SVG seven-segment digits and segmented month letters with AM/PM indicators.
- Responsive layout, keyboard-accessible controls, and screen-reader labels.
- Set a local destination using **Set destination time**, then **Engage**.
- Destination saved in browser local storage; storage errors are visible.
- Fixed dark instrument styling, independent of the device's light/dark preference.
- Countdown recalculates from the actual clock after sleep or backgrounding.
- Past destinations show zero and a destination-reached message.

The initial destination is December 25, 2026 at local midnight. A saved destination
represents an exact instant: if you change time zones, that instant is preserved
and displayed in the device's current local time. No data leaves the browser.
Clearing browser storage removes saved preferences.

The instrument styling is independently recreated from visual observation.
It is not an affiliated product.

## Test

With Node.js 18 or newer:

```powershell
node --test tests\countdown.test.cjs
```

Tests exercise the actual countdown code embedded in the HTML, including
rounding, expired targets, long countdowns, leap dates, daylight-saving gaps,
and saved-setting validation.

## Deploy

Upload [index.html](./index.html) to any static web host. There is no build output
or server-side component to deploy.
