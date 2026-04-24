---
marp: true
theme: enpitsu-choice
size: 16:9
paginate: true
---

<!-- _class: title -->

# プレゼンテーションタイトル

yyyy年mm月dd日　発表者名

---

# コンテンツスライドの例

- 箇条書き第1レベル（28pt）
- テキストは Tsukushi A Round Gothic Regular
  - 第2レベル（24pt）
  - サブ項目もすっきり表示
    - 第3レベル（20pt）
    - 第4レベル以上の箇条書きは利用禁止
- <span class="text-blue">基本の強調（アクセントカラー1） #0096FF</span>
- <span class="text-yellow">青と対比で利用。視認性が悪いためテキストカラーでは使わず、図形やボックスでのみ利用する（アクセントカラー2） #FFD478</span>
- <span class="text-red">強めの強調。多用すると目にキツいので、本当に強調したい時だけに限定（アクセントカラー3） #E61C10</span>

---

# 2カラムレイアウト
<!-- _class: cols -->

<div class="col">
<h2>左側</h2>

<ul>
  <li>箇条書き</li>
  <li>箇条書き</li>
</ul>

<div class="marp-box marp-box-blue">xxx</div>

<div class="marp-box marp-box-pink">xxx</div>

</div>

<div class="col">
<h2>右側</h2>

<ul>
  <li>箇条書き</li>
  <li>箇条書き</li>
</ul>

<div class="marp-box marp-box-yellow">xxx</div>

</div>

---

# 右に画像、左にテキスト
<!-- _class: text-image -->

<div class="text-main">
<h2>左側のメッセージを主役にする</h2>

<p>伝えたい要点は左側にまとめます。右側の画像は、本文の理解を助ける補足情報として配置します。</p>

<ul>
  <li>本文は短く、読み切れる量にする</li>
  <li>画像は説明しすぎず、印象を補強する</li>
  <li>左右の情報量を半分ずつにそろえる</li>
</ul>
</div>

<div class="image-support">
  <img src="materials/icon.jpg" alt="えんぴつチョイスのアイコン">
</div>

---

# 上に画像、下にテキスト
<!-- _class: image-message -->

<div class="image-wide">
  <img src="materials/icon.jpg" alt="えんぴつチョイスのアイコン">
</div>

<p class="message">大きな画像で状況を共有し、その下に一番伝えたいメッセージを短く置きます。</p>

---

# テーブル

| 項目 | 内容 | 備考 |
|------|------|------|
| フォント | Tsukushi A Round Gothic | 丸ゴシック系 |
| 背景色 | #FFFFFF | ホワイト |
| アクセント | 赤・青・黄 | えんぴつチョイス |

<table class="compare-table">
  <thead>
    <tr>
      <th>カテゴリ</th>
      <th>観点</th>
      <th>推し</th>
      <th>比較1</th>
      <th>比較2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>A</td>
      <td>観点1</td>
      <td><span class="result good">○ ◎</span><span class="reason">採用しやすい理由</span></td>
      <td><span class="result neutral">△</span><span class="reason">一部条件つき</span></td>
      <td><span class="result bad">×</span><span class="reason">懸念が大きい</span></td>
    </tr>
    <tr>
      <td>A</td>
      <td>観点2</td>
      <td><span class="result good">○ ◎</span><span class="reason">効果が見えやすい</span></td>
      <td><span class="result neutral">△</span><span class="reason">運用に注意</span></td>
      <td><span class="result bad">×</span><span class="reason">優先度が低い</span></td>
    </tr>
    <tr>
      <td>B</td>
      <td>観点3</td>
      <td><span class="result good">○ ◎</span><span class="reason">総合評価が高い</span></td>
      <td><span class="result neutral">△</span><span class="reason">代替案として検討</span></td>
      <td><span class="result bad">×</span><span class="reason">今回は不採用</span></td>
    </tr>
  </tbody>
</table>

---

# その他（引用、コード、脚注）

> 引用テキストはグレーベースのボックスで表示されます。
> 複数行にわたる引用も対応しています。

```python
def hello(name: str) -> str:
    return f"こんにちは、{name}！"

print(hello("えんぴつ"))
```

<p class="footnote">※ 出典、注釈、但し書きなど、本文より優先度の低い補足はスライド下部に小さく配置します。</p>

---

<!-- _class: section -->

# セクション見出し

このスライドはセクションの区切りに使用します

---

<!-- _class: title -->

# ご清聴ありがとうございました

