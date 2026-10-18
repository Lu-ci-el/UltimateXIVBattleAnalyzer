# UltimateXIVBattleAnalyzer

[日本語](README.md) · [Download](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/releases/latest) · [User guide](docs/USER_GUIDE.en.md)

A Windows app for viewing and organizing FFXIV replay DATs. Extract battles, anonymize recordings for sharing, and convert supported older DATs.

## Getting started

1. Download the [latest ZIP](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/releases/latest).
2. Extract the whole folder and run `UltimateXIVBattleAnalyzer.exe`.
3. Open a recording with the DAT load button.
4. Set the operations you need and save a separate file.

For 64-bit Windows 10/11. The required dictionary is included. If prompted, install [.NET 8 Desktop Runtime for Windows x64](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) and [WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/).

## Features

| Feature | What it does |
| --- | --- |
| View DATs | Shows recording information, players and battles. |
| Extract battles | Saves a selected interval as a DAT or ZIP. |
| Anonymize names | Changes names and character identifiers. |
| Appearance anonymization | Also changes race, gender, height and outfit. |
| End cut | Optionally ends a clear or wipe recording at a chosen remaining HP during anonymization, saving it as uncleared. |
| Past to Modern / batch conversion | Converts supported older DATs. |
| Change Character ID | Uses your own recording as the character-ID reference. |
| Extract ACT logs | Finds matching intervals in the ACT logs from the recording. |
| Individual ZIP compression | Organizes older DATs into separate ZIPs. |

Keep your original DATs. Extract battles and set appearance before anonymizing. See the [user guide](docs/USER_GUIDE.en.md) for instructions.

## Before publishing or sharing

**Before publishing or sharing a DAT, always check that data from the same battle is not publicly available on FF Logs or similar services.** Even after names, IDs, and appearance are changed, action sequences, timestamps, and battle duration can form a combat fingerprint that may be matched to public logs and used to infer who took part. Anonymization does not guarantee complete anonymity.

## Questions and reports

[Report a bug](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/issues/new/choose) · [Ask a usage question](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/discussions)

If conversion or another operation fails, send the original DAT and the symptoms/error message through the [Dropbox upload form](https://www.dropbox.com/request/gkofh48datowq9uozjif).

## Support development

Continued development needs your support. Support for 8.0 will depend on contributions.

If you find UXBA useful or feel it is something you need, please consider supporting its development.

Without support, I will take that as a sign that there is no demand and end development.

[Ko-fi](https://ko-fi.com/lost2) · [OFUSE](https://ofuse.me/lost) · [About development support](docs/SUPPORT.en.md)

Support is not required to report issues or ask questions. Contributions do not guarantee fixes, priority or deadlines.
