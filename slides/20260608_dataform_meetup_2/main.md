---
marp: true
theme: enpitsu-choice
size: 16:9
paginate: true
---

<style>
/* この資料専用の微調整。テーマ本体は変更しない。 */
section.lead p,
section.lead li {
  font-size: 30px;
}

section.compact p,
section.compact li {
  font-size: 26px;
  line-height: 1.42;
  margin-bottom: 6px;
}

section.compact li li {
  font-size: 23px;
}

section.compact li li li {
  font-size: 20px;
}

section.dense p,
section.dense li {
  font-size: 24px;
  line-height: 1.34;
  margin-bottom: 4px;
}

section.dense li li {
  font-size: 21px;
}

section.dense li li li {
  font-size: 19px;
}

section.big-message {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 96px;
  text-align: center;
}

section.big-message h1 {
  position: static;
  white-space: normal;
  overflow: visible;
  font-size: 46px;
  line-height: 1.35;
  text-align: center;
}

section.big-image {
  display: flex;
  align-items: center;
  justify-content: center;
}

section.big-image h1 {
  white-space: normal;
}

section.big-image img {
  display: block;
  width: 520px;
  max-width: 96%;
  max-height: 560px;
  margin: 0 auto;
  object-fit: contain;
  position: relative;
  z-index: 2;
}

section.profile .profile-grid {
  display: grid;
  grid-template-columns: 1.1fr 0.9fr;
  gap: 36px;
  align-items: center;
  position: relative;
  z-index: 2;
}

section.profile .profile-logo {
  width: 300px;
  height: 300px;
  object-fit: cover;
  border-radius: 18px;
  display: block;
  margin: 0 auto 26px;
}

section.profile .article {
  width: 100%;
  border: 1px solid #d6dee8;
  border-radius: 8px;
}

section.profile .version {
  display: inline-block;
  margin-top: 20px;
  padding: 10px 18px;
  border-radius: 8px;
  background: rgba(255, 212, 120, 0.42);
  font-size: 24px;
  font-weight: bold;
}

section.pipeline {
  padding-left: 58px;
  padding-right: 42px;
}

section.pipeline .pipeline-svg {
  display: block;
  width: 106%;
  max-height: 548px;
  margin-left: -3%;
  object-fit: contain;
  position: relative;
  z-index: 2;
}

.pipeline-diagram {
  position: relative;
  z-index: 2;
  display: grid;
  grid-template-columns: 225px 1fr 180px;
  gap: 18px;
  align-items: stretch;
  font-size: 16px;
}

.pipe-zone {
  border: 2px solid #d0d0d0;
  border-radius: 8px;
  padding: 12px;
  background: #fff;
}

.pipe-zone h2 {
  display: block;
  font-size: 22px;
  margin-bottom: 10px;
}

.pipe-zone h2::before {
  content: none;
}

.pipe-stack {
  display: grid;
  gap: 8px;
}

.pipe-box {
  border: 1.5px solid #9fb6ca;
  background: rgba(173, 216, 240, 0.45);
  border-radius: 6px;
  padding: 7px 8px;
  text-align: center;
  line-height: 1.22;
  min-height: 34px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow-wrap: anywhere;
}

.pipe-box.yellow {
  background: rgba(255, 212, 120, 0.42);
  border-color: #d7b25a;
}

.pipe-box.pink {
  background: rgba(220, 120, 110, 0.25);
  border-color: #c8847b;
}

.pipe-arrow {
  text-align: center;
  color: #7a7a7a;
  font-size: 18px;
  line-height: 1;
}

.pipe-marts {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 8px;
}

section.code-split .code-wrap {
  display: grid;
  grid-template-columns: 0.65fr 1.35fr;
  gap: 24px;
  align-items: center;
  position: relative;
  z-index: 2;
}

section.code-split h2 {
  font-size: 24px;
}

section.code-split .screenshot-img {
  width: 100%;
  border: 1px solid #d6dee8;
  border-radius: 8px;
  background: #fff;
}

section.code-split .format-img {
  max-height: 420px;
  object-fit: contain;
}

section.code-split.bqrc-slide {
  padding-left: 72px;
  padding-right: 55px;
}

