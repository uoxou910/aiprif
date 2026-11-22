# サイトA / フレカ置き場

サイトDのUI・操作を4人（**ろりは・めろな・ゆは・もか**）で使えるようにしたサイトA。

- 公開: https://uoxou910.github.io/aiprif/
- 新管理: https://uoxou910.github.io/aiprif/edit.html
- 旧管理（移行完了まで）: https://uoxou910.github.io/aiprif/legacy-edit.html
- 上書き前のサイトA: Git branch `backup-before-site-d-design`

## データの扱い

**まだ新しい管理GASには接続していません。**

`assets/config.js` の `gasUrl` は空欄です。公開画面は旧サイトAのGASからフレカを読み取るため、公開済みフレカをそのまま表示できます。旧フレカの登録・変更・削除は `legacy-edit.html` から継続できます。

所持コーデ、印刷予定、カラー設定、画像アップロードなどの新しい管理機能を使うには、サイトA用に独立したGoogleスプレッドシートとGASを用意し、**旧サイトAの公開フレカをインポートしてから** `gasUrl` を設定してください。サイトDのGASを使わないでください。

GASをつなぐと新管理画面が有効になりますが、切替前の旧サイトAデータは消えません。非公開メモ、パスワード、スプレッドシートIDはGitHubへ追加しないでください。

## 色の同期

`assets/initial-colors.js` は公開用の初期カラーです。新GASへ接続後、公開色の定期同期ワークフローを有効にしてください。

## ファイル

`index.html` / `edit.html`: 新画面。
`legacy-index.html` / `legacy-edit.html` と `assets/legacy-*.js`: 移行前の画面を残したもの。
