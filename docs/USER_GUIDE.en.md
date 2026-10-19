# UltimateXIVBattleAnalyzer

[Home](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer) · [English](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/blob/main/docs/USER_GUIDE.en.md)

## Basics

UltimateXIVBattleAnalyzer is a Windows application for loading, viewing, and organizing FFXIV replay DAT files. It supports recordings from dungeons, trials, raids, and alliance raids. Some files may not be readable or editable, depending on the DAT format generation and recording conditions.

### Launching the App and Loading a DAT

1. Extract the entire distribution ZIP into a folder, then launch `UltimateXIVBattleAnalyzer.exe`.
2. Click "Load DAT" and select a DAT file or a ZIP containing a single DAT file.
3. Check the recording information, player list, and battle list.

The app is intended for 64-bit Windows. Keep the bundled dictionary and folders in their original locations. If prompted at startup, install the [.NET Desktop Runtime (Windows x64)](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) and [WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/). You can switch between Japanese and English in the upper-right corner.

### Information Displayed

- Date and time recorded in the DAT, clear status, and party composition
- Playback time / recording time, number of battles, and Duty ID
- Player list and battle list

The date and time come from the data inside the DAT, not its filename. For anonymized DAT files, the displayed date, time, and character information reflect the modified data.

### Saving

Configure the desired operations and click "Save" to export a DAT or ZIP. If no battle is selected, the entire recording is saved. If a battle row is selected, only that battle segment is saved. Simply changing the settings does not modify the original DAT. Keep a copy of the original DAT and save modified results as separate files.

## DAT → ACT Log Search → Formal Split

Find the ACT log corresponding to a replay and extract only that battle from a log containing multiple fights. This prepares a log that can be uploaded to FF Logs.

1. Click "DAT → ACT Log Search → Formal Split" and select the original DAT before anonymization.
2. Select the ACT log folder. Subfolders and supported log ZIP files are also searched.
3. If a matching log is found, choose an output location and extract it.
4. Review the extracted log and upload it using the FF Logs uploader.

You need the ACT log from when the replay was recorded. This feature does not generate a new ACT log from a DAT file. DAT anonymization is not applied to ACT logs.

## Experimental Features

The following editing features are experimental. Some DAT files cannot be processed due to missing information, and bugs may occur. Check the saved results before using them.

### Anonymization and Appearance Anonymization

Anonymizes much of the personally identifying information about party members contained in the DAT, including names, character IDs, and portraits. The recording date and time are also set to a predetermined value.

"Appearance Anonymization" lets you choose race, gender, height, and several outfit options. When headgear is removed, a random hairstyle is assigned to each character.

*Male Roegadyn characters are always bald.*

1. Open a current-format DAT that has not been anonymized.
2. Open "Appearance Anonymization," turn it ON, and configure the appearance. If you want to anonymize without changing appearances, use the anonymization option on the main screen.
3. If needed, also select a battle segment, change the recorder, or enable the end-of-fight cut, then save to a separate file.

During anonymization, the original recorder's information is transferred to the first person in the party list, and the list is arranged so that person appears at the top. Information associated with the original recorder, such as marker placement, countdowns, and party leader information, is also transferred. This feature does not swap individual players' combat movement or jobs.

The only additional change supported on an already anonymized DAT is "Change Recorder." To change appearances or extract a battle segment again, start with the original DAT before anonymization.

### Change Recorder

Turn ON "Change Recorder," select a person from the player list, and save. The selected party member becomes the recorder, local player, and party leader. This also works with anonymized DAT files received from other people.

If a Splatoon script uses the recorder or local player to determine its behavior, we recommend selecting the intended character. The local player is the character that scripts and other systems refer to as "self."

When used together with anonymization, the selected person takes priority as the recorder and party leader. The selection is cleared when another DAT is loaded, so set it again for each file.

### End-of-Fight Cut

When "End-of-Fight Cut" is enabled during anonymization, the final targeted battle is saved only up to the point where the boss's remaining HP falls to or below the specified percentage.

**The default is 10%, and the selectable range is 1–99%.**

It can be used with both cleared and uncleared recordings, and it can also be applied to a selected battle segment.

The saved replay ends at that point and is marked as uncleared. It does not force you to leave the duty in the actual game. Depending on the intervals between recorded HP updates, the boss's HP at the cut point may be slightly below the specified percentage.

Saving is stopped if the boss never reaches the specified HP threshold or if the target boss or its HP cannot be identified.

This feature shortens the end of the fight to make it harder to match the original battle using the clear time, party DPS, or similar information.

