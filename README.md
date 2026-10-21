# Enigma's Realistic Smoke Rework

*Now with flames. Yes, it still says smoke.*

Smoke that behaves like smoke, and flames that follow their fuel. Smoke rises, finds its way out of rooms, bends in the wind and thins out in the rain. Flames grow with a full fire, shrink as the fuel runs low, and give in to strong wind and rain.

Replaces vanilla smoke. Client side, every setting can be changed live in game, and nothing it does touches your saved world. Only want the smoke? Turn off **Flame effects** in the General settings and the flames go back to the game's own.

<p align="center"><a href="https://thunderstore.io/c/valheim/p/Enigma_Prime/Enigmas_Realistic_Smoke_Rework/"><b>Download</b></a> &nbsp;|&nbsp; <a href="https://github.com/RELinkem/Enigmas-Realistic-Smoke-Rework/blob/main/docs/CONFIG_REFERENCE.md">Settings</a> &nbsp;|&nbsp; <a href="https://github.com/RELinkem/Enigmas-Realistic-Smoke-Rework/issues">Report a bug</a> &nbsp;|&nbsp; <a href="https://github.com/RELinkem/Enigmas-Realistic-Smoke-Rework/blob/main/CHANGELOG.md">Changelog</a></p>

![Smoke column from a campfire bending in the wind](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/hero.png)

> **Updating from 0.3.0?** The settings were renamed and regrouped. Your old values carry over, and a copy of your original config is saved next to it as `EnigmaPrime.RealisticSmokeRework.cfg.pre-0.4.bak`. Open your settings once (F1) and check that your old values still match.

## What it looks like

Everything below describes the default settings.

### Vanilla vs Enigma's Realistic Smoke Rework

