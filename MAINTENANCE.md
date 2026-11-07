# Distribution maintenance

This repo is the public distribution index, not a replacement for either source
repository. Never publish personal plugin configuration, credentials or chat logs.

## Potion Tracker

Its authoritative release/feed remains Shintaxo/FFXIV-Potion-Tracker. Before a
release here, freshly read its pluginmaster.json, copy only the PotionTracker
entry into this feed and preserve the KeybindProfiles entry. Do not blindly
replace the entire combined feed with the upstream single-plugin file.
The combined feed is not automatically synchronized; update it with new Potion
releases. Current baseline: version 0.4.4.0, original upstream URLs unchanged.

## Keybind Profiles

Current binary/source snapshot: 4a7a923403381f202c8ac07f28dee3952a1347ce,
assembly 0.1.4.0, API 15. Public assets are sanitized Release rebuilds; runtime logic is unchanged.
Do not remove the experimental/restart warning without successful live acceptance.
The original source repository stays private; corresponding source ZIP + AGPL
license must remain available alongside each distributed binary.

Update sequence:
1. Build and run safety, profile and SDK/migration checks on the exact commit.
2. Audit ZIP allowlist, manifest identity/version/API and matching source for
   accidental private data. Record SHA256 checksums.
3. Upload plugin and source assets to a new experimental release tag first.
4. Update this feed's versions, install/update URLs and LastUpdate, retaining
   other entries. Keep InternalName stable across updates.
5. Fetch the raw feed and both plugin install URLs without GitHub credentials.
   Check HTTP success, ZIP integrity and manifest identity/version/API.
6. Publish only after all URLs work. Keep previous releases for rollback.

No new scheduler, automatic publisher or credentials are configured here.
Do not run private-source repository release workflows from this index repo.

## Initial binary hashes

- KeybindProfiles-0.1.4-test.zip:
  a6867f67152fb9f8a228e3c55e723df98682abd6a38dd97192b15a62c3ad84f5
- KeybindProfiles-0.1.4-source.zip:
  580f50f9e6d611e1a20cd7d0ff3a0c03d6c9a8fc743e619986dfc6adad074581

## Rollback

Revert the index commit to a previous version and verify old assets still work.
Do not delete releases already referenced by installed feeds. Users replacing
the old Potion-only URL should use just the combined feed to avoid duplicate
entries. Dev-DLL users must disable that copy before installer installation;
personal configuration files must not be deleted or replaced by the manifest.
