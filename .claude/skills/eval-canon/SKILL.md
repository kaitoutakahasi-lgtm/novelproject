---
name: eval-canon
description: |
  設定矛盾を検出する評価器Skill。本作の二層世界観・5時代層・glossary・timeline・
  cast との不整合を厳密にチェックする。Phase 7 で章執筆後に使用。
---

# 設定矛盾評価器 Skill

## 起動時必読

- CLAUDE.md(世界設定の核)
- world/game-era.md
- world/current-era.md
- world/magic-and-system.md
- world/system-residue.md
- world/glossary.md
- _meta/timeline.md
- cast/_index.md
- 対象章

## チェック項目

### 時系列
- [ ] 章内の主人公年齢と _meta/timeline.md が整合
- [ ] 登場 NPC 世代と時代層が整合
- [ ] 過去の出来事の前後関係が timeline と整合

### 用語
- [ ] 固有名詞が world/glossary.md に登録済み
- [ ] 表記ゆれなし(漢字/かな/カタカナの一貫性)
- [ ] 造語の初出・再出が一致

### 地理
- [ ] 訪問地が world/regions/<name>.md の描写と整合
- [ ] 移動経路と独占移動手段が geography.md と整合
- [ ] 時代層の姿(その時代の地域の状態)が整合

### キャラ
- [ ] 登場キャラの口調が cast/<name>.md と一致
- [ ] 主人公への呼称が設定通り
- [ ] 主人公を神扱いする NPC がいない(本人主張は取り合われない設定)

### システム残滓
- [ ] プレイヤー UI の扱いが system-residue.md と整合
- [ ] 客血にシステム機能を付与していない
- [ ] フレンド機能の仕様(消えたら死亡)を守っている

## 出力形式

```
| 矛盾種別 | 本文箇所(行番号) | 設定側参照 | 修正方針 |
|---|---|---|---|
```

矛盾なしなら「監査通過」の一行で。
