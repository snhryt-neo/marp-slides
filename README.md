# marp-slides

## Overview

Marp とカスタムテーマ `enpitsu-choice` を使って、Markdown からスライドを作成するためのリポジトリです。

主な構成は次のとおりです。

| パス | 内容 |
| :--- | :--- |
| `theme/enpitsu-choice.css` | Marp 用のカスタムテーマ |
| `slides/_sample/main.md` | スライドタイプ確認用のサンプル |
| `Taskfile.yml` | スライド作成・コンパイル用タスク |

## Prerequisites

以下のツールを使います。

- [Task](https://taskfile.dev/)
- Node.js / npm

PDF 出力では Marp CLI が内部でブラウザ実行環境を使います。環境によっては追加の依存関係が必要になる場合があります。

## Setup

なし。`npx @marp-team/marp-cli` 経由でインストールなしで Marp スライドを作成します。

## Usage

### 新しいスライドを作る

```bash
task new -- title
```

実行すると、`slides/yyyymmdd_title/` が作成されます。

生成される主なファイルは次のとおりです。

| パス | 内容 |
| :--- | :--- |
| `slides/yyyymmdd_title/main.md` | スライド本文 |
| `slides/yyyymmdd_title/materials/` | 画像などの素材置き場 |

### スライドをコンパイルする

```bash
task compile -- slides/yyyymmdd_title
```

対象ディレクトリの `main.md` から、同じディレクトリに `main.html` と `main.pdf` を出力します。

### スライド作成ルール

Marp front matter は基本的に `slides/_sample/main.md` と同じ構成にします。

```yaml
---
marp: true
theme: enpitsu-choice
size: 16:9
paginate: true
---
```

よく使うスライドクラスは次のとおりです。

| 用途 | クラス |
| :--- | :--- |
| タイトル・締めスライド | `<!-- _class: title -->` |
| セクション区切り | `<!-- _class: section -->` |
| 2カラム | `<!-- _class: cols -->` |
| 右画像・左テキスト | `<!-- _class: text-image -->` |
| 上画像・下メッセージ | `<!-- _class: image-message -->` |

画像素材は各スライドディレクトリの `materials/` 配下に置き、Markdown からは `materials/icon.jpg` のような相対パスで参照します。
