# Digital SVG Clock

A simple SVG digital clock that shows the real time using embedded JavaScript.  
Works offline and is suitable for KNX panels and web views.

---

## File

digital_clock.svg

---

## How It Works

- Uses the device system time
- Updates every second
- No internet connection required
- Handles daylight saving time automatically (if supported)

---

## Configuration

Open the SVG file and edit this section inside the `<script>`:

```javascript
const timeZone = "Europe/Berlin"; // Set your time zone
const locale = "de-DE";           // Language format
const showSeconds = false;        // true = HH:MM:SS
```

Example time zones:

- "Europe/Berlin"
- "Europe/Lisbon"
- "America/New_York"
- "Asia/Tokyo"

---

## Change Colors

At the top of the SVG:

```css
:root{
  --border-color: #000;
  --text-color: #000;
}
```

Modify these values to any color you like.

---

## Usage

Upload `digital_clock.svg` to your server or KNX visualization and load it as:

- Image
- iFrame
- WebView
- Custom widget

---

## Requirements

- Modern browser engine
- JavaScript enabled
- SVG scripts allowed

---

## Notes

- Time depends on the device system clock.
- If JavaScript inside SVG is blocked, the clock will not update.

---

Free to use and modify.