section.code-split.bqrc-slide h1 {
  white-space: normal;
  overflow: visible;
}

section.code-split.bqrc-slide .bqrc-board {
  position: relative;
  z-index: 2;
  display: grid;
  grid-template-columns: 0.98fr 1.12fr;
  gap: 34px;
  align-items: start;
}

section.code-split.bqrc-slide .bqrc-panel {
  position: relative;
  min-height: 386px;
  padding: 22px;
  box-sizing: border-box;
  border: 1px solid #d6dee8;
  border-radius: 8px;
  background: #fff;
}

section.code-split.bqrc-slide .bqrc-format-img {
  display: block;
  width: 112%;
  max-width: none;
  margin-top: 16px;
  transform: translateX(-6%);
}

section.code-split.bqrc-slide .bqrc-code {
  margin: 0;
  min-height: 318px;
  padding: 18px 20px;
  font-size: 16px;
  line-height: 1.36;
  white-space: pre;
  overflow: hidden;
}

section.code-split.bqrc-slide .bqrc-code code {
  font-size: 1em;
}

section.code-split.bqrc-slide .bqrc-format-note {
  display: inline-block;
  margin-bottom: 6px;
  padding: 8px 14px;
  border-radius: 6px;
  background: rgba(255, 212, 120, 0.38);
  border: 1.5px solid rgba(255, 147, 0, 0.5);
  font-size: 22px;
  font-weight: bold;
}

section.code-split.bqrc-slide .comment {
  color: rgba(73, 73, 73, 0.72);
}

section.code-split.bqrc-slide .comment-blue {
  color: var(--accent2);
  font-weight: bold;
}

section.code-split.bqrc-slide .comment-yellow {
  color: #7a5a00;
  font-weight: bold;
}

section.code-split.bqrc-slide .comment-red {
  color: var(--accent1);
  font-weight: bold;
}

section.code-wide pre {
  font-size: 14px;
  line-height: 1.22;
  margin-top: 0;
  max-height: 500px;
}

section.code-wide h1 {
  font-size: 30px;
  white-space: normal;
  overflow: visible;
}

section.code-wide pre,
section.code-wide pre code {
  white-space: pre-wrap;
  overflow-wrap: anywhere;
}

section.snapshot-split h1 {
  font-size: 32px;
  white-space: normal;
  overflow: visible;
}

section.snapshot-split .snapshot-wrap {
  display: grid;
  grid-template-columns: 0.86fr 1.14fr;
  gap: 30px;
  align-items: start;
  position: relative;
  z-index: 2;
}

section.snapshot-split p,
section.snapshot-split li {
  font-size: 25px;
  line-height: 1.38;
  margin-bottom: 7px;
}

section.snapshot-split li li {
  font-size: 22px;
}

section.snapshot-split pre {
  margin-top: 0;
  font-size: 12px;
  line-height: 1.08;
  max-height: 550px;
  padding: 12px 14px;
}

section.snapshot-split pre,
section.snapshot-split pre code {
  white-space: pre-wrap;
  overflow-wrap: anywhere;
}

section.code-wide .hljs-keyword,
section.code-wide .hljs-built_in,
section.code-wide .hljs-type,
section.snapshot-split .hljs-keyword,
section.snapshot-split .hljs-built_in,
section.snapshot-split .hljs-type {
  color: #0096FF;
  font-weight: bold;
}

section.code-wide .hljs-literal,
section.code-wide .hljs-number,
section.snapshot-split .hljs-literal,
section.snapshot-split .hljs-number {
  color: #E61C10;
}

section.code-wide .hljs-operator,
section.snapshot-split .hljs-operator {
  color: #7a5a00;
}

section.screenshot img {
  border: 1px solid #d6dee8;
  border-radius: 8px;
  background: #fff;
}

section.screenshot .image-support img {
  max-height: 360px;
}

section.repository img {
  border: 1px solid #d6dee8;
  border-radius: 8px;
}

section.repository h1 {
  font-size: 30px;
  white-space: normal;
  overflow: visible;
}

