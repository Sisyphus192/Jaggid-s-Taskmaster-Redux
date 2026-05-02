# Publishing to Steam Workshop

The in-game Mod Editor handles packing and uploading in one step. There is no separate `hpk.exe` step — the Mod Editor builds the `.hpk` and pushes it to Steam Workshop when you click Upload.

## Prerequisites

- Stranded: Alien Dawn installed via Steam.
- Steam logged in to the account that should own the Workshop submission.
- The mod folder lives at `%APPDATA%\Stranded - Alien Dawn\Mods\Jaggid's Taskmaster\` (this clone — local mods override Workshop subscriptions of the same id).

## First-time publish

1. Launch *Stranded: Alien Dawn*.
2. Main menu → **Mod Manager** → **Mod Editor**. The game loads a sandbox map and the companion editor window opens.
3. In the editor's left column, double-click **Jaggid's Taskmaster - Redux** to open the per-mod view.
4. Verify metadata: id `jaggids_taskmaster_redux`, title `Jaggid's Taskmaster - Redux`, no `steam_id` set.
5. Click **Test** to validate the mod loads cleanly (watch the **Messages** pane for `[LUA ERROR]` lines).
6. From the per-mod menu, choose **Upload to Steam Workshop**. The dialog asks for visibility, tags (gameplay/activities tags are already set in metadata), and accepts the Steam Workshop legal agreement.
7. Confirm. Steam packs the folder into a `.hpk`, uploads it, and writes the assigned Workshop file id back into `metadata.lua` as `steam_id`.
8. Commit the metadata change (the new `steam_id` line) so the next push lines up the local repo with the live Workshop submission.

## Updating an existing Workshop submission

1. Make changes locally and commit.
2. Open the Mod Editor as above.
3. Click **Test** to validate.
4. Bump `version` in `metadata.lua` (or let the editor bump it on save; the `1.10-XXX` scheme is `version_major.version_minor-version`).
5. **Upload to Steam Workshop** — because `steam_id` is already set, the editor updates the existing submission rather than creating a new one.
6. Commit any metadata changes the editor wrote (timestamp, version bump).

## Caveats

- **Local version overrides Workshop.** While you're iterating, this folder's version is what loads — useful, but remember to unsubscribe from the Workshop copy if you want to test a clean install.
- **`steam_id` ties this folder to a specific Workshop submission.** If you ever need to publish as a brand-new submission (e.g. transfer to a different account), delete the `steam_id` line first.
- **Don't ship compiled Lua.** Keep `.lua` files as plain text; the engine's packer handles the rest. Compiled `.luac` files in the source tree can confuse the loader.
- **Mod-tools `hpk.exe` is separate.** The general modding reference mentions `hpk create --cripple-lua-files --dont-compress-files` — that's for advanced workflows like extracting and repacking the vanilla `Lua.hpk`. It is *not* the publish path. Workshop publishing goes through the Mod Editor.
- **Achievements.** Subscribers playing this mod still earn Steam achievements normally; only the dev-cheat path disables them.
