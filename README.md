# サイトA / フレカ置き場

サイトDのUI・操作を4人（**ろりは・めろな・ゆは・もか**）で使えるようにしたサイトA。

- 公開: https://uoxou910.github.io/aiprif/
- 新管理: https://uoxou910.github.io/aiprif/edit.html
- 旧管理（移行完了まで）: https://uoxou910.github.io/aiprif/legacy-edit.html
- 上書き前のサイトA: Git branch `backup-before-site-d-design`

## データの扱い

**2026-11-22 にサイトA専用GASのウェブアプリURLへ接続しました。**

`assets/config.js` の `gasUrl` にサイトA専用のデプロイURLを設定済みです。現在の公開画面と新管理画面はそのGASにアクセスします。サイトDのGASとは別の接続先です。

旧サイトAの公開フレカは、GAS側で `importLegacyPublicCards` を実行して移行してください（GitHub側のURL設定だけでは旧データは移行されません）。画像アップロードの権限付与はGAS側で `authorizeImageUploads` を実行します。

元の管理画面は `legacy-edit.html` に残してありますが、**旧GASのデータを操作するため、新管理画面とは別の保存先です**。切替前の旧サイトAデータはGitHub側では削除していません。非公開メモ、パスワード、スプレッドシートIDをGitHubに追加しないでください。

## 色の同期

`assets/initial-colors.js` は公開用の初期カラーです。新GASへ接続後、公開色の定期同期ワークフローを有効にしてください。

## ファイル

`index.html` / `edit.html`: 新画面。
`legacy-index.html` / `legacy-edit.html` と `assets/legacy-*.js`: 移行前の画面を残したもの。

## ミクコの管理用チェック

新管理画面のフレカ追加・編集画面では、各フレカに「ミクコ」フラグを設定できます。フレカ一覧の検索欄右側にある「ミクコ」にチェックすると、コーデ名検索やキャラ別絞り込みとAND条件で表示を絞ります。サイトAには「ダーク化」フラグはありません。

GASの既存スキーマを変更しないよう、ミクコフラグはコーデ名末尾の不可視識別子（U+2064×3）で保持します。新管理画面・公開画面ではこの識別子を取り除いて表示します。フラグを付けるコーデ名は117文字以内にしてください（GAS/画面の上限120文字から識別子3文字を差し引くため）。旧管理画面や他の編集ツールでコーデ名を更新すると、フラグが失われる可能性があります。

