# Changelog

## 0.5.0

*Smoke no longer gets stuck in small holes, and it now billows out from the fire.*

- New smoke shape: a new puff starts small and widens quickly, then keeps growing more slowly as it ages. Before, puffs started at full size. Weaker fires start closer to full size, so a last-log fire does not nearly vanish. This is look only.
- Two new settings, **Emerge start size** (default 0.35) and **Emerge time** (default 1.5 seconds). Set the start size to 1 to turn it off.
- **Smoke expansion** now grows fastest at first and slows down as the smoke ages, instead of speeding up in the middle.
- A puff that is stuck in a flue or other cramped space now gets a little smaller with each check, hitbox included, until it slips through. Once it is out, it grows back to full size over a few seconds.
- **Flue puff size** now sets the smallest size a puff shrinks to. Its default is 0.5 (was 0.7). If you already had a saved value, your value is kept. Set it to 1 to turn the shrinking off.
- Removed the two Debug settings (**Debug logging** and **Force weather**). They were only for testing.

## 0.4.0

*Flames have joined the smoke.*

**Important: settings were renamed and regrouped.** Your old values are carried over automatically, and a copy of your original config is saved next to it as `EnigmaPrime.RealisticSmokeRework.cfg.pre-0.4.bak`. After updating, please open your settings (F1) or your config file and check that your old settings still match what you had.

### New: flames follow fuel
- Flames and their light now scale smoothly with the fuel in a fire, from a roaring full fire down to a small flicker on the last log. They stay lit until the game's own out state.
- Adding fuel gives a short flare. The extra "fuel added" particles can be turned off (they are off by default).
- Low fuel fires waver more. This respects the game's Reduce Flashing Lights setting.
- Covers fireplaces, torches, braziers and the like. Handheld torches, smelters, kilns and cooking stations are not touched.

### New: wind and rain on fires
- Strong wind shrinks exposed flames. Weaker fires give in to lower wind, and walls and roofs protect them using the game's own shelter check.
- Blown down campfires, hearths, bonfires and braziers drop to the game's own low flame with its small puffs of smoke. Torches go dark.
- Rain slowly dwindles exposed fires until they look out, with thin wisps of smoke. Covering them brings the flames back.
- All of this is visual only. The game still treats the fire as lit, so nothing changes for other players and fires keep warming and cooking.
- The jack-o-turnip and the snow lantern are sealed, so wind and rain do not affect them.

### Settings
- New numbered sections: General, Global, Flames, Flames wind and rain, Smoke, Smoke visuals, Smoke wind and weather, Performance, Debug.
- Settings that change every fire at once are now in their own Global section and marked (Global).
- Clearer names: the Weak fire settings are now Low fuel (for example Low fuel smoke size), and Fire size effect is now Fuel smoke strength (Global).
- Debug logging is off by default.
- New **Flame effects** switch in General. Turn it off to keep the game's own flames and use the mod for smoke only.

### Performance
- Flames far from you are checked rarely and not animated. Nearby fires cache their shelter results and only do work when something changes.

## 0.3.0
- First public release.
