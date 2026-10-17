# UXBA User Guide

[Home](../README.en.md) · [日本語](USER_GUIDE.ja.md)

## Before starting

Extract the entire download ZIP and run `UltimateXIVBattleAnalyzer.exe`. Do not run it inside the ZIP. Keep the `Runtime`, `Resources`, and `Settings` folders with the executable. The dictionary is included; you do not need to move or remove it.

If prompted at startup, install the [.NET 8 Desktop Runtime for Windows x64](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) and [WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/). Use a folder where you have write permission.

Keep your original DATs and save edits to separate files. Settings are stored in the app's `Settings` folder, and working files in `Work`. Choose input and output locations when prompted.

## 1. Open a DAT

![Main screen](images/main-en.png)

1. Choose **Load DAT** and select a DAT or supported ZIP.
2. Inspect the recording information, player list, and battle list.
3. Check start/end times, duration, results, and enemies. Scroll horizontally to see additional columns.

Use the language selector at the top right to switch between Japanese and English. **Reset** resets the current selection. Reading, conversion, and anonymization have different requirements: being able to open a DAT does not mean every editing operation is supported.

If the recording does not provide enough information to identify a player, the app displays a Player number even with name anonymization off. Unidentified players cannot be selected as recorder.

## 2. Extract a battle

This works with modern DATs. For a supported older DAT, use **Past → Modern** first.

1. Open the DAT and select the battle you want to extract.
2. Choose **Save** and review the extraction confirmation.
3. Select an output location and DAT or ZIP format, then save.

With no battle selected, saving applies to the whole recording. To extract and anonymize together, choose the anonymization settings before saving. You cannot extract another battle from an anonymized DAT; return to the original recording.

Extraction preserves the original DAT's initial entry time. It is not replaced with one fixed time for every duty.

## 3. Anonymize names

1. Open a supported modern DAT.
2. Enable **Anonymize player names**.
3. Leave battles unselected to save the whole recording, or select one battle to extract it.
4. Choose **Save** and create a separate output file.

Names inside the DAT become full English job names, such as `Paladin` or `White Mage`. The app shows `Player 01`, `Player 02`, and so on. These numbers distinguish people even when they have the same job.

Supported character identifiers and home-world information are also changed, and the internal recording date is replaced with a fixed value. Appearance is unchanged. If the original filename contains a name or date, check the output filename before sharing it.

## 4. Change appearance with full anonymization

![Full anonymization settings](images/anonymous-en.jpg)

1. Open a modern DAT that has not been anonymized, then choose **Full anonymization**.
2. Enable **Full anonymization ON**.
3. Choose race, gender, height, and outfit. Every race and gender can remove headgear.
4. Close the settings window and save with **Anonymize player names** enabled.

Removing headgear uses the selected race's default face and randomizes each player's hairstyle. Roegadyn are bald. Dyeable armor uses the assigned color for all 32 combat classes and jobs, including Blue Mage and Beastmaster. Undyeable armor retains its original color. Weapons and shields are undyed: item-level 665 Exquisite weapons, Exquisite Gentlemage's Umbrella for Blue Mage, and the Beastliege hand axe and hoplon for Beastmaster. Phoenix Hero, Vanguard, YoRHa Type-51, Type-53, Type-55, and No.2 Type B outfits are also available.

Choosing settings does not modify the original DAT. Saving applies changes to names, identifiers, and appearance, and clears the recorder's job-gauge data.

Full anonymization does not eliminate every way of recognizing a player. Party composition, movement, and tactics can still offer clues. Check the saved result before sharing it.

## 5. Change the recorder

1. Open the DAT and enable **Change recorder**.
2. Select one person from the party-member list.
3. Choose **Save** and write a separate file.

You can change the recorder while anonymizing a replay. You can also reopen an anonymized DAT and choose a different recorder. Use Player numbers to distinguish candidates with the same job.

When an anonymized DAT is open, name anonymization, full anonymization, battle extraction, character-ID changes, and Past → Modern conversion are unavailable. You can inspect its recording information and battles, and save after enabling recorder changes. Open the original DAT to perform other edits.

### Output filenames

Applied operations are appended to the original name. Example: `Recording T1 Miqo(M) S RB Split.dat`.

