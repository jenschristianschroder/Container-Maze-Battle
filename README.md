# Scrapyard Battles

A top-down arcade buggy shooter built as one self-contained `index.html`. The game includes all graphics, styles, logic, and synthesized sound. It has no runtime dependencies or build step.

## Play

Open `index.html` in a browser, or serve the repository with any static host. For a local web server, run `python3 -m http.server 8000` and open `http://localhost:8000`.

## Modes

| Mode | Goal |
| --- | --- |
| Solo Defense | Protect the crusher through five waves. |
| Co-op Defense | Defend the same crusher with two local players. A knocked-out driver recovers after six seconds while the teammate stays alive. |
| Head-to-head | Fight a local two-player duel. First to three knockouts wins. |

All three layouts are available immediately. Container Maze has tight alleys, Crusher Yard has open approaches, and Rust Circuit has long flanking routes. Completing Defense opens the next yard. Each duel round starts with equal armor and mirrored spawn positions.

## Controls

| Action | Player 1 | Player 2 |
| --- | --- | --- |
| Drive | WASD | Arrow keys |
| Fire | Space | Enter |
| Boost | E | Either Shift key |
| Pause | Escape or P | Escape or P |

On touchscreens, each player has a joystick, a fire button, and a boost button. Holding fire assists aim toward visible targets ahead of the buggy. The camera stays directly overhead. Split-screen stacks in portrait and sits side by side in landscape. The optional face-to-face setting rotates Player 1's camera and controls.

Containers, wrecks, and tire piles block movement and bullets. Boosting into bots damages them. Pickups repair armor, grant rapid fire, or provide a temporary shield. Scrap adds points in Defense. Between waves, surviving drivers and the crusher receive partial repairs. Duel rounds enter sudden death after 75 seconds.

Sound is optional. Sound preferences and Defense best scores are stored locally when browser storage is available. Hiding the page or losing focus pauses a match.

## Implementation

The page uses Canvas 2D, a fixed simulation step, cached scenery, capped effects, continuous projectile collision, and a navigation grid for enemy routes. Each split-screen view draws the same shared simulation. Local multiplayer runs on one device.

Simulation checks cover all nine mode/layout combinations, wave completion, duel scoring, cover collision, movement, damage, recovery, and pause behavior. Canvas rendering was inspected at phone and desktop sizes. Interactive browser testing and real-device multi-touch testing remain to be completed.
