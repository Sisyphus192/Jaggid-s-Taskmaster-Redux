# Jaggid's Taskmaster - Redux

A maintenance fork of [**Jaggid's Taskmaster**](https://steamcommunity.com/sharedfiles/filedetails/?id=2972040553) for *Stranded: Alien Dawn*, published with the original author's permission.

The mod adds new schedule assignments and splits several activity groups so they can be prioritized independently in the Activity Planner:

- **Activity Planner splits** — Healing vs. Self-Heal, Hunting vs. Butchering vs. Slaughtering, Scavenging vs. Salvaging, Construction vs. Repair vs. Deconstruction, plus the Handle group split into Rescue / Dismantle / Load / Manipulation.
- **New schedule assignments** — Farm (& Cook), Craft, Scavenge, Science, Build, Sleep (forbids eating), and an override of vanilla Work that drops eating breaks.

## Why this fork exists

The original mod has not been updated since 2023-11-18, and a couple of small description bugs have accumulated. Jaggid has authorized publishing a maintained fork rather than letting the bug reports go unanswered.

All gameplay design, activity-group splits, and schedule writing are Jaggid Edje's. This fork only fixes bugs — see [`CHANGELOG.md`](CHANGELOG.md) for the per-version list.

## Installation

1. Subscribe via Steam Workshop, **or** clone this repo into:
   ```
   %APPDATA%\Stranded - Alien Dawn\Mods\Jaggid's Taskmaster - Redux\
   ```
   (Windows path; on Linux/Proton, `~/.steam/steam/steamapps/compatdata/1324130/pfx/drive_c/users/steamuser/AppData/Roaming/Stranded - Alien Dawn/Mods/`.)
2. Enable **Jaggid's Taskmaster - Redux** in the in-game Mod Manager.
3. Set up your colony's schedule with the new assignments and prioritize the new activity groups in the Activity Planner.

The mod has no required dependencies. It is compatible with `SAD_CommonLib` but does not need it.

## Compatibility notes

- **Don't combine with other mods that adjust activity sets or activity groups.** Per Jaggid's original guidance, this mod heavily reshapes the vanilla `Work`, `Sleep`, `Heal`, `Hunt`, `Scavenge`, `Construct`, and `Handle` presets; another mod doing the same will collide on whichever loads last.
- Survivors scheduled to **Scavenge** will mine, scavenge, and salvage but not haul resources back to base — by design. Leave some `Anything` time in the schedule so other survivors can deliver.
- Save compatibility: changing schedule assignments mid-save is supported, but if you remove this mod from a save the colony's schedules will fall back to the vanilla `Work`/`Sleep` blocks where Redux assignments were used.

## Credits

- **Jaggid Edje** — original mod, all gameplay/content design.
- **Sisyphus192** — bug fixes and maintenance for this fork.

## License

Code and assets remain under the original author's terms. This fork is published with explicit permission from Jaggid Edje. Do not redistribute outside of these terms without contacting the original author.