- `T1`, `T2`, `H1`, `D1`, etc.: the selected recorder, matching the player list.
- `Miqo(M)`: race abbreviation and gender (M/F).
- `S`, `M`, `L`: minimum, middle, or maximum height.
- `RB`, etc.: outfit abbreviation.
- `Split`: battle extraction. Name-only anonymization adds `Anon`.

Race abbreviations: Hyur, Ele, Lala, Miqo, Roe, AuRa, Hroth, Viera.

Outfit abbreviations: Rabbit RB, Dapper Rabbit RD, Chocobo CB, Chicken CK, Tonberry TB, Kappa KP, Frog FG, Pig PG, Elephant EL, Reindeer RE, Magical MG, Phoenix Hero PH, Vanguard VG, YoRHa Type-51 Y51, No.2 Type B 2B, YoRHa Type-53 Y53, YoRHa Type-55 Y55.

## 6. Convert an older DAT

Choose **Past → Modern**, select the older DAT, and follow the prompts to save a separate file. Open the converted DAT to use modern-DAT operations.

Support depends on the recording generation and contents. Use the original recording, rather than a DAT already processed by UXBA. If conversion is unavailable, keep the exact error message.

### Convert a folder in one batch

1. Click **Batch Past → Modern**, to the right of **Past → Modern**.
2. Select an input folder, then a separate output folder. Each picker remembers its previous location.
3. DATs in subfolders are included. The output keeps their relative folder structure.
4. Review the success and skip counts, and the reason for each skipped file.

Unsupported, modern, or previously processed DATs and existing output names are skipped. Original DATs and existing outputs are preserved. Use **Cancel** to stop; completed outputs remain. Choose separate folders that do not contain one another.

## 7. Change character IDs

This helps adjust party-list presentation in a DAT recorded by someone else. Prepare a reference DAT containing your own character.

1. Open the DAT you want to change and choose **Change character ID**.
2. Select your own DAT as the reference.
3. Choose an output location and save under another name. The suggested filename starts with `CHARACTER_ID_`.

Do not confuse the target DAT with the reference DAT. This operation is unavailable for anonymized DATs. To select a recorder from the party members, use **Change recorder** instead.

## 8. Extract matching ACT logs

You need the ACT logs from the recording session. This feature does not generate ACT logs from a DAT.

1. Choose the **DAT → ACT log search → Official Split** command.
2. Select the original DAT.
3. Select the folder containing the ACT logs. Subfolders and supported log ZIPs are also searched.
4. Choose an output location and check the extracted logs when processing finishes.
5. To publish on FF Logs, use the FF Logs uploader.

Matching uses the recording date, so use the original DAT before anonymization. DAT anonymization does not affect ACT logs. Check visibility settings on FF Logs separately.

## 9. Organize older DATs into individual ZIPs

1. Choose **Individual ZIP compression**.
2. Select the input folder containing the original DATs.
3. Select a separate output folder. It cannot be the input folder, a parent of it, or a folder inside it.
4. Confirm and run. Each eligible DAT is archived separately and organized by generation, duty, and other recording information.

Original DATs are not changed or moved. The current generation is excluded; supported older recordings are organized. Identical existing ZIPs are skipped, and different contents sharing a name are saved separately. Compression does not anonymize recordings.

## Troubleshooting

| Problem | What to check |
| --- | --- |
| The app will not start | Extract the whole ZIP and install any required runtimes. |
| The dictionary will not load | Extract the download again, including `Settings/DictionaryPacks/DictionaryPack.uxdic`. |
| Saving or anonymization is unavailable | Check whether the DAT is a supported modern recording or is already anonymized, and read the message shown in the app. |
| Conversion or extraction stops | The generation or recording contents may be unsupported. Keep the exact error message. |
| ACT logs cannot be found | Use the original, non-anonymized DAT and ACT logs from that recording session. |

Full Remake is in development; the distributed app displays an information message.

When [reporting a bug](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/issues/new/choose), include the app version, steps, expected result, actual result, and error text. Do not attach DATs or ACT logs to public posts. Hide personal information in screenshots. [Support development](SUPPORT.en.md).
