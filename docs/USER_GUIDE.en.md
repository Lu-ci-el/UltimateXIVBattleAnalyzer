# UltimateXIVBattleAnalyzer

[Home](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer) · [日本語](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/blob/main/docs/USER_GUIDE.ja.md)

## Basics

A Windows application for inspecting and organizing FFXIV replay DAT files. It works with recordings from instanced dungeons, trials, raids, and alliance raids. Some files cannot be loaded or processed, depending on their generation and recorded data.

### Starting the app and loading a DAT

1. Extract the entire distribution ZIP and run `UltimateXIVBattleAnalyzer.exe`.
2. Use “Load DAT” to select a DAT or a ZIP containing one DAT.
3. Review the recording details, player list, and battle list.

A 64-bit Windows environment is required. Keep the bundled dictionary and folders together. If prompted, install the [.NET Desktop Runtime for Windows x64](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) and [WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/). Switch between Japanese and English at the top right.

### Displayed information

- Recorded date and time, clear status, and party composition
- Playback/recorded duration, battle count, and DutyID
- Player list and battle list

The date and time come from the DAT, not its filename. An anonymized DAT displays its modified date and character information.

### Saving

Configure the desired options and press “Save” to write a DAT or ZIP. With no battle selected, saving applies to the whole recording; with a battle selected, it extracts that interval. Selecting options alone does not change the original DAT. Keep your original and save processed results to a separate file.

## DAT → ACT log search → official Split

Find the ACT log corresponding to a recording and extract that encounter from a log containing multiple battles. This prepares a log for upload to FF Logs.

1. Choose “DAT → ACT log search → official Split” and select the original, non-anonymized DAT.
2. Select your ACT log folder. Subfolders and supported log ZIPs are also searched.
3. If a matching log is found, choose an output location and extract it.
4. Review the extracted log, then upload it using the FF Logs uploader.

The original ACT log from the recording session is required. This feature does not generate an ACT log from a DAT. DAT anonymization does not anonymize ACT logs.

## Features under testing

The following editing features are experimental. Some DATs lack the required information, and bugs may occur. Check the saved result before using it.

### Anonymization and appearance anonymization

Anonymization replaces much of the identifying information about party members inside the DAT, including names, character IDs, and portraits. It also sets the recorded date and time to a fixed value.

“Appearance anonymization” lets you choose race, gender, height, and several costumes. Hiding headgear assigns random hairstyles per character; male Roegadyn remain bald. Your selected costume also applies to equipment changes during the recording.

1. Open a modern DAT that has not yet been anonymized.
2. Open “Appearance anonymization,” enable it, and choose the appearance settings. To anonymize without changing appearance, use the main window’s anonymization option.
3. If needed, select a battle interval, recorder, and tail-cut option, then save to a separate file.

Anonymization transfers the original recorder’s context to the first person in the displayed party list and arranges that person at the top of the party list. Related information, such as marker placement, countdowns, and leadership, is transferred too. It does not exchange players’ jobs or their actions during the battle.

In the distributed release, “Change recorder” is the only additional edit available for an already anonymized DAT. To redo appearance changes or battle extraction, start again from the original, non-anonymized DAT.

### Change recorder

Enable “Change recorder,” select one person from the player list, and save. The selected party member becomes the recorder, local player, and party leader. This also works with an anonymized DAT received from someone else.

If a Splatoon script uses recorder or local-player checks, selecting the intended person is recommended. The local player is the character that scripts and similar features treat as “you.”

When combined with anonymization, your selection takes priority for the recorder and party leader. Loading another DAT clears the selection, so choose again for each file.

### Tail cut

Enable tail cutting during anonymization to keep the recording only up to the point where the boss in the final applicable battle reaches or falls below the selected HP percentage. **The default is 10%; the range is 1–99%.** It works with cleared and uncleared recordings and can also apply to a selected battle interval.

The saved replay ends at that point and is saved as uncleared. It does not force anyone out of a live game instance. Because HP is recorded at intervals, the actual ending HP may be slightly below the selected percentage.

Saving stops if the boss never reaches the requested HP or if the boss/HP cannot be identified. Removing the ending helps make it harder to match the recording to the original encounter using clear time, party DPS, and similar information.

