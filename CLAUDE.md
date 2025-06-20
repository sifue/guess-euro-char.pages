# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 言語設定 (Language Configuration)

このプロジェクトは日本語環境での動作を前提としています。

- **コミュニケーション**: 日本語で対応してください
- **コメント**: コードコメントは日本語で記述
- **ドキュメント**: 技術文書は日本語で作成
- **エラーメッセージ**: 可能な限り日本語で表示
- **変数名・関数名**: 英語を使用（国際的な慣例に従う）

## プロジェクト概要
このプロジェクトでは、 EURO-CHAR.md の文字情報を元に、GeoGuessr向けのヨーロッパの文字で判別できる国のクイズを作成します。

## プロジェクト名
guess-euro-char

## アプリケーション名
GeoGuessr向けヨーロッパ文字クイズ

## 技術構成

- Node.js v22.16.0
- TypeScript v5.8.3
- Vite
- React.js
- Tailwind CSS

バージョンが記載されてないものは開発が行いやすいバージョンを指定して利用してください。
また他にも必要なライブラリやツールがあれば、適宜追加してください。

## 非機能要件

- Cloudflare Workersへのデプロイに対応
- スマートフォンでもプレイしやすいタッチ操作対応
- PCとスマホのレスポンシブ対応
- README.mdに開発環境のセットアップ手順を記載
- README.mdにwranglerを利用したCloudflare Workersへのデプロイ手順を記載
- .gitignoreファイルを作成し、Gitで構成管理できるようにする
- ヨーロッパの言語の文字がわかりやすいフォントの利用

## 機能要件

- ページは以下の構成
  - ゲームモード選択画面
  - 問題画面
  - 結果表示画面
  - 暗記モード画面
- ゲームモード選択画面では 文字10問モード、暗記モードの2種が選択可能
- スタートボタンを押すとゲーム開始と同時にタイマー起動
- 問題はランダムで出題、問題形式は以下の2種類
  - 文字10問モード：文字情報が大きく表示され4つの選択肢から正解を選ぶ
- 4つの選択肢は登録されている正解の言語の組み合わせの中よりランダムに表示され、正解が一つある (正解が二つないようにすること)
- 問題画面には現在何問中何問目かと現在の経過時刻も表示
- 回答をした瞬間に、それが○×と正解が何だったか表示
- 全ての問題を回答し終えると結果表示ページが表示され得点とタイマーが表示
- 結果表示画面には、過去そのブラウザでやった時の得点とタイマーが表示され、得点 > タイマーで表示され、過去の10個のランキングと得点日時が表示
- これらの過去の記憶はWeb Strageに保存
- 結果表示ページには、それまでに答えた問題の正誤表が表示され、またゲーム選択画面に戻るボタンともう一度挑戦するボタンが表示
- 正解の言語の組み合わせのうち、言語の代表的な国が存在する場合には、 (例: アイスランド語 → アイスランド) その国の国旗を表示
- 国旗情報に関しては、[Flags API & CDN](https://flagcdn.com/) を利用する
- ogpタグを設定し、ゲームのタイトルと説明文を設定
- ファビコンを設定、ヨーロッパの旗を希望

## 問題作成データ
- 問題は `EURO-CHAR.md` から取得

## 問題作成データ参考動画
- [【GeoGueesr解説】絶対に知っておきたい攻略手法10選！｜初級編](https://www.youtube.com/watch?v=_EEJI0il6mY&t=977s)
- [【GeoGuessr攻略】ヨーロッパの言語を見分けよう！](https://www.youtube.com/watch?v=vAyrDesxYlo)

