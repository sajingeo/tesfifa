# ⚽ World Cup Live — Tesla Edition

A single-file live match tracker for the 2026 FIFA World Cup, designed for the Tesla in-car browser: dark theme, huge touch targets, no hover interactions, and automatic refresh while parked or charging.

![On a Tesla screen](demo.jpg)

**Features**
- Live scores for every match of the day, with a match switcher
- Play-by-play commentary feed (goals, cards, subs highlighted)
- Animated team stats (possession bar, shots, corners, passes…)
- Lineups drawn on a pitch by formation, with sub on/off and card badges
- Full-screen animated GOAL! celebration with confetti when a score changes
- Auto-refresh every 20s during live matches (90s otherwise)

**Data source:** ESPN's public scoreboard/summary API for `soccer/fifa.world` — no API key required, CORS-enabled.

## Run locally

```bash
python3 -m http.server 8765
# open http://localhost:8765
```

## Get it in your Tesla

The Tesla browser needs a public URL. The simplest free option is GitHub Pages:

```bash
git add index.html README.md
git commit -m "World Cup live tracker"
gh repo create tesfifa --public --source=. --push
gh api repos/{owner}/tesfifa/pages -X POST -f 'source[branch]=main' -f 'source[path]=/'
```

Then open `https://<your-username>.github.io/tesfifa/` in the Tesla browser and bookmark it. (Netlify Drop or Vercel work just as well — it's one static file.)

## Notes

- Tracks the FIFA World Cup (`fifa.world`). For the Club World Cup, change `API` in `index.html` to use `fifa.cwc`.
- Tap the screen during a goal celebration to dismiss it early.
- On phones, the app shows a redirect message pointing to the Tesla-friendly URL — this is a Tesla-screen experience, not a mobile one.

## Support

If this made a charging stop more fun, [☕ buy me a coffee](https://buymeacoffee.com/sajingeo).

## License

[MIT](LICENSE) — powered by [ESPN](https://www.espn.com/soccer/).
