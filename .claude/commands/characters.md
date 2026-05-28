指定された章の登場キャラクター情報をまとめて読み込むコマンド。

## 手順

1. `characters/index.md` を読み、引数で指定された章番号（例: `5`, `ch5`, `Ch.5`）に該当する行を探す
2. その行の「登場キャラクター」列からキャラクター名を抽出する
3. 以下の名前→ファイル名対応表に基づき、該当するキャラクターファイルをすべて読み込む:
   - エルヴィン → `characters/elvin.md`
   - ルシウス → `characters/lucius.md`
   - アリシア → `characters/alicia.md`
   - レオン → `characters/leon.md`
   - ガレス → `characters/gares.md`
   - トーマス → `characters/thomas.md`
   - マクシミリアン → `characters/maximilian.md`
   - ロデリック王 → `characters/roderick.md`
   - アルトゥス → `characters/altus.md`
   - グレタ → `characters/greta.md`
4. 各キャラクターファイルの内容をまとめて表示する
5. 「手紙のみ」「言及のみ」「遠景」などの注記がある場合はその旨も伝える

## 引数

$ARGUMENTS — 章番号（例: `5`, `ch12`, `Ch.24`）。複数章を指定可能（例: `5-7`, `5,6,7`）

## 出力形式

```
【Ch.X 登場キャラクター】
視点: ○○
登場: ○○、○○、○○

---
（各キャラクターファイルの内容）
---
```
