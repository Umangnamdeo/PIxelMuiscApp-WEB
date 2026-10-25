# PixelMusic Landing Page

A single-page, responsive landing website for **[PixelMusic](https://github.com/ianshulyadav/PixelMusicApp)**, an open-source, ad-free Android music player that combines local lossless audio with YouTube Music streaming in a Material You interface.

The whole site is one self-contained `index.html` file. There is no build step, no framework and no `node_modules`.

## Features

- **Intro animation:** logo pop-in, bouncing equalizer bars and an iris-wipe reveal. It plays once per browser session and can be skipped with a click or the Skip button.
- **Living galaxy background:** a canvas starfield with a slowly rotating spiral galaxy, shooting stars and soft blurred nebula glows over an OLED-black base. Stars shift slightly with the mouse.
- **Hero banner:** the PixelMusic banner with the headline, subhead and download buttons.
- **Feature bento grid:** six pastel cards covering streaming and local audio, Material You theming, synced lyrics, the 10-band EQ, privacy and background playback.
- **Screenshots:** a row of tilted phone screens (Browse & Discover, Moods & Genres, Now Playing, Podcasts and Lossless FLAC), with the Now Playing screen enlarged in the center. On small screens the row scrolls sideways.
- **Download and install guide:** download card plus a three-step install guide.
- **Footer:** links to the repository, release notes, issues and Telegram, plus the creator credit.
- **Accessibility and polish:** respects `prefers-reduced-motion` (the intro and canvas animation are skipped), keyboard-friendly focus styles, and safe-area padding for phones with notches.

## Project structure

```
.
├── index.html   # the entire site: HTML, CSS and JavaScript
└── README.md
```

Screenshots, the banner and the logo are embedded in `index.html` as base64 images, so there are no other files to host. Because of that, a few lines in the file are very long. When editing, search for `data:image` to find them and avoid changing those lines.

## Running locally

Open `index.html` in any browser. For auto-reload while editing, use VS Code with the **Live Server** extension: right-click `index.html` and choose **Open with Live Server**.

Fonts (Unbounded and DM Sans) load from Google Fonts, so they need an internet connection. Offline, the page falls back to system fonts.

## Deploying

If your file is named `pixelmusic.html`, rename it to `index.html` first.

**Netlify (drag and drop)**
1. Open your site in Netlify and go to the **Deploys** tab.
2. Drag the folder containing `index.html` onto the deploy area.

**Netlify, Vercel or GitHub Pages from a repo**
1. Put `index.html` in the root of your repository.
2. Connect the repository to the host. Every push then redeploys automatically.
3. Leave the build command empty and set the publish directory to the repository root.

Netlify's free plan uses a monthly allowance and each production deploy uses part of it, so avoid redeploying for every tiny tweak.

## Customizing

Search for these in `index.html`:

| What to change | What to look for |
| --- | --- |
| Accent colors | `--v` (blue) and `--c` (cyan) at the top of the `<style>` block |
| Download button destination | `PixelMusicApp/releases` (appears on the three download buttons and the footer) |
| Intro length | `setTimeout(done,2800)` near the end of the script (milliseconds) |
| Replay the intro while testing | Open the site in a private window, or clear the `pm-intro` key in session storage |
| Background colors | `.bg i:nth-child(...)` for the glows, and the `hsl(` values in the canvas script for stars and galaxy |
| Footer credit | the `.by` block in the footer |

### Direct APK download (optional)

The download buttons currently open the project's Releases page. To make them download the APK straight from the latest release instead, upload the APK to a GitHub Release with the same file name every time (for example `PixelMusic.apk`) and use this link:

```
https://github.com/ianshulyadav/PixelMusicApp/releases/latest/download/PixelMusic.apk
```

This keeps APK traffic on GitHub and off your website host.

## Links

- App repository: https://github.com/ianshulyadav/PixelMusicApp
- Releases and APK downloads: https://github.com/ianshulyadav/PixelMusicApp/releases
- Issues and feature requests: https://github.com/ianshulyadav/PixelMusicApp/issues
- Telegram: https://t.me/PixelMusicApp

## Credits

- PixelMusic app by [ianshulyadav](https://github.com/ianshulyadav) and contributors.
- Landing page created by [Umang Namdeo](https://github.com/Umangnamdeo).

## License

Add your license here (for example MIT) and include a `LICENSE` file in the repository. The app itself is open source; check its repository for the exact license that applies.
