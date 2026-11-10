# UltimateXIVBattleAnalyzer

[Download 3.7.4.3](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/releases/tag/v3.7.4.3) · [Release notes](docs/CHANGELOG.en.md)

[日本語](README.md) · [Illustrated guide](docs/USER_GUIDE.en.md) · [Support development](docs/SUPPORT.en.md)

A Windows app for working with FFXIV replay DAT files: inspect battles and party composition, extract a battle, anonymize a replay, and find the ACT logs that match a recording.

![UXBA main screen](docs/images/main-en.jpg)

## What you can do

| Feature | Purpose |

| --- | --- |

| Read replay DATs | View duty information, battles, timings, and party composition from supported recording generations. |

| Find and split ACT logs | Choose a DAT and your ACT log folder to extract the matching logs for upload to FF Logs. |

| Anonymize names | Replace names in modern DATs with aliases such as `Player 01`. Character identifiers, home-world information, and the internal recording date are also changed for sharing. |

| Full anonymization | Also change race, gender, height, and outfit through the anonymization settings. |

| Extract a battle | Select an extractable battle in the list and save it as a separate DAT or ZIP. |

| Past → Modern conversion | Convert supported older DAT generations to the modern generation handled by the app. Availability depends on the recording generation. |

| Change character ID | Use your own DAT as a reference to change the character ID in another replay and improve party-list presentation, such as missing entries. |
| Individual ZIP compression | Archive supported older DATs as one ZIP per recording in a separate folder, keeping the original DATs. |

Full Remake is in development. Further work depends on support for the project.

From 3.7.4.3, open a saved DAT to check its conversion, anonymization, and battle-extraction history together with the UXBA versions that performed those operations. See [processing history](docs/USER_GUIDE.en.md#10-check-a-dats-processing-history).

## Getting started

1. Download the application ZIP from Releases and extract the whole folder.

2. Run `UltimateXIVBattleAnalyzer.exe`.

3. Choose **Load DAT** and select a recording.

4. Inspect its battles, then extract, anonymize, or save as needed.

If required at startup, install the [.NET 8 Desktop Runtime for Windows x64](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) and [WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/). Keep the app together with its included files.

The [illustrated guide](docs/USER_GUIDE.en.md) covers each workflow. Anonymization cannot guarantee that nobody can recognize a player: movement, tactics, and party composition may still offer clues. Anonymizing a DAT does not anonymize ACT logs.

## Bugs and questions

Use Issues for reproducible bugs and Discussions for questions or feature ideas. Please include the app version, steps, expected behavior, actual behavior, and the exact error text. Hide names, servers, recording dates, and personal folder names in screenshots. Do not attach DATs or ACT logs to public posts; ask about a private way to provide them if needed.

## Help keep development going

Development and testing are expensive to sustain. I can fund updates myself through December 2026. Updates from January 2027 onward, including 8.0 support, will depend on contributions from people who find the app useful. If it helps you, please consider supporting it at a level that works for you.

[Support on Ko-fi](https://ko-fi.com/lost2) · [Support on OFUSE](https://ofuse.me/lost)

The app is distributed through Releases. This repository contains documentation and download information; it does not include the application's source code.

