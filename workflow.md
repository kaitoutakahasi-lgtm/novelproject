# ワークフロー定義

本プロジェクトは **TP (テーマ駆動型プランナー) + CP/MP 要素** の制作フローを採用。
葦沢式**ストーリー・エンジニアリング**の公式7ステップ

> アイデア → コンセプト → 世界観 → キャラクター → あらすじ → 本文 → 推敲

に、本作固有の2つの前倒し

> (CP要素) 主人公の声を先取りで固める
> (MP要素) 各アークのカタルシス一文を先に置く

を挿入したフローとする。

実行時は Claude Code の Plan mode (Shift+Tab) を推奨。
段階実行は「Phase N まで実行して」で指示する。夜間仕掛け用途のみ全自動を使う。

---

## Phase 0: ブートストラップ(ステップ外 — 基盤)

ゴール: プロジェクトのディレクトリ構造と作品憲法を物理的に存在させる

### 成果物
- ディレクトリツリー一式
- CLAUDE.md 初版 / workflow.md 初版
- .claude/rules/tone.md, .claude/rules/taboos.md
- concept/writer-type.md (作家タイプ診断済み)

### 使うSkill
なし(スクラッチで作る)

### 人間チェックポイント
- 作家タイプ診断の結果が自分の実感と合っているか(違えば作り直す)
- CLAUDE.md が150行以内か

---

## Phase 1: アイデア・コンセプト・テーマ・ビジョン(ステップ①〜②)

ゴール: 葦沢氏が区別する三者 — コンセプト / テーマ / ビジョン — を分離して固める

### 成果物
- concept/pitch.md (企画書・ログライン)
- concept/concept.md (「もし〜なら?」の仮定条件)
- concept/theme.md (伝えたいメッセージ)
- concept/vision.md (作品全体に一貫する作家性の核)

### 使うSkill
- refine-concept (コンセプトとテーマの混同を避けるためのディレクション)

### 人間チェックポイント(重要)
葦沢氏が最も警戒している混同を避ける:

- コンセプトに「喪失と和解」のような**メッセージ**が混じっていないか
- テーマに「もし〜なら?」の**仮定条件**が混じっていないか
- ビジョンに具体的プロットが混じっていないか(ビジョンは姿勢・配合まで)

### Phase 1 完了判定
concept/concept.md が「もし〜なら?」の一文で始まり、concept/theme.md が一行の宣言文で始まり、concept/vision.md が配合(フリーレン型 × ウェンティ型)を明記している

---

## Phase 2: 声のバイブルと評価器の準備(CP要素の先取り)

ゴール: 本作の核である「ウェンティ型腐った声」の作法を Skill として実装する
(本作固有の前倒し。通常のTPフローでは④キャラのタイミングで扱うが、本作は声が作品の印象を決定するため Phase 2 に持ってくる)

### 成果物
- concept/tone-bible.md (完全版)
- drafts/voice-test_*.md 3-5バージョン(プロローグ試し書き)
- .claude/skills/voice-kamome/ (Skill本体 + references/)
- .claude/skills/eval-voice/ (声評価器Skill)

### 使うSkill
- skill-creator (Claudeビルトインで初期生成)
- voice-kamome (作成後すぐ実運用テスト)
- eval-voice (作成後すぐ実運用テスト)

### 人間チェックポイント(重要)
- voice-kamome/references/ の中身を人間が必ず全部目を通す(ここが命)
- 致命的なミスや、AIが勝手に作った一般化軸(例: 比喩Skillが「書く/テキスト系」で統一されがちな罠)を排除
- 試し書きのベスト1本を concept/tone-bible.md の基準サンプルに採用

### Phase 2 完了判定
voice-kamomeスキルを使って書いた200字のテストショートが、3回中2回以上「ウェンティ型腐った声」として成立する

---

## Phase 3: 世界観(ステップ③)

ゴール: アーク01-03の設計に必要な世界観素材を揃える。本作は**二層世界観 + 5時代層 + 地域カード + プレイヤー文化の変質ログ**を扱うため、通常のTPフローより世界観設計の比重が大きい。

