# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## リポジトリの性質

`kazu-2020/kazu-2020` は GitHub のプロフィール表示用リポジトリ（ユーザー名と同名の special repository）。アプリケーションコードもビルドシステムもテストもなく、実体は `README.md` 一枚だけ。GitHub プロフィールのトップに表示される内容そのものである。

そのため「ビルド」「lint」「テスト」に相当するコマンドは存在しない。動作確認は README のマークダウンが GitHub 上で正しくレンダリングされるかどうかで判断する。ローカルのプレビューでは shields.io 等の外部画像の実挙動までは確認できないため、最終確認は push 後の GitHub 上で行う。

## README の構成

`Whoami` / `Tools of Trade` / `Reach me on` の 3 ブロック。[ileriayo/ileriayo](https://github.com/ileriayo/ileriayo) のプロフィールを下敷きにしたレイアウトで、次の約束事に従う:

- マークダウンではなく HTML タグで書き、`<h2 align="center">` と `<p align="center">` で全体を中央寄せにする。見出しは絵文字ではじめる。セクション区切りは `<hr>`。
- 本文は `<samp>` で囲む。
- 画像はすべて `img.shields.io` のバッジで、リポジトリ内に画像ファイルは持たない。スタイルは `for-the-badge` に統一し、バッジ間は `&nbsp;&nbsp;&nbsp;` で空ける。ロゴは simple-icons のスラッグ（`logo=ruby` など）を使う。
- バッジ表示が崩れる場合、ほぼ shields.io 側にそのロゴスラッグが存在しないことが原因。`logo=` を外すか別スラッグに差し替える。

## 履歴について

2026-08 まで `.github/workflows/profile-summary-cards.yml` が 24 時間ごとに走り、`profile-summary-card-output/` 配下に 64 テーマ分のカード SVG を生成して `Generate profile summary cards` というコミットで自動 push していた。README からカードを外した際にワークフローと生成物ごと削除済み。

そのため過去のリポジトリ履歴はほぼ全部この bot コミットで埋まっている。`git log` から人間の変更を探すときは `--invert-grep --grep='Generate profile summary cards'` で除外する。
