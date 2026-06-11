# marp-test — Marp テーマ開発メモ

## Codex へ
- コメント、description、ドキュメントを書くときは、ユーザーから特別な指定がない限り日本語で書くこと。厳守！

## Git
- GitHub Flow: 必ず main を最新化して feature ブランチを切って作業する
- PRのタイトル、コミットメッセージは Conventional commit
- 日本語

## 基本ワークフロー
- 通常作業の入口は `task` コマンドを使う。
- 新しいスライドを作る: `task new -- title`
- スライドを HTML / PDF にコンパイルする: `task compile -- slides/yyyymmdd_title`
- `task compile` は対象ディレクトリの `main.md` から、同じ場所に `main.html` と `main.pdf` を出力する。

## 主要ファイル
- テーマ: `theme/enpitsu-choice.css`
- テーマ登録: `/* @theme enpitsu-choice */`
- 全スライドタイプ確認用サンプル: `slides/_sample/main.md`
- task 定義: `Taskfile.yml`

## スライド作成ルール
- Marp front matter は基本的に `slides/_sample/main.md` と同じ構成にする。
  - `marp: true`
  - `theme: enpitsu-choice`
  - `size: 16:9`
  - `paginate: true`
- タイトルスライドと締めスライドは `<!-- _class: title -->` を使う。
- セクション区切りは `<!-- _class: section -->` を使う。
- 2カラムは `<!-- _class: cols -->` と `<div class="col">` を使って左右を分ける。
- 右画像・左テキストのレイアウトは `<!-- _class: text-image -->`、本文側は `text-main`、画像側は `image-support` を使う。
- 上画像・下メッセージのレイアウトは `<!-- _class: image-message -->`、画像側は `image-wide`、下部メッセージは `message` を使う。
- 画像素材は各スライドディレクトリの `materials/` 配下に置き、Markdown からは `materials/icon.jpg` のような相対パスで参照する。
- スライド個別の CSS が必要な場合は、`main.md` に長い `<style>` を直接埋め込まず、同じスライドディレクトリに `deck.css` などの外部 CSS として切り出す。`main.md` 側では `<style>@import url("./deck.css");</style>` のように参照だけを書く。

## テキスト・装飾ルール
- 基本文字は Tsukushi A Round Gothic Regular を前提にする。
- 箇条書きは第3レベルまでに留め、第4レベル以上は使わない。
- 箇条書きの目安サイズ:
  - 第1レベル: 28pt
  - 第2レベル: 24pt
  - 第3レベル: 20pt
- 強調色は用途を分ける。
  - 青 `text-blue` / `#0096FF`: 基本の強調色。
  - 黄 `text-yellow` / `#FFD478`: 青との対比用。視認性が低いため本文色には使わず、図形やボックス中心に使う。
  - 赤 `text-red` / `#E61C10`: 強い強調用。多用せず、本当に目立たせたい箇所に限定する。
- ボックス装飾は `marp-box` に色クラスを組み合わせる。
  - `marp-box-blue`
  - `marp-box-pink`
  - `marp-box-yellow`
- 比較表は通常の Markdown テーブルではなく、必要に応じて `compare-table` を使う。
  - 評価表示は `result good`、`result neutral`、`result bad` を使い分ける。
  - 評価理由は `reason` に入れる。
- 引用、コード、脚注の見た目はテーマ側で定義されているため、サンプルの構造に合わせる。
- 脚注や出典など優先度の低い補足は `<p class="footnote">...</p>` でスライド下部に置く。

## 手動プレビュー生成
`task` ワークフローで足りない出力が必要なときだけ使う。

- PNG:
  `npx @marp-team/marp-cli slides/_sample/main.md --theme theme/enpitsu-choice.css --images png --output preview/`
- HTML:
  `npx @marp-team/marp-cli slides/_sample/main.md --theme theme/enpitsu-choice.css --html --output /tmp/preview.html && open /tmp/preview.html`
- PNG 出力ファイルは拡張子なしで `preview.001`, `preview.002` のような連番になるが、中身は PNG。

## 画像ツール制約
- `sips -c H W` は中央クロップのため上部切り出し不可。
- `convert`（ImageMagick）・`ffmpeg`・PIL は未インストール。
- SVG の base64:
  `python3 -c "import base64; print(base64.b64encode(svg.encode()).decode())"`

## CSS 技法メモ
- 幅制限付き区切り線: `repeating-linear-gradient` + `background-size: Wpx 4px` + `background-repeat: no-repeat`
- SVG 三角形回転: `transform="translate(cx,cy) rotate(deg) translate(-halfW,-halfH)"` で重心を軸に回転
- `section::before` に SVG とグラデーションを重ねる場合は、`background-image` の複数値を使う。