section.repository .repo-grid {
  display: grid;
  grid-template-columns: 0.72fr 1.28fr;
  gap: 28px;
  align-items: center;
  position: relative;
  z-index: 2;
}

section.repository .repo-grid img:first-child {
  width: 100%;
  max-height: 430px;
  object-fit: contain;
}

section.repository .repo-grid img:last-child {
  width: 100%;
  max-height: 460px;
  object-fit: contain;
}

section.hire h1 {
  white-space: normal;
  overflow: visible;
}
</style>

<!-- _class: title -->

# Dataformのリポジトリを立ち上げるときにまずやること

品原 悠杜 (@snhrytdesu)  
Dataform Meetup #2 (2026-06-08)

---

# 本日話すこと
<!-- _class: lead -->

- 今年の3月に BigQuery x Dataform でデータ基盤をゼロから立ち上げる機会があった
- そのときに最初にやっておいてよかったことをご紹介
  - コストモニタリング用mart整備
  - エージェントハーネス
  - CI/CD
- 最初にやっておくとなおよしだが、後から取り入れても有効な話ばかりだと思います。誰かの参考になれば！

---

# 自己紹介
<!-- _class: profile -->

<div class="profile-grid">
<div>

- 品原 悠杜 (@snhrytdesu)
- 日本に200人ぐらいしかいない名字
- Dataform の呪縛に囚われている人 ↓
- フリーランス
  - ex マイベスト ← アイデミー ← NTTCom

<span class="version">公開予定ver.</span>

</div>
<div>
  <img class="profile-logo" src="materials/profile_logo.jpg" alt="snhryt ロゴ">
  <img class="article" src="materials/dataform_article.png" alt="2025年にDataformを使うことへの葛藤などなど">
</div>
</div>

---

# 自己紹介
<!-- _class: profile -->

<div class="profile-grid">
<div>

- 品原 悠杜 (@snhrytdesu)
- 日本に200人ぐらいしかいない名字
- Dataform の呪縛に囚われている人 ↓
- 無職
  - ex マイベスト ← アイデミー ← NTTCom

<span class="version">投影ver.</span>

</div>
<div>
  <img class="profile-logo" src="materials/profile_logo.jpg" alt="snhryt ロゴ">
  <img class="article" src="materials/dataform_article.png" alt="2025年にDataformを使うことへの葛藤などなど">
</div>
</div>

---

# Excuse
<!-- _class: lead -->

- 当たり前ですが）BigQuery x Dataform でデータ基盤を構築する前提
- 開発環境として Dataform CLI を使ったローカル主体の環境を想定
- クラウド版の IDE を使って開発している方は？→ 今すぐ CLI に乗り換えましょう 🏃🏃🏃🏃🏃🏃
- ハーネスの定義は諸説あるので、「AIで開発するための足回りの話」ぐらいの心づもりでお聞きいただけると幸いです m(_ _)m

---

<!-- _class: section -->

# コストモニタリング用mart整備

---

# どうせみんな BigQuery のコストは論点になる
<!-- _class: lead -->

- 組織によって優先度や重要度は様々あるが、いつか必ず、コストと真面目に向き合わないといけない時がやってくる
- 特に、社内のデータ活用が一定進んでくると、スプレッドシートのデータコネクタによる野良クエリの発行が横行する

---

# なので、最初から全力でモニタリングの足場を整える
<!-- _class: big-image -->

![始めから全開だ](materials/start_full_power.png)

---

# なので、最初から全力でモニタリングの足場を整える
<!-- _class: compact -->

- `INFORMATION_SCHMA.JOBS` を使って、以下のような粒度で `total_bytes_billed` をモニタリングしているチームは多いと思う
  - date x user_email
  - date x referenced_tables
  - query (topN)
- しかし、これだと足りないことが多い。最初から以下をBQに連携しておこう
  - Cloud Audit Logs: スプシのデータコネクトによる課金がシートURL単位でモニタリングできるようになる
  - user_email から所属への変換用テーブル: 所属ごとに集約して利用傾向が追えるようになる
    - 注意：このテーブルを最新化する運用には人事部門などの協力が必須。調整ファイト

---

# パイプラインイメージ
<!-- _class: pipeline -->

