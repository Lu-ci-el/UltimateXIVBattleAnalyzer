# UltimateXIVBattleAnalyzer

[Home](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer) · [日本語](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/blob/main/docs/USER_GUIDE.ja.md)

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

Configure the desired operations and click "Save" to export a DAT or ZIP. If no battle is selected, the entire recording is saved. If a battle row is selected, only that battle segment is saved. Progress is displayed while anonymization or action removal is running. Use the cancel button in the progress area to stop the operation. Simply changing the settings does not modify the original DAT. Keep a copy of the original DAT and save modified results as separate files.

## DAT → ACT Log Search → Formal Split

Find the ACT log corresponding to a replay and extract only that battle from a log containing multiple fights. This prepares a log that can be uploaded to FF Logs.

1. Click "DAT → ACT Log Search → Formal Split" and select the original DAT before anonymization.
2. Select the ACT log folder. Subfolders and supported log ZIP files are also searched.
3. If a matching log is found, choose an output location and extract it.
4. Review the extracted log and upload it using the FF Logs uploader.

You need the ACT log from when the replay was recorded. This feature does not generate a new ACT log from a DAT file. DAT anonymization is not applied to ACT logs.

## Enemy Timeline

Open a DAT and choose “敵技タイムライン” (Enemy Timeline) to see casts, hit timing, targets and boss HP in battle order. You can search by action name or target.

1. Select the first and last events you want to keep, then set them as the start and end. You can also enter times in seconds and add a margin on either side.
2. Choose “Save selected range as DAT” to export the selected scene.
3. Choose CSV or JSON to save the list of events instead.

## Editing replays

### Anonymization and Appearance Anonymization

Anonymizes much of the personally identifying information about party members contained in the DAT, including names, character IDs, and portraits. The recording date and time are also set to a predetermined value.

Displayed damage and healing amounts are set to zero after anonymization. Recorded HP changes, deaths, revivals, and movement are retained.

The outfit settings let you choose weapons and armor independently for the party. Player copies now use the original player’s headgear visibility setting.

- **For a weapon series**, turn on “Change weapons,” type a name in the weapon field and select a result. Search `Ultimate` for seven reward series, including Ultima. Use `ZW`, `AW`, `EW`, `RW`, `MW` or `FW` to find relic upgrade stages. Phantom Weapons also accept `PW`. If a party member has no weapon in a series, the result shows which job is missing.
- **For matching armor**, choose “Other” and select a dyeable series. “Job-specific outfit” offers undyed job sets at the 50, 60, 70, 79, 89 and 99 bands. If a job has no set at the selected band, it uses its lowest available set.
- **To match the weapon to the outfit**, turn on “Use job-specific weapons.” If the equipped set has no matching weapon, UXBA picks one for that job. A weapon series you select takes priority.
- **To randomize each player**, enable the option for random race, gender and height. It also varies face, hairstyle, hair color and highlights. Each player keeps the same appearance throughout the saved DAT.

The settings window stays the same size when you change outfits or search for equipment. Scroll within it to reach the remaining options.

1. Open a current-format DAT that has not been anonymized.
2. Open "Appearance Anonymization," turn it ON, and choose the race, gender, height, outfit, and headgear setting.
3. If needed, also select a battle segment, change the recorder, or enable the end-of-fight cut, then save to a separate file.

During anonymization, the original recorder's information is transferred to the first person in the party list, and the list is arranged so that person appears at the top. Information associated with the original recorder, such as marker placement, countdowns, and party leader information, is also transferred. Individual players keep their recorded movement. To change jobs, use "Remove all player actions / same-role jobs."

The only additional change supported on an already anonymized DAT is "Change Recorder." To change appearances or extract a battle segment again, start with the original DAT before anonymization.

### Remove All Player Actions / Same-Role Jobs

Remove player and pet actions, casts, and friendly job effects while retaining movement and enemy attacks for reviewing the encounter.

1. Open a current-format DAT that has not been anonymized, then enable "Remove all player actions / same-role jobs."
2. Choose the desired job for each character in the player list. Available choices stay within that character's role.
3. If needed, also configure appearance anonymization, the recorder, the battle segment, or "Cut ending," then save to a separate file.

You can leave the jobs unchanged and use action removal on its own. The party display order and labels such as T1 and D1 update to match the selected jobs.

This option also removes friendly buff, shield, and jump displays, and shows MP at its maximum. Movement, knockback, HP changes, deaths, and revivals are retained.

**Action removal alone does not anonymize the DAT.** Enable "Appearance Anonymization" as well when sharing an anonymized replay. Configure the options again after loading another DAT.

The party list has T1 ↔ T2, H1 ↔ H2 and D1 ↔ D2 controls for swapping role labels. Players keep their positions, and the recorder’s filename uses the chosen label. Tank job changes preserve the original pair’s priority order across Paladin, Warrior, Dark Knight and Gunbreaker.

### Change Recorder

Turn ON "Change Recorder," select a person from the player list, and save. The selected party member becomes the recorder, local player, and party leader. This also works with anonymized DAT files received from other people.