### 成果物
- world/game-era.md (元VRMMO仕様)
- world/current-era.md (プレイヤー絶滅後の現在の総観)
- world/magic-and-system.md (魔法/スキル/死・蘇生/寿命AF等)
- world/system-residue.md (【本作固有】UI残存・ログアウト無反応・フレンド機能・客血の無機能)
- world/glossary.md (固有名詞登録制)
- world/geography.md (6大陸+海路、破壊済テレポ網、独占移動手段国3-4)
- world/eras/ (【本作固有】Y0-5攻略期/Y5-15殺伐期/Y15-35拡散期/Y35-60沈静期/Y60+孤独期の5ファイル)
- world/regions/ (【本作固有】地域カード、各時代の姿を時間軸で保持)
- world/npc-society.md (【本作固有】NPC社会全体像)
- world/culture-drift.md (【本作固有】プレイヤー文化のNPC独自解釈への変質ログ)
- world/player-npc-history.md (【本作固有】客人⇄NPC相互認識の変遷史)
- _meta/timeline.md (Y0〜60+の5時代区分ベース)

### 使うSkill
- build-world (世界観構築)
- region-card (【本作固有】地域カード作成)
- eval-canon (設定矛盾監査)

### 人間チェックポイント
- 二層世界観(game-era/current-era)が分離されているか
- 5時代層それぞれで「支配的な客人・主要事件・生まれた文化」が異なっているか
- 各地域カードに時間軸(各時代の姿)が入っているか
- culture-drift.md に「プレイヤー文化が60年でどう変質したか」の具体ケースが3件以上あるか
- system-residue.md に「何が残って、何が使えて、何が消えたか」が明記されているか
- glossary に登録された造語が本作の雰囲気(王道ハイファンタジー)に合っているか

---

## Phase 4: キャラクター(ステップ④)

ゴール: 主人公 + 主要故客人 + 派閥 + 黒歴史遺産を揃える。
本作は**主人公の知識ギャップ・客人間関係グラフ・ギルド派閥興亡史**を扱うため、通常より深い。

### 成果物
- cast/protagonist.md (一人称ぼく・見た目少年・客人・元首残骸)
- cast/protagonist-knowledge.md (【本作固有】主人公の知識ギャップ・誤解リスト)
- cast/former-players/ 主要5-8人
- cast/former-players/_relationships.md (【本作固有】客人間関係グラフ・主人公視野外の関係)
- cast/factions/ (【本作固有】主要ギルド・派閥5-10個と主人公の所属履歴)
- _meta/player-roster.md (初期3万人の統計・関係温度・生死)
- legacy/ 主要3-5件
- legacy/authentication-gimmick.md (【本作固有】主人公認証ギミック仕様)
- legacy/_index.md (使用済み/未使用ステータス)

### 使うSkill
- design-character (通常キャラシート生成)
- former-player-sheet (故客人専用シート)
- knowledge-gap (【本作固有】主人公の誤解・知らなかったこと管理)
- relationship-graph (【本作固有】客人間関係整合性チェック)
- eval-canon (設定矛盾監査)

### 人間チェックポイント
- 主人公の一人称「ぼく」・爺の自認なし・見た目少年が徹底されているか
- 故客人の関係温度マップ(親友/仲間/顔見知り/敵対)が成立しているか
- **主人公視野外の関係**が最低3つ設計されているか(例: AとBが実は深く繋がっていた、CがDを殺していた等)
- 黒歴史(legacy)の未使用ステータスが正しく付いているか
- 各故客人の「生前の最後の言葉/状況」と「主人公が知らなかったこと」が書けているか
- 主要ギルド/派閥5-10個のうち、主人公が所属したものと敵対したものがそれぞれ最低1つあるか

---

## Phase 5: マスタープロット + 巡礼ルート + カタルシス一文(ステップ⑤ + MP前倒し)

ゴール: 全体アーク計画 + カタルシス着地点の先取り配置 + 伏線計画 + 巡礼ルートの表裏設計

### 成果物
- plot/master.md (全体概観)
- _meta/arc-map.md (黒歴史消費計画込み・各アークのカタルシス一文集)
- _meta/pilgrimage-map.md (【本作固有】全アーク巡礼ルート、表の目的/裏の目的/訪問する故人関連地)
- _meta/foreshadow-table.md (時間差開示の二層: 初見層/再読層)
- .claude/skills/catharsis-frieren/ (カタルシス型Skill)
- .claude/skills/eval-catharsis/ (カタルシス評価器)
- .claude/skills/foreshadow-layer/ (【本作固有】伏線の二重読み構造評価器)

### 使うSkill
- outline-synopsis
- catharsis-frieren
- eval-catharsis (マスタープロット段階で適用)
- foreshadow-layer (【本作固有】伏線の二層設計レビュー)

