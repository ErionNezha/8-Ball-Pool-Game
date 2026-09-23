# 8 Ball Pool Game

Created by **Erion Nezha**

Play it live: https://erionnezha.github.io/8-Ball-Pool-Game/

A classic 8-ball pool table game. Aim with the mouse, click to shoot, and pocket all 15 balls — but don't sink the black 8-ball too early!

## Original Python version

Requires Python 3 and pygame:

```bash
pip install pygame
python 8BallPool.py
```

`8BallPool.py` is included here as an exact copy of the original source.

## Web version

Open `index.html` in any modern browser — no build step, no dependencies, no CDN. It's a faithful port of the Python/pygame original to HTML5 Canvas + vanilla JavaScript:

- same table size (660×400 internal resolution, responsive scaling) and exact colors
- same physics: speed/angle model, 0.005 friction per frame, wall bounces, ball-to-ball collisions using the original formulas
- same mouse aiming (cue stick follows the mouse, white aim line) and click-to-shoot with force = distance / 10, capped at 10
- same starting triangle formation of the 15 numbered balls
- same bottom strip with the remaining balls and "Remaining Balls: N"

## Controls

- **Mouse** — move to aim, **click** to shoot toward the click point (shot force grows with distance, max 10)
- **R** — new game
- Touch works too: tap to shoot

## Note: win condition fix

In the original Python code the *"You Won!"* message was unreachable: pocketing the 8-ball always showed *"You Lost! Black in Hole!"*, even when it was the last ball on the table (the game also ended in a loss as soon as only the 8-ball remained). The web port fixes this with one small rule change: pocketing the 8-ball now ends the game with **"You Won!"** if it was the last remaining ball, otherwise **"You Lost! Black in Hole!"**. Everything else is a 1:1 port of the original.
