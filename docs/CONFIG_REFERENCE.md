# Enigma's Realistic Smoke Rework: settings reference

All settings are in `BepInEx/config/EnigmaPrime.RealisticSmokeRework.cfg` and can also be changed live in game with Configuration Manager (F1). Settings marked *advanced* only show in F1 when "Show advanced settings" is ticked.

## Notes for server owners

- The mod runs on each player's own game and only changes what that player sees. A dedicated server does not need it, and it never changes saved world data.
- The one setting that touches gameplay is **Required space** (Fireplaces). Smelters, kilns and similar stations use the same check to decide whether they are blocked, so every player on a server should use the same value (or leave it at the default).
- Settings are not synced between players. To keep everyone consistent, give players the same `EnigmaPrime.RealisticSmokeRework.cfg`.
- For a base with many fires, the biggest performance levers are **Detailed range**, **Max amount** and **Spawn rate multiplier**.


## General

| Setting | Default | Range | What it does |
|---|---|---|---|
| Enabled | true | - | Master switch. When off, smoke behaves exactly like the unmodded game (including the main menu fire). |
| Extra ignored object ids *(advanced)* |  | - | Extra prefab names (separated by comma) that smoke passes straight through, added to the built-in list (grates, ladders, stairs and similar). Example: wood_gate,wood_door |

## Fireplaces

| Setting | Default | Range | What it does |
|---|---|---|---|
| Required space | 0.5 | 0 to 2 | Clear space needed above a fireplace, in meters, before it will release smoke (the game uses about 0.75). 0 turns the check off. GAMEPLAY: this is the same check smelters, kilns and similar stations use to decide they are blocked, so on a server every player should use the same value. |
| Fire size effect | 1 | 0 to 1 | How much a fire's fuel level changes its smoke (size, speed and puff rate of the three settings below). 0 = every fire looks the same, 1 = full effect. |
| Weak fire puff size | 0.45 | 0.03 to 1 | How big the puffs of a fire with one log (or less) look, as a fraction of normal. A full fire is normal size, fires in between scale smoothly. Visual only. 1 = no change. |
| Weak fire rise speed | 0.38 | 0.1 to 1 | How fast the smoke of a fire with one log (or less) rises, as a fraction of normal. A full fire rises a little faster than normal. 1 = no change. |
| Weak fire spawn boost | 5 | 1 to 6 | How many times more often a fire with one log (or less) releases puffs than a full fire, so its small slow puffs make a steady stream. 1 = no change. High values mean more smoke objects, so raise Max amount with it. |

## Smoke

| Setting | Default | Range | What it does |
|---|---|---|---|
| Lifetime multiplier | 1.25 | 0.1 to 5 | How long smoke lasts before it fades, relative to the game. Longer smoke travels farther and needs a higher Max amount. |
| Spawn rate multiplier | 2 | 0.1 to 10 | How often fires and chimneys release smoke, relative to the game. 2 = twice as often. More smoke costs performance. |
| Spawn timing variance | 0.3 | 0 to 0.9 | Random variation in the time between puffs (0.3 = plus or minus 30%) so smoke comes out in uneven pulses. The average rate stays the same. 0 = perfectly even. |
| Rise speed | 2 | 0 to 10 | Starting upward speed of fresh smoke in meters per second. It still slows as the smoke ages. The game uses 1. |
| Rise speed variance | 0.2 | 0 to 0.5 | Each new puff rises this fraction faster or slower (0.2 = plus or minus 20%), so some smoke overtakes other smoke. 0 = all the same. |
| Chimney pull | 0.6 | 0 to 5 | Extra upward speed (meters per second) for smoke inside narrow spaces like flues, so it is drawn out of the tube. A little stronger in wind. 0 = off. |
| Collider size multiplier | 1 | 0.1 to 2 | Scales how much room a puff needs to move, without changing how it looks. Lower it if smoke gets squeezed in tight flues. Applies to new puffs. |
| Acceleration multiplier *(advanced)* | 2 | 0.1 to 10 | How quickly smoke reaches its target speed, relative to the game. 2 = twice as snappy. Applies to new puffs. |

## Wind

| Setting | Default | Range | What it does |
|---|---|---|---|
| Wind drift speed | 1.3 | 0 to 5 | Sideways speed (meters per second) of cooled smoke in full wind. Higher bends the smoke more. 0 = wind has no effect (also on the main menu). |
| Early wind effect *(advanced)* | 0.4 | 0 to 1 | How much of the wind fresh, hot smoke feels (0 to 1). Higher makes the smoke bend sooner instead of rising as a straight column. |
| Wind turbulence | 0.5 | 0 to 1 | Gusts and swirls: smoke wavers around the wind direction and strength instead of following it smoothly. 0 = off, 1 = strong. |

## Weather

| Setting | Default | Range | What it does |
|---|---|---|---|
| Freezing cap height | 20 | 0 to 200 | In freezing weather smoke stops rising about this many meters above its source and spreads out sideways. 0 = no cap. |
| Cold cap height | 30 | 0 to 200 | Same as the freezing cap, for cold weather. 0 = no cap. |
| Rain decay boost | 0.15 | 0 to 2 | While it is wet, smoke fades this much faster (0.15 = 15% faster). 0 = rain has no effect. |

## Visuals

| Setting | Default | Range | What it does |
|---|---|---|---|
| Smoke size multiplier | 1 | 0.1 to 4 | How big every puff looks. |
| Smoke expansion | 1.6 | 1 to 4 | How many times bigger the smoke looks by the end of its life. Growth starts after a quarter of its life, and after leaving any flue. 1 = no growth. |
| Puff size variance | 0.2 | 0 to 0.6 | Each new puff looks bigger or smaller by up to this fraction (0.2 = plus or minus 20%). 0 = all the same. |
| Flue puff size | 0.7 | 0.2 to 1 | How big puffs look while inside a flue or other cramped space, as a fraction of normal. They ease to full size a few seconds after getting out. 1 = no change. |

## Main Menu

| Setting | Default | Range | What it does |
|---|---|---|---|
| Affect main menu fire | true | - | Also applies the mod to the fire on the main menu screen: spawn rate, lifetime, wind (never toward the camera), rise speed variance and uneven puffs. Takes effect when the menu loads. |

## Performance

| Setting | Default | Range | What it does |
|---|---|---|---|
| Max amount | 150 | 20 to 1000 | Maximum number of smoke objects in the world at once (the game uses 100). When it is reached the oldest smoke fades early. Raise it with Spawn rate multiplier, Lifetime multiplier or Weak fire spawn boost. |
| Detailed range | 40 | 0 to 64 | Smoke farther than this many meters from you skips the wall and path checks and just rises and drifts in the wind. This is the biggest saver in bases with many fires. 0 = detailed checks everywhere. |
| Recheck interval *(advanced)* | 1.5 | 0.5 to 5 | Seconds between environment checks for each nearby puff. Higher is cheaper but makes smoke slower to react to walls and openings. |

## Debug

| Setting | Default | Range | What it does |
|---|---|---|---|
| Debug logging *(advanced)* | false | - | Writes extra lines to the BepInEx log: fire detection and a sample of what smoke decided. Leave off unless asked. |
| Force weather *(advanced)* | Off | - | For testing only. Makes the mod behave as if this weather were active, whatever the game says. |
