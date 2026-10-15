# Enigma's Realistic Smoke Rework

*Now with flames. Yes, it still says smoke.*

Valheim smoke that acts like smoke, and flames that follow their fuel. Smoke rises, finds its way out of rooms, pools under ceilings when it has nowhere to go, bends in the wind, and reacts to the weather. Flames grow with a full fire, shrink as the fuel runs low, and give in to wind and rain. Weak fires puff small and slow. Strong fires pour out big, fast smoke.

Replaces vanilla smoke. Client side, every setting can be changed live in game, and nothing it does touches your saved world.

Only want the smoke? Turn off **Flame effects** in the General settings and the flames go back to the game's own.

**Updating from 0.3.0?** The settings were renamed and regrouped. Your old values are carried over automatically, and a copy of your original config is saved next to it as `EnigmaPrime.RealisticSmokeRework.cfg.pre-0.4.bak`. Open your settings once (F1) and check that your old values still match.

![Smoke column from a campfire bending in the wind](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/hero.png)

## What it looks like

Everything below describes the default settings.

### Vanilla vs Enigma's Realistic Smoke Rework

![Same fire, vanilla smoke on the left and Enigma's Realistic Smoke Rework on the right](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/before-after.gif)

Same fire, same spot. The difference is in how the smoke moves, grows, bends and fades.

### Finding the way out

![Smoke rising out through the roof vent of a building](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/smoke-exit.gif)

Smoke looks at the space around it and heads for the path of least resistance, through gaps, windows and flues, instead of piling against the first ceiling.

### Pooling when there is no way out

![Smoke gathering under the ceiling of a hall](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/smoke-pooling.gif)

With no exit, smoke collects at the highest point and spreads out, then fades.

### Chimneys and flues


Inside narrow spaces smoke gets a gentle pull upward, shrinks a little to fit, and eases back to full size once it is out in the open.

![A tower with a fire at the bottom: smoke climbs the shaft and leaves through the top](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/flue-tower.gif)

### Wind


Wind bends the plume, with gusts and swirls instead of a straight line. Fresh hot smoke is pushed around less than smoke that has cooled.

### Cold and rain

![Smoke flattening out at the cold-weather height cap](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/cold.jpg)

In freezing weather smoke stops climbing at about 20 meters above the fire and spreads out sideways. In cold weather it stops at about 30 meters. Both heights can be changed in the settings. In rain smoke fades faster.

### Fire strength

![Last-log fire next to a full fire, with very different smoke](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/firesize.gif)

A fire on its last log makes small, slow, frequent puffs. A full fire makes big, fast smoke. Fires in between scale smoothly.

### Flames follow fuel

A full fire burns taller and brighter than the game's. As the fuel drops, the flames and their light shrink smoothly instead of staying the same until the last log. A last-log fire is a small, wavering flame. Adding fuel gives a short flare. Weaker fires flicker more, and nothing flickers harder than the game's own Reduce Flashing Lights setting allows.

This covers fireplaces, torches, braziers and the like. Handheld torches, smelters, kilns and cooking stations are not touched.

![A pan across fires with different fuel levels: the flames and their light follow how much fuel is left](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/fuel-flames.gif)

![Adding fuel to a low fire gives a short flare that settles back down](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/refuel-flare.gif)

### Wind and fire

Strong wind on an exposed fire shrinks its flames. A weaker fire gives in to lower wind than a full one. Past that point, campfires, hearths, bonfires and braziers drop to the game's own low flame with its little puffs of smoke, and torches go dark. Walls and roofs protect a fire, using the game's own shelter check. The fire stays lit as far as the game is concerned, so it keeps warming and cooking. Nothing changes for other players.

![Fires shrinking and dropping to the small flame with puffs as the wind rises, then coming back when it drops (sped up)](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/wind-blowout.gif)

### Rain and fire

An exposed fire dwindles the longer it stays in the rain, until it looks out, with only thin wisps of smoke. Get it under cover and the flames come back. Like the wind effect, this is visual only: the game still treats the fire as lit.

The sealed lanterns (jack-o-turnip and snow lantern) ignore wind and rain.

![Exposed fires dwindling in the rain until they look out (sped up)](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/rain-dwindle.gif)

![The flames coming back after the rain stops (sped up)](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/rain-recovery.gif)

## Features

- Smoke finds the path of least resistance out of a room, through gaps and flues.
- With no way out it pools at the highest point.
- Wind bends the plume with gusts and swirls. Hot fresh smoke is less affected than cooled smoke.
- Freezing and cold weather cap how high smoke climbs (about 20 and 30 meters by default, adjustable). Rain makes it fade faster.
- Fire strength matters, from a last-log wisp to a full blaze.
- Smoke is drawn up narrow flues and chimneys and eases out the top without squeezing.
- Puffs vary in size, speed and timing, so smoke comes out in uneven pulses instead of a perfect stream.
- The main menu fire gets the same treatment.
- Flames and light follow the fuel in a fire: a roaring full fire down to a small flicker, with a flare when you add fuel.
- Strong wind shrinks and blows down exposed flames, and weaker fires give in sooner. Shelter protects them.
- Rain slowly dwindles exposed fires until they look out. Covering them brings them back.
- Low fuel flames waver more.
- Over 50 settings, all with sliders in game. Nothing is hardcoded that you would want to change.

## How it works, in plain terms

Each puff of smoke checks the space around it every second or so. It looks for walls, roofs and openings, then steers toward whatever gives it the most room. Heat decides how fast it rises and how much the wind can push it. Cold weather lowers its ceiling. Rain thins it out faster.

Smoke far from you skips the wall checks and just rises and drifts, so a base full of fires stays playable. Flames work the same way: fires far from you are checked rarely and not animated, and nearby fires only do work when something changes.

![Diagram: how a puff of smoke decides where to go](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/diagram.png)

## Download

Install from Thunderstore with r2modman or the Thunderstore app. BepInExPack Valheim is installed automatically:

[https://thunderstore.io/c/valheim/p/Enigma_Prime/Enigmas_Realistic_Smoke_Rework/](https://thunderstore.io/c/valheim/p/Enigma_Prime/Enigmas_Realistic_Smoke_Rework/)

To change settings in game, install Configuration Manager and press F1.

## Settings

Every setting is explained in [docs/CONFIG_REFERENCE.md](docs/CONFIG_REFERENCE.md), including notes for server owners.

## Compatibility

- This mod includes its own smoke collision, so it will not load alongside the Smoke Collision mod. Other mods that change smoke collision cover the same ground and can conflict, so please test your setup if you use more than one.
- Client side. It only changes what each player sees and never touches saved world data. A dedicated server does not need it.
- If you run a server, see the server notes in [docs/CONFIG_REFERENCE.md](docs/CONFIG_REFERENCE.md).

## Performance

Smoke far from you skips the expensive checks, and so do flames. For bases with many fires, lower Detailed range, Max amount or Spawn rate multiplier.

## Support

If you like the mod and want to say thanks, you can buy me a coffee:

[Buy me a coffee on Ko-fi](https://ko-fi.com/enigmaprime)

Bug reports and ideas are just as welcome. Open an issue on [GitHub](https://github.com/RELinkem/Enigmas-Realistic-Smoke-Rework/issues) and include your BepInEx log and your settings file.

## How this mod was made

The ideas, the design, and every decision about how the smoke should look and behave are mine: where it goes, how it reacts to wind and cold, what the settings should be. However, I am not a programmer. The code was written by Claude, an AI assistant made by Anthropic, working from my direction through [Claude Code](https://claude.com/claude-code).

I want to be upfront about that. I am the one who plays the game, so I test every build in Valheim, read the game log for errors, and send back anything that looks or feels wrong until it behaves the way I intended. The code was also checked against Valheim's own code so it hooks in the right places. If you find a bug, please open an issue and I will work on a fix.

Not affiliated with or endorsed by Anthropic.

## Changelog

See [CHANGELOG.md](CHANGELOG.md).

## License

All rights reserved. You are free to download and use the mod, but please don't redistribute, modify or re-upload it without asking first, see [LICENSE](LICENSE). Valheim is the property of Iron Gate AB and Coffee Stain Publishing. This mod is not affiliated with or endorsed by them.
