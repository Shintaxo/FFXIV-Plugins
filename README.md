# Shintaxo's Dalamud plugins

One custom Dalamud repository for **Potion Tracker** and **Keybind Profiles**.
This is an unofficial third-party repository, not the official Dalamud catalog.

## Install

1. Open /xlsettings → Experimental → Custom Plugin Repositories.
2. Add and enable:

   https://raw.githubusercontent.com/Shintaxo/FFXIV-Plugins/main/pluginmaster.json

3. Refresh /xlplugins and install Potion Tracker and/or Keybind Profiles.

If you used the Potion-Tracker-only URL, replace it with this combined URL; do
not enable both feeds simultaneously. Already-installed Potion Tracker keeps its
InternalName, version and upstream download URL. No config migration is required.
The old Potion Tracker feed and releases remain unchanged.

If Keybind Profiles was loaded as a development DLL, disable it and remove its
Dev Plugin Location before installing the feed version. Do not load both copies.
Keep your existing plugin configuration and profiles. Back up game settings first.

## Plugins

### Potion Tracker — 0.4.4

Tracks locally observed party potion use per pull. Source and downloads remain
in [FFXIV-Potion-Tracker](https://github.com/Shintaxo/FFXIV-Potion-Tracker).
No detected onset does not prove that a player did not use a potion.

### Keybind Profiles — 0.1.5 SESSION-ONLY HOTFIX

Save and explicitly apply character-specific primary hotbar keybind profiles.

**WARNING: bindings may revert after logout or a game restart. You may need to
manually apply your desired profile again after logging in.** 0.1.5 disables explicit native file saving after the 0.1.4 save guard blocked
profile use. This restores session-only operation; it is NOT a restart-persistence fix.

If upgrading with an old pending backup: keep all saved profiles, update, click
**Undo profile switch** on the same character, then preview/apply the desired profile.
The recovery may restore original primary bindings; it does not delete saved profiles.
If a save/recovery error is pending, preserve the backup and inspect the error;
do not repeatedly apply profiles.
No automatic application on login and no automatic job switching.

**Hinweis: Nach Ausloggen oder Spielneustart können alte Keybinds zurückkehren.
Das gewünschte Profil muss dann möglicherweise erneut manuell angewendet werden.**
Vorher Spiel-Einstellungen und Plugin-Konfiguration sichern.

Managed safety, profile and SDK/migration checks and a Windows CI build passed.
These do not prove native disk persistence or successful installation in your game.

The [experimental release](https://github.com/Shintaxo/FFXIV-Plugins/releases/tag/keybindprofiles-v0.1.5)
contains the ready-built ZIP, installation instructions, license and matching
source archive. The source project repository remains private; the corresponding
source snapshot is publicly provided with this distribution under AGPL-3.0.

## Updates and licensing

Dalamud can fetch the version advertised in pluginmaster.json through the normal
custom-repository installer/update path. Future releases still require a deliberate
feed update by the maintainer; no automatic build/publication service is implied.

Potion Tracker's upstream repository controls its license. Keybind Profiles is
AGPL-3.0: see LICENSE.md and the exact corresponding source ZIP alongside each
Keybind release. This distribution repository does not relicense either plugin.

[Maintainer instructions](MAINTENANCE.md)
