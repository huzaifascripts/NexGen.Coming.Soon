# NexGen Computers – Coming Soon

A one-page "coming soon" site I built for NexGen Computers, a computer store opening in Al-Khuwair, Muscat. The shop wasn't open yet and needed something online fast: the logo, a way to message them, and a map pin. So that's all it has.

Live here: https://nexgencomputersoman.com

## What's on the page

- The NexGen logo, animated in piece by piece (it's an inline SVG, so there's no image file to go missing)
- A "Launching soon" line and a short message
- WhatsApp and Instagram buttons
- The shop address with a Get Directions button that opens Google Maps
- An English / Arabic switch

There are no products, prices or cart on it. It's just an announcement page until the real store goes up.

## Running it

It's one `index.html` file with the CSS and JS inside it, so there's nothing to install or build. Download it and open it in a browser, or drop it on any static host.

If you'd rather use a local server:

```
npx serve
```

## Arabic and RTL

The page switches between English and Arabic from the button in the top corner. It remembers your choice using `localStorage`, so you land on the same language next time.

You can also force a language through the URL:

```
index.html?lang=ar
```

When the page is in Arabic it flips to right-to-left. I turned off letter-spacing and uppercase there, because they break the joined Arabic letters. The Cairo font only downloads when Arabic is actually showing.

## Changing things

**Text:** all the visible text is in the `text` object in the script at the bottom of `index.html`, with an `en` and an `ar` section. Edit it there, not in the HTML. The HTML only holds the English as a fallback.

**Countdown:** there's a countdown built in, but it stays hidden because no launch date has been picked yet. When there is one, set `LAUNCH_DATE` near the bottom of the file, with the timezone included (Oman is UTC+4):

```js
const LAUNCH_DATE = '2026-12-01T09:00:00+04:00';
```

**Colors:** they're CSS variables at the top of the `<style>` block (`--orange`, `--ink` and so on).

## Notes

- The animations switch off if the visitor has "reduce motion" turned on in their system settings.
- It works down to small phones, and in landscape on short screens it changes to a two-column layout so nothing gets cut off.
- Buttons have proper labels for screen readers, and keyboard focus is visible.

## A note on the branding

The code is mine, but the NexGen name, logo and contact details belong to NexGen Computers. If you reuse this as a template, swap those out for your own.

Built by Huzaifa Khan.
