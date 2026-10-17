# UXBA User Guide

[Home](../README.en.md) · [日本語](USER_GUIDE.ja.md)

## Getting started

Extract the entire release ZIP and run `UltimateXIVBattleAnalyzer.exe`. Keep the included files and folders together. If prompted, install [.NET 8 Desktop Runtime for Windows x64](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) and [WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/).

Keep your original DATs and save processed results as separate files. Available operations depend on the DAT format and its current state.

## Open and save a DAT

1. Click the DAT load button and choose a DAT, or a ZIP containing one DAT.
2. Review the recording information, players and battles.
3. Set the operations you need, then save as a DAT or ZIP.

Saving without selecting a battle row processes the whole recording. Use the language control at the top right to switch between Japanese and English.

## Extract a battle

1. Open a modern DAT and select the battle interval to keep.
2. Click Save and review the confirmation.
3. Choose the output location and DAT or ZIP format.

Convert supported older recordings first with Past to Modern. An anonymized DAT cannot be extracted again. To extract and anonymize together, select both operations on the original DAT before saving.

## Before publishing or sharing

**Before publishing or sharing a DAT, always check that data from the same battle is not publicly available on FF Logs or similar services.** Even after names, IDs, and appearance are changed, action sequences, timestamps, and battle duration can form a combat fingerprint that may be matched to public logs and used to infer who took part. Anonymization does not guarantee complete anonymity.

## Anonymize names

1. Open a modern DAT that has not been anonymized.
2. Enable player-name anonymization.
3. Save to a separate file.

Names become English job names, while the app displays labels such as `Player 01`. Character and home-world identifiers and the recording date are also changed. Titles are removed, and the party leader is set to the first tank. Appearance stays the same. Anonymization also puts a tank first.

## Change appearance with appearance anonymization

1. Open an original modern DAT and open Appearance Anonymization.
2. Turn Appearance Anonymization on.
3. Choose race, gender, height, outfit and headgear settings.
4. Close the settings, keep name anonymization enabled, and save.

This changes names and appearance together. Removing headgear uses a standard face and different hairstyles for each person; Roegadyn use no hair. Dyeable armor uses class/job colors. Weapons and shields are undyed. The settings also apply to equipment changes during the recording. The Phoenix outfit uses Vanguard weapons for supported jobs.

Choosing settings does not change the original DAT. To change the settings after anonymization, start again from the original.

## Convert older DATs

Choose Past to Modern, select a DAT or a ZIP containing a DAT, and follow the prompts to save a separate file. Check the conversion result for support status.

For multiple files, use batch conversion.

1. Select an input folder and a separate output folder.
2. Subfolders are included, and their structure is preserved in the output.
3. Check the completion report for converted and skipped files and their reasons.

Unsupported DATs, DATs already in the current format, and files whose output name already exists are skipped. Originals and existing outputs are not overwritten. Canceling leaves completed outputs in place.

## Change character ID

This adapts a recording made by someone else to your character. Prepare a reference DAT recorded with your own character.

1. Open the DAT to change and choose Change Character ID.
2. Select your own reference DAT.
3. Choose an output location and save a separate file.

Do not mix up the reference and target files.

## Extract matching ACT logs

You need the ACT logs from the original recording. This feature does not generate new ACT logs from a DAT.

1. Choose the DAT to ACT log search and split operation.
2. Select the original DAT before anonymization.
3. Select the ACT log folder. Subfolders and supported log ZIPs are searched too.
4. Select an output location and review the extracted logs.

Use the FF Logs uploader if you want to publish the logs. DAT anonymization does not anonymize ACT logs.

## Organize older DATs into individual ZIPs

Choose individual ZIP compression, then select separate input and output folders. Supported older DATs are stored in individual ZIPs and organized by recording generation and content.

Original DATs remain in place. Modern DATs are excluded. Identical ZIPs are skipped; different content with the same filename is saved under a different name. Compression alone does not anonymize a recording.

## Output filename labels

The operations you apply add labels before the original filename.

| Label | Meaning |
| --- | --- |
| `Miqo(M)`, etc. | Race and gender (M = male, F = female) |
| `S`, `M`, `L` | Height |
| `RB`, etc. | Outfit |
| `Head(on)`, `Head(off)` | Headgear on or off |
| `Anon` | Name anonymization |
| `Split` | Battle extraction |

## Troubleshooting and reports

If the app does not start, check that the entire ZIP was extracted and the required runtimes are installed. For dictionary errors, extract all included files again.

In a [bug report](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/issues/new/choose), include the app version, steps, symptoms and error message. If conversion or another operation fails on a DAT, send the original DAT and a description through the [Dropbox upload form](https://www.dropbox.com/request/gkofh48datowq9uozjif). Include the issue URL if you have one.


[Usage questions](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/discussions) · [Support development](SUPPORT.en.md)