### 人間チェックポイント(重要 — 本文展開前のコンパクト段階)
葦沢氏の最重要TIPS通り、ここで徹底的に潰す:

- **各アークのカタルシス一文**が全アーク分書けているか:
  「主人公は ___ と思っていたが、___ だったと遅すぎる形で理解する」
- **巡礼ルートの表/裏**が各アークで設計されているか(表=NPC依頼等、裏=故人の痕跡の回収)
- 黒歴史素材の消費タイミングが早期に集中していないか(中盤〜終盤に配分)
- 伏線の**初見層(軽い装飾)**と**再読層(真意)**が foreshadow-table.md で分離されているか
- 伏線の設置と回収のアーク割り当てに無理がないか
- Arc 01(エルフ王国家督争い、1年旅程、2章構成)が具体化されているか

### 本作固有の Arc 01 の骨格(参考)
- Ch 01「消えたフレンド」: 訃報(フレンド消失) → 宿屋日常 → 腰が重い → 出航
- Ch 02「森の縁」: 通常船数ヶ月 → 森の縁 → 30年待った腹心 → 森の回廊 → 王都到着
- Ch 03以降: 家督争い本編

---

## Phase 6: 第1アーク詳細あらすじ(ステップ⑤の精緻化)

ゴール: アーク01のシーン単位ビート

### 成果物
- plot/arcs/arc01_<slug>/plot.md
- plot/arcs/arc01_<slug>/scenes.md (シーンビート)

### 使うSkill
- arc-plot
- outline-synopsis
- eval-catharsis (プロット段階で適用)

### 人間チェックポイント(超重要)
- カタルシス一文が5幕構成の「4. 転換」で成立しているか
- シーンごとの役割タグ(A/B/C/D/E)が被っていないか
- 本文展開前にここで潰す(本文化後の修正は葦沢氏が指摘する通り最も高コスト)

---

## Phase 7: 第1アーク本文執筆 + 推敲(ステップ⑥ + ⑦)

ゴール: アーク01の全章を書き切り、推敲も通す

### 成果物
- chapters/arc01/ch01.md 〜 chXX.md
- reviews/arc01_chNN_review.md (章ごと)

### 使うSkill (1章につき以下の順)
1. scene-draft (初稿執筆)
2. voice-kamome (執筆時の参照)
3. eval-voice (執筆後の声チェック)
4. eval-canon (設定矛盾チェック)
5. eval-catharsis (章末〜章全体の着地評価)
6. revise-pass (推敲A→B→Cの3層)

### 人間チェックポイント
- 1章ごとに評価器3種を順に走らせる
- voice 指摘を反映してから次章へ
- 5章ごとに foreshadow-table.md 更新

---

## Phase N: 継続サイクル(ステップ⑥⑦の反復)

Phase 6-7 をアークごとに繰り返す。

5アーク終了ごとに:
- 全キャラ設定の更新確認
- マスタープロットとの乖離確認
- 伏線回収スケジュール調整
- 各Skillのreferences/に新しい実例を追加(Skills自体の成長)

---

## 7ステップ ↔ Phase 対応表

| 葦沢式 7ステップ | 本作 Phase | 備考 |
|---|---|---|
| ① アイデア | Phase 1 | pitch.md |
| ② コンセプト | Phase 1 | concept.md + theme.md + vision.md で三分割 |
| (本作独自・CP前倒し) | Phase 2 | 声の先取り |
| ③ 世界観 | Phase 3 | 二層世界観 |
| ④ キャラクター | Phase 4 | 主人公 + 故プレイヤー + 遺産 |
| ⑤ あらすじ | Phase 5-6 | マスタープロット → アーク詳細 |
| (本作独自・MP前倒し) | Phase 5 | カタルシス一文の先置き |
| ⑥ 本文 | Phase 7 | scene-draft + voice-kamome |
| ⑦ 推敲 | Phase 7 | 評価器3種 + revise-pass |

---

## 実行コマンド例

```
# Plan mode で段階実行
> Phase 3 まで実行して

# 1章書いて評価まで通す
> /scene-draft 01 03 「主人公が廃墟となった宗教国家の外周で巡礼者に出会う」で書いて、
> そのあと voice-kamome / eval-voice / eval-catharsis で評価して

# 新アーク設計
> /arc-plot でアーク04の詳細を設計して。主題の故人は [故人名]
```