![Same fire, vanilla smoke on the left and Enigma's Realistic Smoke Rework on the right](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/before-after.gif)

*Same fire, same spot. The difference is in how the smoke moves, grows, bends and fades.*

### Finding the way out

Smoke looks at the space around it and heads for the most open way out, through gaps, windows and flues, instead of piling against the first ceiling. If it cannot get out right away, it collects at the highest point, spreads out, then finds the opening and leaves.

![Smoke pooling under a raised part of the roof, then leaving through the opening](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/smoke-pooling.gif)

*From inside: smoke gathers under the raised roof, then heads for the opening.*

![Smoke leaving a building through an exit far from the fire](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/smoke-exit.gif)

*From outside: it finds its way out even when the exit is far from the fire.*

### Chimneys and flues

Narrow spaces give smoke a gentle pull upward. A puff that gets stuck shrinks a little more with each check, hitbox included, until it slips through, then grows back to full size outside.

![A tower with a fire at the bottom: smoke climbs the shaft and leaves through the top](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/flue-tower.gif)

### Wind

Wind bends the plume with gusts and swirls. Fresh hot smoke is pushed around less than smoke that has cooled. Vanilla smoke mostly just rises. With the mod, it drifts downwind.

![Vanilla on the left, the mod on the right: indoors, smoke drifts toward the downwind side with the mod](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/wind-inside.gif)

*Indoors.*

![Vanilla on the left, the mod on the right: outdoors, smoke is carried downwind with the mod](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/wind-outside.gif)

*Outdoors.*

### Cold and rain

![Smoke flattening out at the cold-weather height cap](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/cold.jpg)

In freezing weather smoke stops climbing at about 20 meters above the fire and spreads out sideways, and in cold weather at about 30 meters. Both heights can be changed in the settings. In rain smoke fades faster.

### Fire strength

The fuel in a fire sets the size of its smoke and its flames together. A last-log fire makes small, slow puffs and a small wavering flame. A full fire makes big, fast smoke and tall, bright flames. Fires in between scale smoothly.

![A full fire with full smoke next to a weak fire with weak smoke](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/firesize.gif)

### Flames follow fuel

A full fire burns taller and brighter than the game's. As the fuel drops, the flames and their light shrink smoothly instead of staying the same until the last log. Adding fuel gives a short flare. Weaker fires flicker more, and nothing flickers harder than the game's own Reduce Flashing Lights setting allows.

![A pan across fires with different fuel levels: the flames and their light follow how much fuel is left](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/fuel-flames.gif)

*This covers fireplaces, torches, braziers and the like. Handheld torches, smelters, kilns and cooking stations are not touched.*

Add fuel to a low fire and it flares up for a moment, then settles back to the size that fits its new fuel level.

![Adding fuel to a low fire gives a short flare that settles back down](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/refuel-flare.gif)

*Refueling a low fire.*

### Wind and fire

Strong wind on an exposed fire shrinks its flames. A weaker fire gives in to lower wind than a full one. Past that point, campfires, hearths, bonfires and braziers drop to the game's own low flame with its little puffs of smoke, and torches go dark. Walls and roofs protect a fire, using the game's own shelter check. The fire stays lit as far as the game is concerned, so it keeps warming and cooking. Nothing changes for other players.

![Fires shrinking and dropping to the small flame with puffs as the wind rises, then coming back when it drops (sped up)](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/wind-blowout.gif)

### Rain and fire

An exposed fire dwindles the longer it stays in the rain, until it looks out, with only thin wisps of smoke. Get it under cover and the flames come back. Like the wind effect, this is visual only: the game still treats the fire as lit. The sealed lanterns (jack-o-turnip and snow lantern) ignore wind and rain.

![Exposed fires dwindling in the rain until they look out (sped up)](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/rain-dwindle.gif)

![The flames coming back after the rain stops (sped up)](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/rain-recovery.gif)

## Features

**Smoke**
- Finds the way out of a room, or pools under the ceiling when there is none.
- Wind, cold and rain change how it moves and how long it lasts.
- Fire strength changes puff size, speed and timing, so smoke comes out in uneven pulses.
- Narrow flues and chimneys pull smoke up and out. The main menu fire gets the same treatment.

**Flames**
- Flames and light follow the fuel, from a roaring fire down to a small flicker, with a flare when you add fuel.
- Strong wind blows down exposed flames, rain dwindles them, and shelter protects them.

**Settings**
- Over 50 settings, all with sliders in game.

## How it works

Each puff of smoke checks the space around it every second or so. It looks for walls, roofs and openings, then steers toward whatever gives it the most room. Heat decides how fast it rises and how much the wind can push it. Cold weather lowers its ceiling. Rain thins it out faster.

Smoke far from you skips the wall checks and just rises and drifts, so a base full of fires stays playable. Flames work the same way: fires far from you are checked rarely and not animated, and nearby fires only do work when something changes.

![Diagram: how a puff of smoke decides where to go](https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/diagram.png)


## Download

Install from Thunderstore with r2modman or the Thunderstore app. BepInExPack Valheim is installed automatically:

[https://thunderstore.io/c/valheim/p/Enigma_Prime/Enigmas_Realistic_Smoke_Rework/](https://thunderstore.io/c/valheim/p/Enigma_Prime/Enigmas_Realistic_Smoke_Rework/)

To change settings in game, install Configuration Manager and press F1.

## Settings

Every setting is explained in [docs/CONFIG_REFERENCE.md](https://github.com/RELinkem/Enigmas-Realistic-Smoke-Rework/blob/main/docs/CONFIG_REFERENCE.md), including notes for server owners.

## Multiplayer and servers

Client side only. It only changes what each player sees and never touches saved world data. A dedicated server does not need it. If you run a server, see the server notes in [docs/CONFIG_REFERENCE.md](https://github.com/RELinkem/Enigmas-Realistic-Smoke-Rework/blob/main/docs/CONFIG_REFERENCE.md).

## Compatibility

- This mod includes its own smoke collision, so it will not load alongside the Smoke Collision mod. Other mods that change smoke collision cover the same ground and can conflict, so please test your setup if you use more than one.

## Performance

Smoke far from you skips the expensive checks, and so do flames. For bases with many fires, lower Detailed range, Max amount or Spawn rate multiplier.

## Support

<a href="https://ko-fi.com/enigmaprime"><img src="https://raw.githubusercontent.com/RELinkem/Enigmas-Realistic-Smoke-Rework/main/images/Ko-Fi-badge-web.png" alt="I asked AI for help and it told me to get Ko-fi" width="220" align="left" hspace="16"></a>

If you like the mod and want to say thanks, you can:<br>[buy me a coffee on Ko-fi](https://ko-fi.com/enigmaprime)

<br clear="left">

Bug reports and ideas are just as welcome. Open an issue on [GitHub](https://github.com/RELinkem/Enigmas-Realistic-Smoke-Rework/issues) and include your BepInEx log and your settings file.

## More mods by Enigma Prime

<a href="https://thunderstore.io/c/valheim/p/Enigma_Prime/Enigmas_Item_Salvager/"><img src="https://raw.githubusercontent.com/relinkem/Enigmas-Item-Salvager/main/Release/icon.png" alt="Enigma's Item Salvager icon" width="96" align="left" hspace="16"></a>

**[Enigma's Item Salvager](https://thunderstore.io/c/valheim/p/Enigma_Prime/Enigmas_Item_Salvager/)**<br>Take your gear apart at the Workbench, Forge, Black Forge or Galdr Table and get some of the materials back.

<br clear="left">

<a href="https://thunderstore.io/c/valheim/p/Enigma_Prime/Enigmas_Useful_Tasty_Mead/"><img src="https://raw.githubusercontent.com/relinkem/Enigmas-Useful-Tasty-Mead/main/Release/icon.png" alt="Enigma's Useful Tasty Mead icon" width="96" align="left" hspace="16"></a>

**[Enigma's Useful Tasty Mead](https://thunderstore.io/c/valheim/p/Enigma_Prime/Enigmas_Useful_Tasty_Mead/)**<br>A sweet mead that makes your food count as freshly eaten again, lifting your max health, stamina and Eitr before fading back.

<br clear="left">

<a href="https://thunderstore.io/c/valheim/p/Enigma_Prime/Enigmas_Enhanced_Forging/"><img src="https://raw.githubusercontent.com/relinkem/Enigmas-Enhanced-Forging/main/Release/icon.png" alt="Enigma's Enhanced Forging icon" width="96" align="left" hspace="16"></a>

**[Enigma's Enhanced Forging](https://thunderstore.io/c/valheim/p/Enigma_Prime/Enigmas_Enhanced_Forging/)**<br>Smelters, kilns and the Eitr refinery become walk-away machines with inventory screens, a Light button and winding animations.

<br clear="left">

## How this mod was made

The ideas, the design, and every decision about how the smoke should look and behave are mine: where it goes, how it reacts to wind and cold, what the settings should be. However, I am not a programmer. The code was written by Claude, an AI assistant made by Anthropic, working from my direction through [Claude Code](https://claude.com/claude-code).

I want to be upfront about that. I am the one who plays the game, so I test every build in Valheim, read the game log for errors, and send back anything that looks or feels wrong until it behaves the way I intended. The code was also checked against Valheim's own code so it hooks in the right places. If you find a bug, please open an issue and I will work on a fix.

Not affiliated with or endorsed by Anthropic.

## Changelog

See [CHANGELOG.md](https://github.com/RELinkem/Enigmas-Realistic-Smoke-Rework/blob/main/CHANGELOG.md).

## License

All rights reserved. You are free to download and use the mod, but please don't redistribute, modify or re-upload it without asking first, see [LICENSE](https://github.com/RELinkem/Enigmas-Realistic-Smoke-Rework/blob/main/LICENSE). Valheim is the property of Iron Gate AB and Coffee Stain Publishing. This mod is not affiliated with or endorsed by them.
