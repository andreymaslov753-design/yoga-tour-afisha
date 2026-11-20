# Yoga Tour Afisha / Афиша йога-тура

[![Made with pollinations.ai](https://raw.githubusercontent.com/pollinations/pollinations/main/packages/ui/src/brand/badge-made-with.svg)](https://pollinations.ai/?ref=badge)

A small static web app for yoga-tour and retreat posters (Sochi, Abkhazia, and nearby coasts). It calls the [Pollinations image API](https://gen.pollinations.ai/docs) to generate a typography-free background, then composites the Russian title, dates, and a short call-to-action in the browser so Cyrillic stays sharp.

Статическая страница для афиш йога-туров и ретритов. Фон рисует Pollinations, русский текст накладывается локально на canvas.

## What it uses

- API: `GET https://gen.pollinations.ai/image/{prompt}`
- Default model: `tongyi-mai/z-image-turbo`
- Sizes: 1080×1920 (stories), 1080×1080 (post), 1920×1080 (cover)
- No secret keys in the repository. Visitors sign in with Pollinations via the official `<polli-connect>` button ([Pollinations Pay](https://github.com/pollinations/pollinations/blob/main/BRING_YOUR_OWN_POLLEN.md)); the page never asks them to paste a key.
- After sign-in, the user's key stays in the browser and is sent only to `gen.pollinations.ai` as `Authorization: Bearer`. Uncached generations use the visitor's Pollen. Identical cached requests may be served without a key, as documented in the official API docs.

## Run locally

Open `index.html` in a browser, or from this folder:

```bash
python3 -m http.server 4173
```

Then visit `http://127.0.0.1:4173`.

## Host for free

Preferred, no extra Cloudflare token needed:

1. Create a public GitHub repository under the same account that is linked at enter.pollinations.ai (for this project: `andreymaslov753-design`).
2. Push these files.
3. Enable GitHub Pages from the `main` branch root.
4. Public URL will look like `https://andreymaslov753-design.github.io/<repo>/`.

Alternative: [Pollinations Sites](https://gen.pollinations.ai/docs#tag/sites) at `https://<name>.pollinations.app` via `polli sites deploy` (needs a Pollinations key with the `machines` permission; never put that key in the site files). Cloudflare Pages is also possible, but the existing Workers AI token should not be assumed to deploy Pages.

## License

You may use and modify this app. Please keep the “Made with pollinations.ai” badge visible.
