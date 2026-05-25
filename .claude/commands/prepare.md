指定された章の執筆に必要な全リファレンスを一括で読み込むコマンド。

## 手順（.claude/claude.md の執筆手順に準拠）

1. `plot/full-plot.md` を読み、引数で指定された章のプロット部分を確認する
2. `characters/index.md` で該当章の登場キャラクターを確認し、各キャラクターファイルを読む
3. `reference/style-guide.md` を読む
4. 該当章に戦闘シーンがある場合は `reference/battle-guide.md` を読む
5. 該当章に勘違いストーリーライン（★勘違い）マークがある場合は、`characters/lucius.md` の「憑依時の副産物」セクションを重点確認する
6. 必要に応じて `settings/world-rules.md`、`settings/locations.md`、`reference/enemy-nation.md` を確認する
7. 前章の原稿（`manuscript/` 内）があれば末尾を確認し、接続を把握する

## 引数

$ARGUMENTS — 章番号（例: `ch3`, `3`, `Ch.15`）

## 出力

読み込んだ情報を整理し、以下を簡潔にまとめる:
- この章のプロット概要
- 登場キャラクターと役割
- 注意すべき設定・テーマ
- 前章からの接続ポイント
- 戦闘/勘違いイベントの有無と注意点
