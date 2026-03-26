# Do You Love Me? 💕

A silly single-page "Valentine's Day trap" you can send to someone. It asks them "Do You Love Me?" with a **Yes** and **No** button — except the No button has other plans.

![Preview](https://img.shields.io/badge/status-no_is_not_an_option-ff3a6e?style=for-the-badge)
![HTML](https://img.shields.io/badge/HTML-single_file-e34c26?style=flat-square&logo=html5&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)

---

## What happens

You send someone the link. They see a cute card asking "Do You Love Me?" with two buttons. They click **Yes** — confetti, cat kiss meme, everyone's happy.

But if they try to click **No**... things escalate.

The No button escapes from the card and starts flying around the screen. And it doesn't stop there — every attempt triggers something worse. There are **17 phases** of escalating chaos before the button finally gives up and switches sides.

### The 17 stages of denial

| # | What happens |
|---|---|
| 1 | Button runs away (normal) |
| 2 | "Someone special is watching you decide..." typing indicator |
| 3 | The No button speaks: *"Please don't click me 🥺"* |
| 4 | Fake notification: 📸 *"Screenshot sent to your crush"* |
| 5 | The card starts crying actual tears |
| 6 | Entire page flips upside down |
| 7 | No button says goodbye and fades out (comes back) |
| 8 | **KISS CAM** — full stadium-style overlay with REC dot |
| 9 | Notification: 📱 *"Mom is calling... she's disappointed"* |
| 10 | 6 decoy No buttons spawn everywhere |
| 11 | Card starts glitching + system warning |
| 12 | Page tilts sideways, button screams *"I HAVE A FAMILY"* |
| 13 | Screen goes black like the tab crashed, then: *"You thought closing the tab would save you?"* |
| 14 | *"Your WiFi will be disconnected until you say Yes"* + blur |
| 15 | 10 clone buttons flood the screen |
| 16 | Full desperation — glitching, tears, *"PLEASE I'M BEGGING"* |
| 17 | **Windows Blue Screen of Death** → reboots → No button surrenders and becomes *"OK Fine, YES 😤💖"* |

After they (inevitably) click Yes, they get a confetti explosion and a cat kissing the camera. You're welcome.

## Demo

Just open `index.html` in any browser. That's it. No build step, no dependencies, no npm install. It's a single HTML file.

Works on desktop and mobile. Tested on Chrome, Safari, Firefox, and Edge.

## How to use

**Option A — just send the file:**
1. Download `index.html`
2. Send it to someone on WhatsApp/Telegram/Discord/whatever
3. They open it in their phone browser
4. Watch them suffer

**Option B — host it somewhere:**
1. Drop it on [Netlify](https://netlify.com), [Vercel](https://vercel.com), [GitHub Pages](https://pages.github.com), or literally any static host
2. Send the link
3. Same result, but fancier

**Option C — GitHub Pages (easiest):**
1. Fork this repo
2. Go to Settings → Pages → Deploy from main branch
3. Your link is `https://yourusername.github.io/do-you-love-me/`
4. Send it

## Tech stuff

- **Pure HTML/CSS/JS** — no frameworks, no libraries, no build tools
- **Single file** — everything is self-contained including the cat GIF (base64 encoded)
- **Mobile responsive** — three breakpoints (480px, 360px, landscape), touch events, no-scroll, proper `dvh` support
- **~1.6MB** — mostly the embedded GIF. could be smaller with an external image but the whole point is that it works offline with zero dependencies

### Things I had to deal with

- The No button uses `position: fixed` once it escapes, but needs to avoid landing back inside the card. There's a zone-based positioning system that calculates safe areas above/below/left/right of the card.
- Mobile Safari has... opinions about viewport height. Using `100dvh` and `touch-action: manipulation` to keep things sane.
- `preventDefault` on `touchmove` to stop pull-to-refresh from ruining the experience.
- The BSOD phase takes over the screen, so the escape handler returns `true` to skip the normal button movement — otherwise the button would teleport behind the blue screen and the user would never see it.

## Customization

Want to change the question? The meme? The taunts? Everything is in the HTML file:

- **Question text**: search for `Do You Love Me?` in the HTML
- **Taunts array**: search for `var taunts = [`
- **Phase actions**: search for `var phases = [` — each function is one escalation step, commented with what it does
- **Cat GIF**: replace the base64 `src` in the `<img>` tag (or just use a URL if you don't care about offline support)
- **Colors**: the whole palette is built around `#ff3a6e` / `#ff6b9d` / `#1a0011` — search and replace if you want a different vibe

## Why

I was bored. Also Valentine's Day.

## License

MIT — do whatever you want with it. Send it to your crush, your ex, your mom, your cat. I don't care.

If you actually use this to ask someone out and it works, please open an issue and tell me about it. I need to know.
