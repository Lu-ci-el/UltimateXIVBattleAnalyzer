# UltimateXIVBattleAnalyzer

[日本語](README.md) · [Download](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/releases/latest) · [English user guide](docs/USER_GUIDE.en.md) · [Changes since 3.7.9.8](docs/CHANGELOG.en.md)

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

Only recorder changes are available for an already anonymized DAT. Anonymization does not guarantee complete anonymity. Before sharing, check whether logs of the same encounter are public on FF Logs or elsewhere. After game updates, wait for a distribution supporting Past → Modern and anonymization in the new environment.

## Future updates

FFXIV Patch 7.58 is scheduled for November 10, 2026. I hope to release a compatible version of UXBA if I can. [Official FFXIV announcement](https://na.finalfantasyxiv.com/lodestone/topics/detail/5c3b0f9e2fa2295dfc32c19e02e57e4e0614a09c)

I built UXBA as a hobby and have covered its running costs myself. In my experience, more people want to see someone else’s replay than are willing to share their own, even after their recording has been anonymized. That leaves fewer opportunities to use these tools, and I’m unsure how many people need this much replay editing.

The running costs are high. I can keep updating UXBA beyond 7.58 if contributions cover those costs, but I can’t keep paying for it on my own.

[Support development on Ko-fi](https://ko-fi.com/lost2)

## Questions

[Report a bug](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/issues/new/choose) · [Usage questions](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/discussions) · [Submit a DAT](https://www.dropbox.com/request/gkofh48datowq9uozjif)

The app is free to use. The source code is private to protect the anonymization approach. Please use the app only if you are comfortable doing so.

[About development support](docs/SUPPORT.en.md)