### Battle Segment Extraction

1. Select the segment you want to extract from the battle list.
2. Click "Save" and review the confirmation screen.
3. Choose the output location and DAT or ZIP format.

Only segments whose start and end can be identified using information such as countdowns are supported. Extraction may not be possible for DAT files with insufficient information or unsupported duties.

If the pre-fight preparation period is long, the waiting time before the fight is shortened to a maximum of 30 seconds in the extracted replay. If it is 30 seconds or less, it is preserved as-is. Because this is a complex operation, playback issues may occur even when saving succeeds.

For older DAT files, use "Old → Current" first if conversion is supported. To combine extraction and anonymization, configure both operations on the original, non-anonymized DAT and save the result.

### Change Character ID

Use this when someone other than the original recorder wants to play back a DAT that has not been anonymized. When another person plays the recording, entries may be missing from the party list. This feature uses character information from one of your own DAT files to make the display match.

1. Open the DAT you want to modify and click "Change Character ID".
2. Select a DAT recorded with your own character as the reference.
3. Save the result as a separate file.

This is separate from anonymization. Be careful not to mix up the reference DAT and the DAT you want to modify.

### Old → Current

Restores older replay DAT files from version 7.0x onward to a supported current format. Select a DAT or a ZIP containing a DAT using "Old → Current" and follow the on-screen instructions to save it. Conversion alone does not anonymize the file.

Not every DAT can be restored. Support is limited to formats and duties that have been examined and analyzed.

If a file cannot be converted, submit the older DAT through the [DAT submission form](https://www.dropbox.com/request/gkofh48datowq9uozjif), along with a current DAT from the same duty if possible. An older DAT alone may be enough, but a current DAT helps with comparison.

Supporting additional cases requires analysis. Continued development and the range of supported files depend on overall demand and support. A particular donation amount does not guarantee conversion for an individual file or a specific completion date.

For batch processing, select "Batch Convert Old Replays" and choose separate input and output folders. Subfolders are processed, and the original folder structure is preserved. Unsupported files, files that do not need conversion, and files with an existing output of the same name are skipped with a reason shown. Outputs completed before cancellation are retained.

**After a game update, please wait for a compatible release before using Old → Current conversion or anonymization.**

### Full Remake

This feature is under development and is not available in the current public release.

## Individual ZIP Compression

Select "Individual ZIP Compression" and choose separate input and output folders to compress supported older DAT files into individual ZIP files, organized by format generation and duty.

The original DAT files are preserved. Current-format DAT files are excluded. ZIP creation is skipped if an identical ZIP already exists; if the filename is the same but the contents differ, the result is saved under a different name. ZIP compression alone does not anonymize or convert a DAT to the current format.

## Saved Filename Prefixes

Depending on the operations performed, an indicator is added to the beginning of the saved filename.

| Example prefix | Meaning |
|---|---|
| `Miqo(M)`, `S` / `M` / `L`, `RB`, etc. | Race/gender, height, outfit |
| `Head(on)` / `Head(off)` | Headgear on/off |
| `Anonymass` | Anonymization |
| `Recorder-T1 Trial`, etc. | Recorder change; T1 and similar labels indicate the selected character's role |
| `Split3`, etc. | Extracted segment number |

## Before Sharing

**Anonymization does not guarantee complete anonymity.**

If a recording of the same battle is available on FF Logs or similar services, it may be possible to match the replay using the sequence of actions, timestamps, battle duration, or other information.

Before publishing or sharing a DAT, check whether a log of the same battle has been made public.

## Troubleshooting

If the app will not launch, make sure you extracted the entire ZIP and installed the required runtimes.

If you encounter a dictionary error, extract the distribution again with all bundled files.

When using the [bug report form](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/issues/new/choose), describe the steps you took, the symptoms, and any error messages. If a DAT file is needed, use the [submission form](https://www.dropbox.com/request/gkofh48datowq9uozjif); do not attach original DAT files directly to public GitHub issues.

## Development and Support

The app is provided free of charge, but continued development is difficult without financial support. Future development and the range of supported features, including Full Remake and additional analysis, will depend on overall demand and support.

*Note: The update count is the number of version updates...*

The source code is not public in order to protect the anonymization mechanism. If you have concerns about using the app, please refrain from using it. Use it only if you are comfortable doing so.

[Ko-fi](https://ko-fi.com/lost2) · [OFUSE](https://ofuse.me/lost) · [Questions about Using the App](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/discussions)

Donations are not required to report bugs or ask questions. Donations do not guarantee fixes, priority handling, or completion deadlines.

Feel free to use it.
