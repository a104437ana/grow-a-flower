# grow-a-flower

a minimal focus timer that grows a glowing flower while you study.

choose how long you want to focus, hit start, and watch a generative neon
flower bloom on screen as time passes. no account, no tracking, one HTML
file. when the timer ends, the flower opens fully and bursts into
particles — with an optional alarm.

## usage

```bash
python3 -m http.server
```

then open `http://localhost:8000` in your browser.

or just open `index.html` directly.

## how it works

- the flower is drawn entirely on `<canvas>` — bezier-curve petals in 7
  layers that open from the outside in as the session progresses, additive
  ("lighter") blending for the glow, a fibonacci-spiral center at the end.
- each session picks a random color palette and petal layout, so every
  flower is unique.
- the countdown is based on `Date.now()`, so it won't drift if the tab is
  backgrounded; remaining time is shown in the tab title.
- no build step, no dependencies, no server required.