If a Splatoon script uses the recorder or local player to determine its behavior, we recommend selecting the intended character. The local player is the character that scripts and other systems refer to as "self."

When used together with anonymization, the selected person takes priority as the recorder and party leader. The selection is cleared when another DAT is loaded, so set it again for each file.

### End-of-Fight Cut

Enable "Cut ending" together with anonymization or "Remove all player actions / same-role jobs" to save the final targeted battle only up to the point where the boss's remaining HP falls to or below the specified percentage.

**The default is 10%, and the selectable range is 0–99%.**

It can be used with both cleared and uncleared recordings, and it can also be applied to a selected battle segment.

At 0%, the replay is retained through the recorded point where the boss's HP reaches zero.

The saved replay ends at that point and is marked as uncleared. It does not force you to leave the duty in the actual game. Depending on the intervals between recorded HP updates, the boss's HP at the cut point may be slightly below the specified percentage.

Saving is stopped if the boss never reaches the specified HP threshold or if the target boss or its HP cannot be identified.

This feature shortens the end of the fight to make it harder to match the original battle using the clear time, party DPS, or similar information.

### Battle Segment Extraction

1. Select the segment you want to extract from the battle list.
2. Click "Save" and review the confirmation screen.
3. Choose the output location and DAT or ZIP format.

Only segments whose start and end can be identified using information such as countdowns are supported. Extraction may not be possible for DAT files with insufficient information or unsupported duties.

If the pre-fight preparation period is long, the waiting time before the fight is shortened to a maximum of 5 seconds in the extracted replay. If it is 5 seconds or less, it is preserved as-is. Because this is a complex operation, playback issues may occur even when saving succeeds.

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

### Contingency Update

This optional feature is available from "Contingency update" when regular dictionary updates are unavailable.

1. Choose "Prepare from dictionary" and select the FFXIV executable matching the current dictionary.
2. After a game update, choose "Update from new EXE" and select the newer FFXIV executable.
3. Enable "Use contingency data for generations absent from the registered dictionary," then reload the DAT.

If a change cannot be supported, the update stops and retains the previous data. This feature does not support every game update.

### Full Remake

Open a current-format DAT that has not been anonymized and choose “Full Remake.”

1. Enable Full Remake and select the party member you want to edit.
2. Change that player’s appearance or equipment and save the player settings. Repeat for any other members you want to edit.
3. Click “Save” in the main window to write the changes to a replay DAT.

## Individual ZIP Compression

Select "Individual ZIP Compression" and choose separate input and output folders to compress supported older DAT files into individual ZIP files, organized by format generation and duty.

The original DAT files are preserved. Current-format DAT files are excluded. ZIP creation is skipped if an identical ZIP already exists; if the filename is the same but the contents differ, the result is saved under a different name. ZIP compression alone does not anonymize or convert a DAT to the current format.

## Saved Filename Prefixes

Depending on the operations performed, an indicator is added to the beginning of the saved filename.

| Example prefix | Meaning |
|---|---|
| `La(M)` / `Miqo(M)`, `S` / `M` / `L`, `PH` / `RB`, etc. | Race/gender, height, outfit |
| `Rnd` / `AF99`, etc. | Per-player random appearance / selected job armor band |
| `Hd_on` / `Hd_off` | Headgear on/off |
| `Anon` | Anonymization |
| `Re-T1` / `Re-D4`, etc. | Recorder change; T1 and D4 indicate the selected character's role |
| `NA` | Action removal and same-role job selection |
| `Sp3`, etc. | Extracted segment number |

Example: `Re-D4 NA La(M) S PH Hd_on Sp10 Anon.dat`

ZIP output uses the same naming format with the `.zip` extension.

## Before Sharing

**Anonymization does not guarantee complete anonymity.**

If a recording of the same battle is available on FF Logs or similar services, it may be possible to match the replay using the sequence of actions, timestamps, battle duration, or other information.

Before publishing or sharing a DAT, check whether a log of the same battle has been made public.

## Troubleshooting

If the app will not launch, make sure you extracted the entire ZIP and installed the required runtimes.

If you encounter a dictionary error, extract the distribution again with all bundled files.

When using the [bug report form](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/issues/new/choose), describe the steps you took, the symptoms, and any error messages. If a DAT file is needed, use the [submission form](https://www.dropbox.com/request/gkofh48datowq9uozjif); do not attach original DAT files directly to public GitHub issues.

## Development and Support

UXBA is a free hobby project. See the [developer’s note](../README.en.md#future-updates) for plans for 7.58 and the support needed for future updates.

The source code is not public in order to protect the anonymization mechanism. If you have concerns about using the app, please refrain from using it. Use it only if you are comfortable doing so.

[Ko-fi](https://ko-fi.com/lost2) · [OFUSE](https://ofuse.me/lost) · [Questions about Using the App](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/discussions)

Donations are not required to report bugs or ask questions. Donations do not guarantee fixes, priority handling, or completion deadlines.

Feel free to use it.
