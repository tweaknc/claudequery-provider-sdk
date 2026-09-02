# The Quest to Rename Wonders and Waterways of the World

An 8-bit browser game. Three holes of golf-course platforming, helicopter
dogfighting and very polite Canadian resistance — plus one hidden level — and
then you get to redraw the atlas.

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

## The secret level

Somewhere on Hole 1 there is a way in. It is findable, not cruel: near the
last green, climb the three-platform stack and take the golden ball. That
warps you under the Delaware Rec Center, where Corn Pop is in a cage and the
Big Guy is doing laps with the key, throwing ice cream. Five good swings.

Freeing Corn Pop pays 5000 points and unlocks a fourteenth, secret decree at
the ceremony. You come back out onto the same fairway exactly where you left,
with your collected balls intact.

## The renaming ceremony

Clear all three holes and you reach the signing table.

**Waterways & Landmarks (6)** — the Great Lakes, the Strait of Hormuz, the
Panama Canal, the River Thames, Mount Everest, the Pacific Ocean.

**Wonders of the World (7)** — the Great Pyramid of Giza, the Eiffel Tower,
the Louvre, the Great Wall of China, the Colosseum, Machu Picchu, the Taj
Mahal. (Two of those are not on anybody's official list. The decree
acknowledges this and proceeds anyway.)

**Secret Bonus Decree (1)** — only if Corn Pop walks.

Pick one of three suggestions or type your own name, then stamp it with the
Seal of the Boss. The ending scrolls the updated atlas.

## Notes

It's a parody. The moose has filed an appeal.

## Structure

`index.html` is one file in labelled sections: palette and sprite data, input,
WebAudio, the platformer engine and its two levels, the shooter level, the
renaming ceremony, the screens, and the fixed-timestep main loop at the bottom.
Tuning constants (`GRAV`, `MAXVX`, `JUMPV`) sit at the top of the platformer
section — the level geometry is built around that jump arc: it clears 78px
across and 58px up, so no gap exceeds 44px and no platform step exceeds 56px.
