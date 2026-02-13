# Digital SVG Clock (KNX / Offline Ready)

A self-contained SVG digital clock that displays the real time using embedded JavaScript.  
Designed for KNX panels, web views, and offline environments.

---

## Features

- Pure SVG file
- Embedded JavaScript (no external dependencies)
- Works offline
- Customizable colors via CSS variables
- Configurable time zone
- Optional seconds display
- Automatic daylight saving time (DST) handling via `Intl`
- Fallback mode if `Intl` is not supported

---

## File

digital_clock.svg

---

## How It Works

The clock:

1. Uses `new Date()` to get the system time.
2. Uses `Intl.DateTimeFormat` to apply a specific time zone.
3. Updates every second using `setInterval()`.
4. Falls back to local system time if `Intl` is unavailable.

No internet connection is required.

---

## Configuration

Open the SVG file and modify the configuration section inside the `<script>` block:

```javascript
const timeZone = "Europe/Berlin"; // Change time zone
const locale = "de-DE";           // Language format
const showSeconds = false;        // true = HH:MM:SS
```

### Example Time Zones

| Location | Value |
|----------|-------|
| Germany | "Europe/Berlin" |
| Portugal | "Europe/Lisbon" |
| Brazil | "America/Sao_Paulo" |
| USA (New York) | "America/New_York" |
| Japan | "Asia/Tokyo" |

---

## Color Customization

At the top of the SVG you will find:

```css
:root{
  --border-color: #000;
  --text-color:   #000;
}
```

Change these values to any CSS color:

```css
--border-color: #555;
--text-color: #00cc66;
```

---

## Usage

### Direct SVG Usage

Upload `digital_clock.svg` to your server or KNX visualization and load it as:

- Image
- iFrame
- Custom HTML widget
- WebView component

---

### KNX Panel Usage

Works if your KNX panel supports:

- SVG rendering
- JavaScript execution inside SVG

Most WebView-based panels support this.  
If scripts are blocked, use the HTML version instead.

---

## Browser / Engine Requirements

Requires:

- Modern browser engine (Chromium, WebKit, etc.)
- JavaScript enabled
- `Intl.DateTimeFormat` support

If `Intl` is not supported, the clock falls back to local system time without timezone conversion.

---

## Offline Capability

Fully offline.

The clock:

- Does NOT use any API
- Does NOT require internet
- Uses only system time

Accuracy depends on the device system clock.

---

## Limitations

- If the system time is wrong, the clock will be wrong.
- If the panel blocks JavaScript in SVG, the clock will not update.
- Very old embedded browsers may lack full timezone support.

---

## License

Free to use and modify.
