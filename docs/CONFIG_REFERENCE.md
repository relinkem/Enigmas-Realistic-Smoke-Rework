# Enigma's Realistic Smoke Rework: settings reference

Version 0.5.0, 54 settings.

All settings are in `BepInEx/config/EnigmaPrime.RealisticSmokeRework.cfg` and can also be changed live in game with Configuration Manager (F1). Settings marked *advanced* only show in F1 when "Show advanced settings" is ticked.

## Notes for server owners

- The mod runs on each player's own game and only changes what that player sees. A dedicated server does not need it, and it never changes saved world data. The flame, wind and rain effects are visual only and never change whether a fire is lit.
- The one setting that touches gameplay is **Required space** (section 5 Smoke). Smelters, kilns and similar stations use the same check to decide whether they are blocked, so every player on a server should use the same value (or leave it at the default).
- Settings are not synced between players. To keep everyone consistent, give players the same `EnigmaPrime.RealisticSmokeRework.cfg`.
- For a base with many fires, the biggest performance levers are **Detailed range**, **Max amount** and **Spawn rate multiplier**.

## 1 General

| Setting | Default | Range | What it does |
|---|---|---|---|
| Enabled | true | - | Master switch for the whole mod. When off, smoke and flames behave exactly like the unmodded game (including the main menu fire). |
| Flame effects | true | - | Master switch for every flame change: fuel size and light, refuel flare, wind and rain. Off = the game's own flames, smoke only. Visual only. |
| Affect main menu fire | true | - | Also applies the mod to the fire on the main menu screen: spawn rate, lifetime, wind (never toward the camera), rise speed variance and uneven puffs. Takes effect when the menu loads. |
| Extra ignored object ids *(advanced)* |  | - | Extra prefab names (separated by comma) that smoke passes straight through, added to the built-in list (grates, ladders, stairs and similar). Example: wood_gate,wood_door |

## 2 Global

| Setting | Default | Range | What it does |
|---|---|---|---|
| Fuel flame strength (Global) | 1 | 0 to 1 | How strongly a fire's fuel level changes its flames: size, light and particles. 0 = every fire looks like the game's, 1 = full strength. To turn all flame changes off, use Flame effects in General. Visual only. |
| Fuel smoke strength (Global) | 1 | 0 to 1 | How much a fire's fuel level changes its smoke: puff size, rise speed and puff rate (the three Low fuel smoke settings). 0 = every fire's smoke looks the same, 1 = full strength. |
| Smoke size multiplier (Global) | 1 | 0.1 to 4 | How big every puff of smoke looks. |
| Lifetime multiplier (Global) | 2.5 | 0.1 to 5 | How long all smoke lasts before it fades, relative to the game. Longer smoke travels farther and needs a higher Max amount. |
| Spawn rate multiplier (Global) | 2 | 0.1 to 10 | How often all fires and chimneys release smoke, relative to the game. 2 = twice as often. More smoke costs performance. |
| Acceleration multiplier (Global) *(advanced)* | 1.5 | 0.1 to 10 | How quickly all smoke reaches its target speed, relative to the game. 2 = twice as snappy. Applies to new puffs. |
| Collider size multiplier (Global) | 1 | 0.1 to 2 | Scales how much room every puff needs to move, without changing how it looks. Lower it if smoke gets squeezed in tight flues. Applies to new puffs. |

## 3 Flames