<img class="pipeline-svg" src="materials/pipeline.svg" alt="BigQuery と Dataform のパイプラインイメージ">

---

# tips1: INFORMATION_SCHEMA の日次スナップショット保管も検討を
<!-- _class: snapshot-split -->

<div class="snapshot-wrap">
<div>

- Dataform でモデリングして、INFORMATION_SCHEMA は日次スナップショットをパーティショニングテーブルとして保管するようにした
- `JOBS`
  - 情報の宝庫
  - 180日までしか履歴が遡れないので、コストが許すなら永続化する
- `TABLE_STORAGE`
  - 最新データのみで履歴が追えない
  - 履歴があるとストレージコストの増分試算に便利

</div>
<div>

```sql
config {
  type: "incremental",
  schema: "staging",
  bigquery: {
    partitionBy: "date",
    clusterBy: ["user_email"],
  },
  uniqueKey: ["job_id"],
  protected: true,
}

pre_operations {
  declare checkpoint_timestamp default(
    ${
      when(
        incremental(),
        `select max(creation_time) from ${self()}`,
        `timestamp("2026-01-01 00:00:00 UTC")`
      )
    }
  )
}

select
  date(creation_time, "Asia/Tokyo") as date,
  *
from
  `region-${dataform.projectConfig.defaultLocation}.INFORMATION_SCHEMA.JOBS`
where
  creation_time > checkpoint_timestamp
```

</div>
</div>

---

# tips2: bytes→コスト変換（概算）UDFを作っておくと使いまわしが効きやすい
<!-- _class: code-wide -->

```sql
config {
  type: "operations",
  schema: "udfs",
  hasOutput: true,
  tags: ["udfs"],
}

create or replace function ${self()}(
  byte_count int64,
  cost_category string
)
returns float64
as (
  case cost_category
    when "computing" then safe_divide(byte_count, pow(1024, 4)) * 6.25
    when "active_logical_storage" then safe_divide(byte_count, pow(1024, 3)) * 0.000031507 * 24
    when "longterm_logical_storage" then safe_divide(byte_count, pow(1024, 3)) * 0.000021918 * 24
    when "active_physical_storage" then safe_divide(byte_count, pow(1024, 3)) * 0.000054795 * 24
    when "longterm_physical_storage" then safe_divide(byte_count, pow(1024, 3)) * 0.000027397 * 24
    else error(format("Unsupported cost category: %s", cost_category))
  end
)
options (
  description = "バイト数とコストカテゴリからBigQuery利用コストの概算をUSDで返す。東京リージョンの公開単価を使用し、無料枠、契約割引、税、丸め、為替換算は考慮しない。ストレージはGiB-hour単価を24倍した1日分"
);
```

---

<!-- _class: section -->

# 2. エージェントハーネス

---

# `bq query` コマンドを直接叩かせない
<!-- _class: compact -->

- AI に自律してクエリを書かせようと思ったら、コードベースだけではなく、既存のテーブルの中身も見て開発させたい → `bq query`
- ただし、ノーガードでクエリを叩かせると、BigQuery 側のコスト観点や、AI 側のトークン消費観点で懸念がある
- `make query` のようにショートカットを定義する
  - .bigqueryrc で最大サイズや出力フォーマットを固定してリポジトリ管理
  - デフォルトでは $HOME のファイルを見に行くので、向き先をリポジトリに強制するために`make query` = `bq query --bigqueryrc .bigueryrc “SQL”` のようにwrapする
  - その上で、settings.json で `Bash(bq query*)` を deny しておく（Claude Code の場合）

---

# .bigqueryrc の例
<!-- _class: code-split bqrc-slide -->

<div class="bqrc-board">
  <div class="bqrc-panel">
<pre class="bqrc-code"><code>[global]
--apilog=stdout
<span class="comment comment-blue"># クエリ結果の出力形式を JSON に固定</span>
--format=json
--location=asia-northeast1
[query]
--use_legacy_sql=false
<span class="comment comment-yellow"># 出力行数の upper</span>
--max_rows=100
<span class="comment comment-red"># クエリサイズの upper</span>
--maximum_bytes_billed=100000000</code></pre>
  </div>
  <div class="bqrc-panel">
    <div class="bqrc-format-note">`--format` の指定値はこれだけ</div>
    <img class="bqrc-format-img" src="materials/bq_format_help.png" alt="bq query の --format 説明">
  </div>
