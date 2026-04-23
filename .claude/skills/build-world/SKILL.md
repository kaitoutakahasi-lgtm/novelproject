---
name: build-world
description: |
  Phase 3 で使う。本作の二層世界観(game-era / current-era)と 5 時代層
  (攻略期/殺伐期/拡散期/沈静期/孤独期)を構築するSkill。世界観ファイル群を
  一貫性を保って生成する。references/two-era-template.md を参照する。
---

# 世界観構築 Skill

## 目的

本作の二層世界観を段階的に構築する:

1. **game-era** — 元 VRMMO 仕様(3 万人が閉じ込められた当時の設定)
2. **current-era** — Y60+ 時点のプレイヤー絶滅後の現在
3. **5 時代層** — 攻略期 / 殺伐期 / 拡散期 / 沈静期 / 孤独期

## 使い方

1. 対象ファイルを指定(game-era.md, current-era.md, eras/era-XX.md 等)
2. references/two-era-template.md の構造に沿って生成
3. world/glossary.md に新規造語があれば同時登録
4. _meta/timeline.md と整合性を取る

## 禁則

- 造語の独断追加(glossary.md 登録前に本文で使わない)
- 時代層の齟齬(Y10 の出来事が Y5 時点で既知になる等)
- NPC 社会を主人公視点だけで描く(NPC 自身の合理が必要)
- プレイヤー側のシステム機能を NPC に付与(客血はシステム機能なし)
