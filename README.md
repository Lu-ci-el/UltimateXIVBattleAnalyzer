# UltimateXIVBattleAnalyzer

For English instructions, please see the [English guide](README.en.md).

[3.7.4.5をダウンロード](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/releases/tag/v3.7.4.5) · [更新内容](docs/CHANGELOG.ja.md)

[English](README.en.md) · [画像付き操作ガイド](docs/USER_GUIDE.ja.md) · [開発支援](docs/SUPPORT.ja.md)

FFXIVのリプレイDATから戦闘一覧やパーティ構成を確認し、戦闘区間の取り出し、匿名化、対応するACTログの抽出まで行えるWindows用アプリです。

![UXBAのメイン画面](docs/images/main-ja.jpg)

## できること

- **DATの読み込み**  
  対応する各世代のDATを読み込みます。  
  コンテンツ、戦闘一覧、時間、パーティ構成などを確認できます。

- **ACTログの検索・Split抽出**  
  DATとACTログの保存フォルダを選び、対応するログを取り出します。  
  FF Logsへアップロードするログの準備に使えます。

- **名前の匿名化**  
  現代DATの名前を `Player 01` などへ変更します。  
  キャラクターの識別ID、所属サーバー情報、内部の撮影日時も共有用に変更します。

- **完全匿名化**  
  名前などの匿名化に加え、キャラクターの見た目も変更します。  
  種族・性別・身長・衣装を設定できます。

- **戦闘区間の抽出**  
  戦闘一覧から取り出せる区間を選びます。  
  選んだ区間を、別のDATまたはZIPに保存できます。

- **過去→現代変換**  
  対応する過去世代のDATを、アプリが扱う現代世代へ変換します。  
  対応状況はDATの世代によって異なります。

- **キャラID変更**  
  自分のDATを参照して、対象DATのキャラIDを変更します。  
  PT一覧の抜けなど、リプレイの表示を整えるために使います。

- **個別ZIP圧縮**  
  対応する過去のDATを、1本ずつZIPにして別フォルダへ整理します。  
  元DATは残ります。

フルリメイクは開発中です。  
今後の開発は支援状況を見ながら進めます。

## 使い始める

1. ReleasesからアプリのZIPをダウンロードし、フォルダごと展開します。

2. `UltimateXIVBattleAnalyzer.exe`を起動します。

3. 「DAT読み込み」でDATを選びます。

4. 戦闘一覧を確認し、目的に応じて抽出・匿名化・保存を行います。

起動に必要な場合は [.NET 8 Desktop Runtime（Windows x64）](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) と [WebView2 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) をインストールしてください。  
アプリは同梱ファイルを含むフォルダのまま使います。

操作ごとの手順は[画像付き操作ガイド](docs/USER_GUIDE.ja.md)にまとめています。  
匿名化したDATから人物を推測できる可能性は残ります。  
戦闘の動きや構成まで別物になる機能ではありません。  
また、DATの匿名化はACTログには適用されません。

## 不具合・質問

再現する不具合や未対応DATは[不具合報告](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/issues/new/choose)へ、使い方の質問や機能の相談は[Discussions](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/discussions)へお願いします。  
アプリのバージョン、行った操作、期待した結果、実際の結果とエラー文があると調べやすくなります。  
画像の名前・サーバー・撮影日時・個人フォルダ名は隠してください。  
DATやACTログは公開投稿に添付しないでください。  
元DATの非公開送信窓口は現在用意していないため、まずは症状とエラー文で報告してください。  
詳しくは[報告・ファイル提供の案内](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/blob/main/.github/SUPPORT.md#日本語)をご覧ください。

調査・修正や未対応DATへの対応は、支援の状況と開発に充てられる時間によって変わります。  
対応できない場合もありますが、報告や質問に支援は必須ではありません。  
報告や支援をいただいても、修正・優先対応・期限をお約束するものではありません。

## 開発を支えてください

開発・検証を続けるには費用がかかります。  
自費で更新を続けられる見込みは2026年12月までで、2027年1月以降の更新や8.0対応は、皆さんからの支援に支えられる形になります。  
使って役に立ったら、無理のない範囲で応援してもらえると助かります。

[Ko-fiで支援する](https://ko-fi.com/lost2) · [OFUSEで支援する](https://ofuse.me/lost)

アプリ本体はReleasesで配布します。  
このリポジトリには説明書と配布案内を置いており、アプリのソースコードは含みません。