</div>

---

# テーブルメタデータの mart を作っておくとより便利
<!-- _class: dense -->

- 色々な INFORMATION_SCHEMA を join して、テーブル毎の指標を集約したワイドテーブルを Dataform でモデリングしておく
  - レコード数 / ストレージサイズ
  - freshness
  - 直近 30 日の ジョブ実行回数 / クエリコスト / ジョブ実行ユーザーtopN
  - カラム description 充填率
  - 推奨事項 (INFORMATION_SCHEMA.RECOMMENDATIONS)
  - etc.
- `make report` := `make query “select * from table_report”` のように wrap しておくといろいろ便利
  - `make query` の前にチェック
  - エージェントスキル化して、特定テーブルの健全性レポートを html 出力
  - 「table_report の推奨事項があるテーブルを改善するPR書いて」で丸投げ

---

<!-- _class: section -->

# 3. CI/CD

---

# SQLFluff でコーディングスタイル強制を統一
<!-- _class: text-image screenshot compact -->

<div class="text-main">

- `.sqlfluff` に SQL のコーディングスタイルを記述
- pre-commit や GitHub Actions などで強制適用する
- @hiracky16 さん作の sqlfluff-templater-dataform があるので是非！

</div>

<div class="image-support">
  <img src="materials/sqlfluff_dataform.png" alt="Dataform plugin for SQLFluff">
</div>

---

# リネーム・削除済モデルの自動お掃除
<!-- _class: text-image screenshot compact -->

<div class="text-main">

- リネームする前の古いテーブルが残りっぱなしで、社内から「更新止まってるみたいなんですけど」と問い合わせが来た経験はありませんか？
- 残念ながら、Dataform には、モデル側の変更に追従して BigQuery 側のリソースを自動でリネーム・削除してくれる仕組みがない
- 自作しましょう
- リネーム・削除を検知してPR内で予告をだし、マージ後に BigQuery 側のリソース削除を実施する Action →

</div>

<div class="image-support">
  <img src="materials/bq_cleanup_action.png" alt="BQ テーブル削除予告">
</div>

---

# Dataform Cloud へのワークフロー設定自動反映
<!-- _class: text-image screenshot compact -->

<div class="text-main">

- Dataform Cloud でワークフローを動かす場合、ワークフローの設定はモデリングとは別で管理する必要がある → tag 新設時のスケジューラ設定漏れなどが起こりやすい
- 手動はブルシット。かといって、Terraform にワークフローの責務は持たせたくない
- → JSON ファイル 1 つでクラウド側に設定を自動反映する GitHub Actions を公開しています！（宣伝）

</div>

<div class="image-support">
  <img src="materials/apply_dataform_workflows.png" alt="apply-dataform-workflows の紹介">
</div>

---

<!-- _class: section -->

# Conclusion

---

# まとめ
<!-- _class: compact -->

- Dataform のリポジトリを立ち上げる際にやってよかったことを紹介
- コストモニタリング用mart整備
  - INFORMATION_SCHEMA だけでは不十分になるので、Audit Log やユーザーメタデータも基盤に連携して、最初からがっつり足場を整えておこう
- エージェントハーネス
  - AI に `bq query` で好き勝手やらせない
  - テーブルのメタデータ集約 mart があると便利
- CI/CD
  - コーディングスタイルの統一 by SQLFLuff
  - リネーム・削除済モデルの自動お掃除
  - Dataform Cloud へのワークフロー設定自動反映

---

# 諸々取り入れたリポジトリテンプレートを公開しました（近日公開予定）
<!-- _class: repository -->

<div class="repo-grid">
  <img src="materials/ask_me.png" alt="間に合いませんでした">
  <img src="materials/repository_template.png" alt="Dataform リポジトリテンプレート">
</div>

---

<!-- _class: title hire -->

# I’m for hire!

@snhrytdesu
