# Couch co-op for The Two Towers Recompiled (fork)

> This branch, `coop-1.9.7`, is [The Two Towers Recompiled](https://github.com/Gumpolas/TooTawersRecomp) **1.9.7**
> with this fork's later co-op work merged on top. The port's own README (downloads, what the port adds, release
> notes): [README.md](https://github.com/Volverine-Dude/TooTawersRecomp-coop/blob/coop-1.9.7/README.md). How co-op
> and Versus play: [COOP.md](https://github.com/Volverine-Dude/TooTawersRecomp-coop/blob/coop-1.9.7/COOP.md).

Co-op is part of the official port from 1.9.6, which merged this fork's first version. This branch is based on
**1.9.7** (Versus, achievements, Impossible difficulty, the F10 options) and adds the co-op changes below, which are
not in an official release yet. It is still an **alpha**.

It needs the same game as the port: the US Xbox retail release. Nothing from the game is in this repository: no
game data, and no code generated from the game.

## What this branch adds to 1.9.7

**Controllers and menus**
- Player 1 keeps his controller in co-op (in 1.9.6 the only controller went to player 2).
- Co-op menu: the title, New Game and Load Game in the middle at the top in the main menu's font; the Ready line on
  the hero select; P2 Bot with three modes (Off, When Idle: any input on player 2's controller hands it back for 3 s,
  Always); P2 Controls (player 2's own button layout).

**Story**
- Forced heroes for player 2: Isildur on the prologue; Legolas on Weathertop, with copies of player 1's weapons.
- A level beaten in co-op with a hero shows "Already Beaten" on the mission select; once the game is cleared, every
  story level is open.
- Films can be skipped the first time they play; the mission select's save question is no longer blocked.

**Play**
- A downed hero comes back on ground player 1 actually stood on, near the other hero (not inside a wall or over the
  void).
- Only player 1 sets off the camera planes.
- Aim dots: while a player aims (LT), a dot over the enemy his lock is on, in his colour (player 1 blue, player 2
  amber), smaller the further it is from the camera.
- Heroes' arrows and thrown axes fly through allies and only hit the enemy they are locked on (and walls); every hit
  counts (the game took some enemies' damage only in some of their states: the cave troll ignored most arrows).
- A hero's lock never stays on an ally.

**HUD**
- The P1 / P2 head markers and the aim dots are drawn under every HUD piece.
- The boss bar (every boss's) sits under player 2's health sword at the top right.

**P2 Bot**
- At the Watcher: attacks a random idle tentacle, parries strikes near it. At the cave troll: a task of its own
  (stays at reach, attacks, parries the troll's swings at it). Not stuck at the Gates of Moria's lake.
- In Versus it fights player 1 (1.9.7's), as a task of the reworked bot.

All of these are co-op only; in Versus the other hero stays the target (the pass-through and ally rules are off there).

## Building

As for the port: see the README's
[Building from source](https://github.com/Volverine-Dude/TooTawersRecomp-coop/blob/coop-1.9.7/README.md#building-from-source).
You generate the game's C code from your own `default.xbe`, then compile it with the runtime.

## Testing

`tools/coop-bot/` runs the real game with bots and checks its log: see its
[README](https://github.com/Volverine-Dude/TooTawersRecomp-coop/blob/coop-1.9.7/tools/coop-bot/README.md). The
`TT_COOP_*` environment variables set up test situations (each one is described where the code reads it). The
changes above were checked with bot runs; a human playtest of each is still under way.

## Research

Addresses, evidence and what didn't work:
[the Co-op Anything write-up](https://github.com/cranebeaker/coop-anything/tree/main/games/lotr-two-towers).

## License and credits

MIT, as the port (see [LICENSE](https://github.com/Volverine-Dude/TooTawersRecomp-coop/blob/coop-1.9.7/LICENSE.txt));
xboxrecomp's licenses are in `xboxrecomp-0.12.0/`.

- [The Two Towers Recompiled](https://github.com/Gumpolas/TooTawersRecomp) by Gumpolas: the port, its co-op and Versus.
- [xboxrecomp](https://github.com/sp00nznet/xboxrecomp) by sp00nznet: the recompilation toolkit it uses.
- [Co-op Anything](https://github.com/cranebeaker/coop-anything): the playbook this work followed.
- The Lord of the Rings: The Two Towers belongs to its rights holders; nothing from the game is included here.
