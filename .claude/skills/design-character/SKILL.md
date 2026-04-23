---
name: design-character
description: |
  Phase 4 で使う汎用キャラクターシート生成Skill。NPC / 客血 / 一般キャラに使用。
  故プレイヤー(登場しない故人)は専用 Skill former-player-sheet を使うこと。
---

# キャラクターシート生成 Skill

## 使い方

1. キャラ種別を指定: NPC / 客血 / 派閥長 / etc.
2. 登場予定アーク・役割を指定
3. references/... のテンプレに従って生成
4. cast/<subfolder>/<name>.md に保存
5. cast/_index.md に追記

## 標準項目

- 基本(名前・種族・推定年齢・職業)
- 主人公との関係
- 口調サンプル
- アーク登場予定
- 主人公への呼称(敬称レベル)

## 禁則

- 主人公を神扱い・崇拝させない(本人主張は取り合われない設定)
- 頭文字がかち合うキャラを作らない(cast/_index.md 確認)
- 説明セリフを喋らせない
- 現地人に VRMMO システム機能を付与しない
