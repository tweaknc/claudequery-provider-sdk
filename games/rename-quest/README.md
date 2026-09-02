# Rename Quest

An 8-bit browser game. Three holes of golf-course platforming, helicopter
dogfighting and very polite Canadian resistance — and then you get to redraw
the atlas.

Everything runs in one `index.html`. No build step, no dependencies, no image
or audio files: the sprites are pixel arrays, the music is a WebAudio square
wave, and the whole thing renders to a 256×224 canvas (NES resolution) scaled
up with `image-rendering: pixelated`.

## Play it

Open `index.html` in any browser. That's it — it works straight off the
filesystem, no server needed.

To host it, drop the file on any static host. For GitHub Pages: Settings →
Pages → Deploy from branch → `main` / root. (Pages needs a public repo unless
you're on a paid plan.)

## Controls

| Action | Keys |
|---|---|
| Move | Arrow keys or WASD |
| Jump | Space or Z |
| Swing club / fire | X |
| Confirm | Enter |
| Pause | P |
| Mute | M |

On phones and tablets an on-screen D-pad appears automatically.

## The three holes

1. **Sand Trap Summit** — a golf-course platformer. Collect balls, bonk the
   geese with a 7-iron, don't land in the drink.
2. **Chopper One** — side-scrolling shooter. Marine One heads north through
   bureaucracy blimps and storm fronts. Grab a bald eagle for a wingman that
   fires alongside you and patches you up.
3. **The 51st Hole** — snow, syrup and hockey defencemen who apologise when
   you bonk them. Ends with the Great Moose of the North, six good swings.

Three hearts per hole, unlimited retries. Pucks can be swung back at the
player who shot them.

## The renaming ceremony

Clear all three and you reach the signing table: six Presidential Decrees,
one apiece for the Great Lakes, the Strait of Hormuz, the Panama Canal, the
River Thames, Mount Everest and the Pacific Ocean. Pick one of three
suggestions or type your own name, and stamp it with the Seal of the Boss.
The ending scrolls the updated atlas.

## Notes

It's a parody. The moose has filed an appeal.

## Structure

`index.html` is one file in labelled sections: palette and sprite data, input,
WebAudio, the platformer engine and its two levels, the shooter level, the
renaming ceremony, the screens, and the fixed-timestep main loop at the bottom.
Tuning constants (`GRAV`, `MAXVX`, `JUMPV`) sit at the top of the platformer
section — the level geometry is built around that jump arc: it clears 78px
across and 58px up, so no gap exceeds 44px and no platform step exceeds 56px.
