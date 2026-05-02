# Changelog

## [1.10-169] - 2026-05-02

First Redux release. The initial commit is Jaggid's untouched v1.10-168 source; every change since is a single bug fix.

### Fixed

- **TM-1** — Removed `Cooking` from the `Craft` ActivitySet. The original set enabled `Cooking`, which contradicted the schedule's "no breaks for meals" intent and caused cooks to abandon crafting tasks to prep food. Cooking remains available under the `Farm` (Farm_Cook) assignment, where it belongs.
- **TM-2** — `Scavenge` ActivitySet tooltip typo fixed: `"Scrapping"` → `"Scavenging"`, and the trailing double period reduced to a single full stop.

## [1.10-168]

Last release by Jaggid Edje. Baseline for this fork; see the original [Steam Workshop page](https://steamcommunity.com/sharedfiles/filedetails/?id=2972040553) for its history.
