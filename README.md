# ROTATE ($ROTATE)

**Buys the next meta, not the last one.**

ROTATE counts which words and themes are speeding up in new pump.fun launches right now and buys the leader of the newest one. The site is a live board that runs in the browser on PumpPortal's free launch stream. No API keys.

Layout: "the word is the visual". Light Swiss poster, one giant live word that flips when the meta rotates, a ticker of live launch words, a pinned rank chart for the story, a live pipeline, a typographic board and a black token section. No WebGL, so it runs everywhere.

Files: `index.html` and `og.jpg`. No build step, no dependencies. The previous orrery version is kept in `v1-orrery/`.

## What is live and what is not

| Part | Status |
|---|---|
| Launch stream (`wss://pumpportal.fun/api/data`) | Live, free, no key. One connection per visitor |
| Words, themes, acceleration, emerging words, the pick, the giant word | Live, computed in the browser every 2 seconds |
| Leader of the pick | Live via DexScreener's free API. If it can't be reached, the site says so and shows the latest launch in the theme |
| The engine's buys | Not live. On the roadmap as "Next". The engine wallet is posted after launch |
| "Why" (the day 05:30–13:45) | Illustrative, labeled as such |
| Preview | If the stream can't be reached, every lamp says **Preview** and the launches are simulated |

The first live visit needs about 4 minutes of launches before ratios mean anything (the page says "Scanning" / "Calibrating"). The last hour is kept in the visitor's browser, so a reload within 15 minutes skips that.

## Fill in at launch

At the top of the script in `index.html`:

```js
const CONFIG = {
  ca: "JBg56n3uCbvzb7NRULRqDF3TPcKGKYqu1gYc1WT5gyp3",   // the $ROTATE mint address
  x: "",              // e.g. "https://x.com/yourhandle"
  dexscreener: "",    // optional
  site: "",           // e.g. "rotate.fun", printed on rotation cards
  engineWallet: "",   // the engine's public wallet once it is live
  ...
};
```

## Deploy

1. Create a GitHub repo and push `index.html`, `og.jpg` and `README.md`.
2. Vercel → Add New Project → import the repo → Framework Preset **Other**, no build command.
3. Deploy.

## Check after deploy

- The lamps turn red and blink with **Live** within a few seconds.
- After about 4 minutes the giant word stops saying "Scanning" and shows a theme, with a ratio and a leader.
- Fonts load: Sofia Sans Extra Condensed, Albert Sans, Red Hat Mono.
- Scroll through "Why": the rank chart draws with the scroll and the story changes at 08:39, 09:00 and 11:14.
- "Make a rotation card" opens a card that can be saved.
- Paste the link in X and check the preview image.