| Setting | Default | Range | What it does |
|---|---|---|---|
| Full fuel flame height | 1.75 | 1 to 2 | How big flames get on a full fire, as a multiple of the game's. 1 = same as the game, higher makes full fires rage. Visual only. |
| Low fuel flame height | 0.4 | 0.1 to 1 | How small flames get on a nearly empty fire, as a fraction of the game's. Visual only. |
| Full flame fuel level | 1 | 0.05 to 1 | Fuel level (0 to 1, as a fraction of the fire's maximum) where flames are at full height. 1 = only a completely full fire is at full height, and flames shrink steadily from there. Visual only. |
| Low flame fuel level | 0.2 | 0 to 0.9 | Fuel level where flames and light reach their lowest. Below it they stay there until the fuel runs out and the game puts the fire out. 0.2 = two logs on a campfire. Visual only. |
| Flame height curve | 1 | 0.3 to 3 | Shape of the shrink between the two fuel levels above. 1 = steady, the same amount per log. Higher keeps flames bigger for longer and drops them faster near the end. Lower does the opposite. Visual only. |
| Full fuel light | 1 | 1 to 2 | How bright the light from a full fire is, as a multiple of the game's. 1 = same as the game. Visual only. |
| Low fuel light | 0.45 | 0.05 to 1 | How bright the light is on a nearly empty fire, as a fraction of the game's. Light dims smoothly with the flames down to this. Visual only. |
| Refuel flare | 0.4 | 0 to 1 | When logs are added, flames and light briefly get this much bigger and brighter on top of what the fuel level gives (0.4 = 40% more), then settle back. 0 = off. Visual only. |
| Refuel flare hold | 2.5 | 0 to 10 | Seconds the refuel flare stays at full strength. Visual only. |
| Refuel flare fade | 1.5 | 0.1 to 5 | Seconds the refuel flare takes to fade back to normal after the hold. Visual only. |
| Low fuel flicker | 3 | 1 to 5 | How unsteady the light is on a nearly empty fire, as a multiple of the game's flicker. 1 = same as the game. It builds up as the fuel drops, and also while a fire is blown down or soaked by rain. Does nothing if Reduce Flashing Lights is on in the game's settings. Visual only. |
| Fuel puff particles | false | - | The extra puff of particles the game shows when you add fuel. Off = no puff (any sound is kept). On = the game's normal puff. Applies to fires that load after the change, so reload the area or restart. Visual only. |

## 4 Flames wind and rain

| Setting | Default | Range | What it does |
|---|---|---|---|
| Enhanced wind blowout | Visual only | Off / Visual only | How exposed fires react to strong wind. Low fuel gives in sooner, shelter protects. Off = game default. On (Visual only) = flames shrink or go dark but the fire stays lit, and nothing changes for other players or the server. Sealed lanterns ignore wind. |
| Low fuel wind blowout | 0.35 | 0.1 to 0.8 | Wind strength (0 to 1) that blows out an exposed fire at its Low flame fuel level or less. A full fire holds until the game's own 0.8. Fires in between follow the same curve as their flame height. |
| Wind flame shrink | true | - | Flames of an exposed fire shrink steadily as the wind rises, before any blowout. Off = flames ignore wind until the blowout. Sheltered fires are never affected. Visual only. |
| Wind flame shrink amount | 0.6 | 0 to 1 | How far wind shrinks exposed flames before the blowout. 0 = not at all, 1 = all the way down to the blown-down size just before it. Visual only. |
| Wind flame start | 0.2 | 0 to 0.7 | Wind strength (0 to 1) where exposed flames start to shrink. Fires with less fuel reach their blowout wind sooner, so they shrink faster. Visual only. |
| Rain flame shrink | true | - | Exposed fires dwindle in rain until they look out, with thin smoke wisps. Cover brings them back. Sheltered fires and sealed lanterns are unaffected. Visual only: the fire still warms and cooks. |
| Rain dwindle time | 180 | 20 to 1200 | Seconds of steady rain it takes an exposed full fire to dwindle until it looks out. Wind and low fuel make it faster, so a weak fire in a storm goes much sooner. 180 = three minutes. Visual only. |

## 5 Smoke

| Setting | Default | Range | What it does |
|---|---|---|---|
| Required space | 0.5 | 0 to 2 | Clear space needed above a fireplace, in meters, before it will release smoke (the game uses about 0.75). 0 turns the check off. GAMEPLAY: this is the same check smelters, kilns and similar stations use to decide they are blocked, so on a server every player should use the same value. |
| Low fuel smoke size | 0.42 | 0.03 to 1 | How big the puffs of a nearly empty fire (one log or less) look, as a fraction of normal. A full fire is normal size, fires in between scale smoothly. Visual only. 1 = no change. |
| Low fuel smoke speed | 0.38 | 0.1 to 1 | How fast the smoke of a nearly empty fire (one log or less) rises, as a fraction of normal. A full fire rises a little faster than normal. 1 = no change. |
| Low fuel puff rate | 6 | 1 to 6 | How many times more often a nearly empty fire (one log or less) releases puffs than a full fire, so its small slow puffs make a steady stream. 1 = no change. High values mean more smoke objects, so raise Max amount with it. |
| Spawn timing variance | 0.3 | 0 to 0.9 | Random variation in the time between puffs (0.3 = plus or minus 30%) so smoke comes out in uneven pulses. The average rate stays the same. 0 = perfectly even. |
| Rise speed | 1.5 | 0 to 10 | Starting upward speed of fresh smoke in meters per second. It still slows as the smoke ages. The game uses 1. |
| Rise speed variance | 0.2 | 0 to 0.5 | Each new puff rises this fraction faster or slower (0.2 = plus or minus 20%), so some smoke overtakes other smoke. 0 = all the same. |
| Chimney pull | 0.5 | 0 to 5 | Extra upward speed (meters per second) for smoke inside narrow spaces like flues, so it is drawn out of the tube. A little stronger in wind. 0 = off. |

## 6 Smoke visuals

| Setting | Default | Range | What it does |
|---|---|---|---|
| Smoke expansion | 1.6 | 1 to 4 | How many times bigger the smoke looks by the end of its life. Growth starts after a quarter of its life, and after leaving any flue. It grows fastest at first and slows down as the smoke ages. 1 = no growth. |
| Puff size variance | 0.2 | 0 to 0.6 | Each new puff looks bigger or smaller by up to this fraction (0.2 = plus or minus 20%). 0 = all the same. |
| Flue puff size | 0.5 | 0.2 to 1 | Smallest size a puff shrinks to (look and hitbox, as a fraction of normal) when it is stuck in a flue or other cramped space. It gets a little smaller each check until it escapes, then grows back to full size over a few seconds. 1 = no shrinking. |
| Emerge start size | 0.35 | 0.1 to 1 | How big a new puff looks the moment it leaves the fire, as a fraction of normal. It widens to full size over Emerge time, so smoke starts narrow and fans out as it rises. Weaker fires start closer to full size. Visual only. 1 = no emerging. |
| Emerge time | 1.5 | 0.2 to 5 | Seconds a new puff takes to widen from its start size to full size. It grows fastest at first, then eases off. Visual only. |

## 7 Smoke wind and weather

| Setting | Default | Range | What it does |
|---|---|---|---|
| Wind drift speed | 2.5 | 0 to 5 | Sideways speed (meters per second) of cooled smoke in full wind. Higher bends the smoke more. 0 = wind has no effect (also on the main menu). |
| Early wind effect *(advanced)* | 0.5 | 0 to 1 | How much of the wind fresh, hot smoke feels (0 to 1). Higher makes the smoke bend sooner instead of rising as a straight column. |
| Wind turbulence | 0.3 | 0 to 1 | Gusts and swirls: smoke wavers around the wind direction and strength instead of following it smoothly. 0 = off, 1 = strong. |
| Freezing cap height | 20 | 0 to 200 | In freezing weather smoke stops rising about this many meters above its source and spreads out sideways. 0 = no cap. |
| Cold cap height | 30 | 0 to 200 | Same as the freezing cap, for cold weather. 0 = no cap. |
| Rain decay boost | 0.25 | 0 to 2 | While it is wet, smoke fades this much faster (0.25 = 25% faster). 0 = rain has no effect. |

## 8 Performance

| Setting | Default | Range | What it does |
|---|---|---|---|
| Max amount | 200 | 20 to 1000 | Maximum number of smoke objects in the world at once (the game uses 100). When it is reached the oldest smoke fades early. Raise it with Spawn rate multiplier, Lifetime multiplier or Low fuel puff rate. |
| Detailed range | 40 | 0 to 64 | Smoke farther than this many meters from you skips the wall and path checks and just rises and drifts in the wind. This is the biggest saver in bases with many fires. 0 = detailed checks everywhere. |
| Recheck interval *(advanced)* | 1.5 | 0.5 to 5 | Seconds between environment checks for each nearby puff. Higher is cheaper but makes smoke slower to react to walls and openings. |