### Extract a battle interval

1. Select the interval you want in the battle list.
2. Press “Save” and review the confirmation.
3. Choose the output location and DAT or ZIP format.

The app uses starting information, such as countdowns, to identify an interval’s beginning and end. Files with insufficient information or unsupported content cannot be extracted.

Long starting/preparation intervals are shortened so that the wait before combat is at most 30 seconds. Preparation of 30 seconds or less is preserved. Extraction is complex, and playback issues may occur even when saving succeeds.

For a past-generation DAT, first use “Past → Modern” if supported. To extract and anonymize together, enable both operations on the original, non-anonymized DAT before saving.

### Change character ID

Use this when someone other than the original recorder plays a non-anonymized DAT. Party-list entries may be missing when another person plays it. Referencing character information from your own DAT helps align the display.

1. Load the DAT you want to modify and choose “Change character ID.”
2. Select a reference DAT recorded with your own character.
3. Save to a separate file.

This is separate from anonymization. Do not confuse the reference DAT with the DAT being modified.

### Past → Modern

Restore supported older replay DATs from the 7.0x era onward into a supported modern format. Choose “Past → Modern,” select a DAT or DAT ZIP, and follow the saving prompts. Conversion alone does not anonymize the recording.

Not every DAT can be restored. Support depends on the content and structures that have been checked and analyzed. If restoration fails, send the old DAT through the [DAT submission form](https://www.dropbox.com/request/gkofh48datowq9uozjif), preferably with a modern DAT from the same content. The old DAT alone may be enough, but a modern example helps with comparison.

Adding support requires analysis. Continued work and coverage depend on overall demand and support, rather than an individual donation amount. Restoration or a response deadline cannot be guaranteed.

For multiple files, use the batch conversion option and choose separate input and output folders. Subfolders are included and their structure is preserved. Unsupported files, files that do not need conversion, and files whose output already exists are skipped with reasons shown. Completed outputs remain if you cancel.

**After a game update, wait for a distribution that supports the new game environment before using Past → Modern or anonymization.**

### Full Remake

This feature is under development and is unavailable in the distributed release.

## Individual ZIP compression

Choose “Individual ZIP compression,” then separate input and output folders, to compress supported older DATs into individual ZIPs organized by generation and content.

The original DATs are retained. Modern DATs are excluded. Identical ZIPs are skipped; if the same name has different contents, a separate name is used. ZIP compression alone does not anonymize or modernize a DAT.

## Filename markers

Applied operations add markers at the beginning of the output filename.

| Example | Meaning |
| --- | --- |
| `Miqo(M)`, `S`/`M`/`L`, `RB`, etc. | Race/gender, height, and costume |
| `Head(on)` / `Head(off)` | Headgear shown / hidden |
| `Anon` | Anonymization |
| `Recorder-T1 Trial`, etc. | Recorder change; T1 and similar labels identify the selected player’s role |
| `Split3`, etc. | Extracted interval number |
| `Split` | Tail cutting without selecting an interval |

## Before sharing

Anonymization does not guarantee complete anonymity. If the same encounter is public on FF Logs or elsewhere, action order, timestamps, and battle duration may allow it to be matched. Check for public logs of the same encounter before publishing or sharing a replay.

## Troubleshooting

If the app does not start, check that you extracted the entire ZIP and installed the required runtimes. For dictionary errors, extract the full distribution again, including its bundled files.

When [reporting a bug](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/issues/new/choose), include the app version you are using, your steps, symptoms, and error message. If a DAT is needed, use the [submission form](https://www.dropbox.com/request/gkofh48datowq9uozjif) instead of attaching the original DAT directly to a public issue.

## Development and support

The app is generally free, but continued development is difficult without financial support. Future work, including Full Remake and additional analysis, depends on overall demand and support.

The source code is private to protect the anonymization approach. If you are uncomfortable using the app, please do not use it. Use it only if you are comfortable doing so.

[Ko-fi](https://ko-fi.com/lost2) · [OFUSE](https://ofuse.me/lost) · [Usage questions](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/discussions)

Support is not required to report a problem or ask a question. Donations do not guarantee a fix, priority, or deadline.
