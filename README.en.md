# UltimateXIVBattleAnalyzer

[日本語](README.md) · [Download](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/releases/latest) · [English user guide](docs/USER_GUIDE.en.md) · [Release history](docs/CHANGELOG.en.md) · [Anonymized replay forum](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/discussions/2)

A Windows app for inspecting and organizing FFXIV replay DAT files from dungeons, trials, raids, and alliance raids.

## What it can do

- Display recorded date/time, clear status, party composition, durations, DutyID, players, and battles
- Find matching ACT logs and extract encounters for upload to FF Logs
- Anonymize identities and appearance, change the recorder, and cut the ending at a chosen boss HP percentage
- Remove player and pet actions and select jobs within the same role
- Extract battle intervals, change character IDs, and convert supported older DATs individually or in batches
- Inspect enemy actions on a timeline and export a selected range as a replay DAT, CSV or JSON
- Edit individual players with Full Remake or select equipment series for the whole party with Appearance Anonymization
- Compress older DATs into individual ZIPs and organize them

## Getting started

1. Download the [distribution ZIP](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/releases/latest) and extract the entire folder.
2. Run `UltimateXIVBattleAnalyzer.exe` and use “Load DAT” to open a DAT or a ZIP containing one DAT.
3. Set the desired options, keep the original DAT, and save to a separate file.

Keep the bundled dictionary and folders together. See the [English user guide](docs/USER_GUIDE.en.md) for setup, supported conditions, and instructions.

Only recorder changes are available for an already anonymized DAT. Anonymization does not guarantee complete anonymity. Before sharing, check whether logs of the same encounter are public on FF Logs or elsewhere. After a game update, use a compatible distribution for anonymization. Old → Current is also available when Contingency Update can verify the conversion.

## Future updates

UXBA 3.8.2.9 supports FFXIV patch 7.58. With the 7.57h dictionary and Contingency Update, older replays can be converted for playback on 7.58.

This approach may work again for a similarly small patch. I expect a major update like 8.0 to require more work than Contingency Update can handle on its own.

I built UXBA as a hobby and have covered its running costs myself. In my experience, more people want to see someone else’s replay than are willing to share their own, even after their recording has been anonymized. That leaves fewer opportunities to use these tools, and I’m unsure how many people need this much replay editing.

I hoped that making a replay with a striking scene or an interesting camera angle in Full Remake might make someone think, “I’d like to share mine, too.”

Thank you to the two people who have supported development. Contributions have dried up lately, and sometimes I wonder how many people still need UXBA. I can’t keep covering the costs on my own. I’m sorry to say this may be the last update. If you’d like to keep using UXBA through future patches, please consider supporting its development.

[Support development on Ko-fi](https://ko-fi.com/lost2)

## Questions

[Report a bug](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/issues/new/choose) · [Usage questions](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/discussions) · [Submit a DAT](https://www.dropbox.com/request/gkofh48datowq9uozjif)

The app is free to use. The source code is private to protect the anonymization approach. Please use the app only if you are comfortable doing so.

[About development support](docs/SUPPORT.en.md)
