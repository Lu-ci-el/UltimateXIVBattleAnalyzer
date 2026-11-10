# UltimateXIVBattleAnalyzer

[English](README.en.md) · [ダウンロード](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/releases/latest) · [日本語の説明書](docs/USER_GUIDE.ja.md) · [更新履歴](docs/CHANGELOG.ja.md) · [匿名リプレイ共有フォーラム](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/discussions/2)

FFXIVのリプレイDATを確認・整理するWindows用アプリです。
通常ID、討伐・討滅戦、レイド、アライアンスレイドの録画を扱います。

## できること

- DATの記録日時・クリア判定・PT編成・時間・DutyID、プレイヤー一覧・戦闘一覧の表示
- 対応するACTログの検索と、FF Logsへアップロードする区間の抽出
- 匿名化・外見匿名化、記録者変更、ボスの残HPを指定した終盤カット
- プレイヤー・ペットのアクション消去と、同じロール内でのジョブ選択
- 戦闘区間の抽出、キャラID変更、対応する過去DATの現代化・一括変換
- 敵技タイムラインの表示、選択範囲のDAT・CSV・JSON保存
- フルリメイクでの個別編集、外見匿名化でのPT装備シリーズ選択
- 過去DATの個別ZIP圧縮・分類

## 使い始める

1. [配布ZIP](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/releases/latest)をダウンロードし、フォルダごと展開します。
2. `UltimateXIVBattleAnalyzer.exe`を起動し、「DAT読み込み」でDATまたはDATを1本含むZIPを開きます。
3. 操作を設定し、元DATを保管したうえで別ファイルへ保存します。

同梱の辞書・フォルダはそのまま使ってください。導入手順・対応条件・各機能の使い方は[日本語の説明書](docs/USER_GUIDE.ja.md)をご覧ください。

匿名化済みDATは記録者変更のみ可能です。匿名化は完全な匿名性を保証しません。

共有前に、同じ戦闘のログがFF Logsなどで公開されていないか確認してください。

ゲーム更新後の匿名化には、その世代に対応した配布物をお使いください。「過去→現代」は、予備更新で変換経路を確認できた場合にも使えます。

## 今後の更新について

UXBA 3.8.2.9でFFXIV 7.58に対応しました。7.57hの旧辞書を使った「予備の自動更新」で、過去のリプレイを7.58へ変換して再生できました。

今回と同じくらい小さな更新なら、この方法で次も再生できるかもしれません。8.0のような大型アップデートでは、予備更新だけで対応するのは厳しいと思っています。

UXBAは趣味で作り、これまで維持費も自分で負担してきました。「録画を共有してほしい」という人に比べて、匿名化したとしても自分の録画を共有してもいいという人は少ないと感じています。ここまでの機能を必要とする人や、実際に使う機会は限られているのかもしれません。

フルリメイクでかっこいい場面や面白い構図のリプレイを作れたら、「自分の録画も公開してみたい」と思うきっかけになるんじゃないかと考えました。

これまで支援してくださったお二人、本当にありがとうございます。最近は支援が途絶えていて、「今もこのアプリを必要としてくれている人はいるのかな」と迷うことがあります。維持費を自分一人で払い続けるのは厳しく、申し訳ありませんが、今回が最後の更新になるかもしれません。これからもUXBAを使いたいと思ってくださる方は、開発を支援していただけるとうれしいです。

[OFUSEで支援する](https://ofuse.me/lost) · [Ko-fiで支援する](https://ko-fi.com/lost2)

## 問い合わせ

[不具合報告](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/issues/new/choose) · [使い方の質問](https://github.com/Lu-ci-el/UltimateXIVBattleAnalyzer/discussions) · [DATの提出窓口](https://www.dropbox.com/request/gkofh48datowq9uozjif)

匿名化の仕組みを保護するためソースコードは非公開です。

不安がある場合は使用を控え、納得した方だけお使いください。

[開発支援について](docs/SUPPORT.ja.md)
