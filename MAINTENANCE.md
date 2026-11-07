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

Current binary/source snapshot: 6b9435faf4dc8426c882829c2b4f2e7984a8b400,
assembly 0.1.4.0, API 15. Public assets are the exact tested private-release ZIPs.
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
  09f2bae5548500faabfa50d46a5624ff6986da198d2d8fd5e52467f7f7ee041a
- KeybindProfiles-0.1.4-source.zip:
  c155c7e04492e71226f19e93dbdfbc5328d7ccc577cce69b580572dd253e423c

## Rollback

Revert the index commit to a previous version and verify old assets still work.
Do not delete releases already referenced by installed feeds. Users replacing
the old Potion-only URL should use just the combined feed to avoid duplicate
entries. Dev-DLL users must disable that copy before installer installation;
personal configuration files must not be deleted or replaced by the manifest.
