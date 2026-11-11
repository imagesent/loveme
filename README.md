# loveme ❤️

A Python + `turtle` animation that fills a heart with **"I love you" in 20 languages**.

Phrases are packed inside the heart's outline like a word cloud, then fly into place,
flash red, and settle. Once everything has landed, the heart gently shimmers.

## Requirements

- Python 3.9+ — only the standard library is used
- Tkinter — bundled with Python on Windows and macOS.
  On Linux, install it with your package manager, e.g.:

  ```bash
  sudo apt install python3-tk
  ```

## Usage

```bash
python love.py
```

That's it — no dependencies to install. The animation builds the heart over
about 10 seconds, then keeps shimmering in the open window. Close the window
to exit.

## How it works

- The heart outline comes from the classic parametric equation
  `x = 16·sin³(t)`, `y = 13·cos(t) − 5·cos(2t) − 2·cos(3t) − cos(4t)`.
- Horizontal slices of the heart are computed per text row, and phrases are
  packed into the available spans, alternating between four font sizes with
  small random jitter so the fill looks organically scattered.
- Edge phrases are placed around the outline (sorted by angle) and inner
  phrases from the outside in, so the heart builds up naturally.
- Rendering happens on the raw Tk canvas (`tracer(0)`) rather than with
  turtle's pen — each phrase eases in with a cubic ease-out, flashes red,
  then settles into black.
- A seeded random number generator (`Random(11)`) makes every run look the
  same.

## Languages included

English, Türkçe, Español, Français, Deutsch, Italiano, Português, Русский,
한국어, 日本語, 中文, हिन्दी, Ελληνικά, Nederlands, Svenska, Polski, ไทย,
Tiếng Việt, Bahasa Indonesia, Українська
