# KOTATSUNEKO — 開店・閉店チェック

①上々(jyoujyou)の`index.html`から「開店・閉店チェック」ページだけを使えるようにした派生版。
買い物・仕込み表・シフト・売上確認・まかないチェックのタブ/機能はコードごと残したまま、
CSSの`hidden`属性でUIから見えなくしてある（③イソノと同じ「隠すだけ・消さない」方式）。

このフォルダ（`~/Desktop/kotatsuneko`）が唯一の正規の作業コピー。

## バックエンド

Firebase Realtime Database、プロジェクト`kotatsuneko-shop`（リージョン`asia-southeast1`）。
①②③とは完全に別のFirebaseプロジェクト。データベースのセキュリティルールは
「認証済みのみ許可」（`auth != null`）にデプロイ済み。

**要対応（初回のみ）**: Firebase Consoleで`kotatsuneko-shop`プロジェクトの
Authentication → Sign-in method から「匿名」を有効化すること。CLIからは
AIエージェント検知により対話的プロンプトが使えず、ここだけは手動設定が必要。
https://console.firebase.google.com/project/kotatsuneko-shop/authentication/providers

## 公開

GitHub Pagesのみ（Netlifyは使わない）。リポジトリは`atsup0917-arch/kotatsuneko`想定、
pushすれば`https://atsup0917-arch.github.io/kotatsuneko/`に自動反映される。

GitHubへのpushは毎回ユーザーの明示的な指示があった時だけ行う（①②と同じ方針）。

## 編集時の注意

- 買い物・仕込み表・シフト等の隠しページのコードは①からそのまま残っているが、
  実際に動かす想定ではない。開店閉店チェック機能だけを触ること。
- ①のCLAUDE.mdにある「実データ埋め込みランドマイン」のうち、Firebaseへ自動書き込み
  していた`shiftEmbeddedSepFirstDinnerData`/`...LunchData`スクリプトはこのコピーでは
  削除済み。①から再度まるごと上書きコピーする場合は同じ対応が必要。
- OneSignalプッシュ通知機能はこのコピーでは無効化（削除）済み。シフト機能自体を
  使わないため不要。
- ロゴ画像は無し（ヘッダーは文字表示のみ）。ロゴ画像をもらったら
  `assets/logo.jpg`に追加してヘッダーに戻せる。

変更履歴は`git log`を参照（このファイルには変更ログを書かない）。
