# 自分のリポジトリ一つでpull requestを試すための手順 in GitHub

`master`に`1stPullRequest`ブランチをmerge(マスター上で`git merge 1stPullRequest`)してもらいたいと仮定

## 前提
`remote`(githubのリポジトリ。以降`origin`)のmaster(`origin/master`)と`local`の`master`が同期済み

## 流れ

1. `local`で`1stPullRequest`branchを作成

2. 何か適当な更新を行いcommit

3. `origin`に`1stPullRequest`をpush

4. GitHub(ブラウザ上)で`master ← 1stPullRequest` のpull requestを作成

5. GitHub上でoriginのリポジトリを確認すると、`Your recently pushed branches:Pull Request Compare 1stPullRequest (1 minutes ago)`
のようなメッセージが出ているので`Pull Request`のボタンをクリック

6. 画面遷移後うえのほうをみると、マージ先とマージ元を選択する画面になっているので `master ← 1stPullRequest` となるように設定

7. pull requestの`タイトル`、`本文`を入力した後、`Send pull request`をクリック

8. GitHub(ブラウザ上)で`master`へ`1stPullRequest` をmergeしていいかレビュー

9. pull requestが作成され`Discussion`タブが開かれた状態になるので、レビュアーになったつもりでレビュー

10. 気になる点があれば、コメントでやり取りする※

11. 問題がなければ、GitHub(ブラウザ上)で`merge pull request`ボタンをクリック


※コメントのやりとりはpull request上がいいのか、commit上がいいのか調べる

メモ：
pull request中のブランチも更新可能（基本的に、できるけどやらないという方針がいいらしい）
pull request中のブランチを削除すると、pull requestがcloseされる
rejectされた場合はブランチ削除してから同じ名前のブランチでpull request送る？それとも名前かえる？
`1stPullRequest → 1stPullRequest2`みたいに。