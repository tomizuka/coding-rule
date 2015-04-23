# HTML/CSS Style Guide

[Google HTML/CSS Style Guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml)を基準にしている。

## 全般
### プロトコル

埋め込みリソースから(http,https)を省略する。

```html
# 非推奨
<script src="http://www.google.com/js/gweb/analytics/autotrack.js"></script>

# 推奨
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```

```css
# 非推奨
.example {
  background: url(http://www.google.com/images/example);
}

# 推奨
.example {
  background: url(//www.google.com/images/example);
}
```

## フォーマット
### インデント

**インデントは半角スペース2文字**とする。タブや半角スペースを混合して使用しない。

```html
# 非推奨
<ul>
    <li>Fantastic
    <li>Great
</ul>

# 推奨
<ul>
  <li>Fantastic
  <li>Great
</ul>
```

```css
# 非推奨
.example {
    color: blue;
}

# 推奨
.example {
  color: blue;
}
```

### 小文字の使用

HTMLの各要素、属性、属性値、CSSのセレクタ、プロパティ名、プロパティ値の記述には小文字を使用する。

```html
# 非推奨
<A HREF="/">Home</A>

# 推奨
<img src="google.png" alt="Google">
```

### 末尾の空白

末尾の空白は削除する。

```html
# 非推奨
<p>What?</p>_

# 推奨
<p>Yes please.</p>
```

## メタ

### エンコード設定

ソースコードのエンコードは**UTF-8(BOMなし)**を使用する。

### 注釈

保守管理しやすいように、必要に応じてコードの機能をコメントしておく。

### アクションアイテム

コードにTODOをコメントとして記述する。

```html
{# TODO: revisit centering #}
<center>Test</center>
```

```html
<!-- TODO: remove optional tags -->
<ul>
  <li>Apples</li>
  <li>Oranges</li>
</ul>
```

## HTML

### ドキュメントの種類

HTML5を使用する。

### HTMLバリデート

[W3C HTML validator](http://validator.w3.org/nu/)のようなツールでテストする。

### 意味のあるHTMLマークアップ

目的や機能に応じたHTMLを使用する。

```html
# 非推奨
<div onclick="goToRecommendations();">All recommendations</div>


# 推奨
<a href="recommendations/">All recommendations</a>
```

### マルチメディアコンテンツ

マルチメディアの代替コンテンツの提供としてalt属性を利用する。

```html
# 非推奨
<img src="spreadsheet.png">

# 推奨
<img src="spreadsheet.png" alt="Spreadsheet screenshot.">
```

### 各構造の分離

マークアップ、スタイリング、スクリプトの各構造ごとに分割して記述する。

```html
# 非推奨
<!DOCTYPE html>
<title>HTML sucks</title>
<link rel="stylesheet" href="base.css" media="screen">
<link rel="stylesheet" href="grid.css" media="screen">
<link rel="stylesheet" href="print.css" media="print">
<h1 style="font-size: 1em;">HTML sucks</h1>
<p>I've read about this on a few sites but now I'm sure:
  <u>HTML is stupid!!1</u>
<center>I can't believe there's no way to control the styling of
  my website without doing everything all over again!</center>

# 推奨
<!DOCTYPE html>
<title>My first CSS-only redesign</title>
<link rel="stylesheet" href="default.css">
<h1>My first CSS-only redesign</h1>
<p>I've read about this on a few sites but today I'm actually
  doing it: separating concerns and avoiding anything in the HTML of
  my website that is presentational.</p>
<p>It's awesome!</p>
```
### 実体参照の禁止

HTMLでの特殊な記号を除き、実体参照の禁止。

```html
# 非推奨
The currency symbol for the Euro is ＆ldquo;＆eur;＆rdquo;.

# 推奨
The currency symbol for the Euro is "€".
```

### スタイルシートとスクリプトの属性の省略

HTML5では、デフォルトの言語として扱われるため、スタイルシートとスクリプトの属性は省略して記述する。

```html
# 非推奨
<link rel="stylesheet" href="//www.google.com/css/maia.css" type="text/css">

# 推奨
<link rel="stylesheet" href="//www.google.com/css/maia.css">
```

```html
# 非推奨
<script src="//www.google.com/js/gweb/analytics/autotrack.js" type="text/javascript"></script>

# 推奨
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```

## HTMLの書式

### 一般的な書式

**ブロック、リスト、テーブル要素は改行**し、**子要素にはインデントを挿入**する。

```html
<blockquote>
  <p><em>Space</em>, the final frontier.</p>
</blockquote>
<ul>
  <li>Moe
  <li>Larry
  <li>Curly
</ul>
<table>
  <thead>
    <tr>
      <th scope="col">Income</th>
      <th scope="col">Taxes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>$ 5.00</td>
      <td>$ 4.50</td>
    </tr>
  </tbody>
</table>
```

### HTMLでの引用符
引用符は単一引用符ではなく**二重引用符を使用**する。
```html
# 非推奨
<a class='maia-button maia-button-secondary'>Sign in</a>

# 推奨
<a class="maia-button maia-button-secondary">Sign in</a>
```


## CSS

### CSSバリデート

規定された文法に則り、要求された使用に対して適切なCSSを記述する。
[CSS Validation Service](http://jigsaw.w3.org/css-validator/validator.html.ja)のようなツールでテストする。

### ID属性

ID属性にCSSを適用しない。

### タイプセレクタ

```css
# 非推奨
div.error {}

# 推奨
.error {}
```

### プロパティ指定の簡略化

プロパティは細かく指定せず、一括で指定する。

```CSS
# 非推奨
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;

# 推奨
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```

### プロパティ指定の簡略化

プロパティは細かく指定せず、一括で指定する。

```css
# 非推奨
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;

# 推奨
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```

### 0と単位

値が0の場合、単位は省略する。

```css
margin: 0;
padding: 0;
```

### 小数点がある場合

1以下の数値を設定する場合には、0を省略し、小数点以下の値を入力する。

```css
font-size: .8em;
```

### 16進数の数値の設定

可能な限り、3桁での16進数による値を設定する。

```css
# 非推奨
color: #eebbcc;

# 推奨
color: #ebc;
```

### ハック

ユーザーエージェント対応のためにCSSハックを利用する前にほかの手段を試し、CSSハックは極力避けること。

## CSSフォーマット

### ブロックコンテンツのインデント

ブロックの内容は全てインデントし、階層を視認しやすくする。

```css
@media screen, projection {

  html {
    background: #fff;
    color: #444;
  }
}
```

### 宣言の終了

行末には必ずセミコロンを付ける。

```css
# 非推奨
.test {
  display: block;
  height: 100px
}

# 推奨
.test {
  display: block;
  height: 100px;
}
```

### プロパティ名の終端

プロパティ名のコロンの後にスペースを挿入する。

```css
# 非推奨
h3 {
  font-weight:bold;
}

# 推奨
h3 {
  font-weight: bold;
}
```

### 宣言とブロックの分離

最後のセレクタと宣言ブロックの間にスペースを挿入し、中括弧はセレクタと同じ行に記述する。

```css
# 非推奨(スペースがない)
.video{
  margin-top: 1em;
}

# 非推奨(改行されている)
.video
{
  margin-top: 1em;
}

# 推奨
.video {
  margin-top: 1em;
}
```

### セレクタと宣言の分離

各セレクタと宣言は改行して分離する。

```css
# 非推
a:focus, a:active {
  position: relative; top: 1px;
}

推奨
h1,
h2,
h3 {
  font-weight: normal;
  line-height: 1.2;
}
```

### 宣言ごとの行間

宣言ごとに一行の行間を空ける。

```css
html {
  background: #fff;
}

body {
  margin: auto;
  width: 50%;
}
```
### CSSの引用符

URLの指定には引用符を使用しない。
セレクタとプロパティの値には二重引用符ではなく単一引用符を使用する。

```css
# 非推奨
@import url("//www.google.com/css/maia.css");

html {
  font-family: "open sans", arial, sans-serif;
}

# 推奨
@import url(//www.google.com/css/maia.css);

html {
  font-family: 'open sans', arial, sans-serif;
}
```

### CSSのネスト
ネストは孫まとする。

```
親 > 子 > 孫
```

### 宣言順

[cssComb](http://csscomb.com/)を導入する。

原則、下記の順番で記述する。
***
- 表示に関するプロパティ
    - display
    - list-style
        - list-style-type
        - list-style-image
        - list-style-position
    - overflow
    - clip
    - visibility
    - opacity

  - 内容の追加に関するプロパティ
    - content
    - quotes
    - counter-reset
    - counter-increment　

- 配置に関するプロパティ
    - position
    - top
    - right
    - bottom
    - left
    - float
    - clear
    - z-index
    - transform

- ボックスモデルに関するプロパティ
    - width
    - height
    - margin
    - padding
    - border
        - border-width
        - border-color
        - border-style
    - border-radius
    - border-image
    - box-sizing
    - box-shadow

- 背景に関するプロパティ
    - background
        - background-color
        - background-image
        - background-repeat
        - background-attachment
        - background-position
    - background-clip
    - background-origin
    - background-size

- テキストに関するプロパティ
    - color
    - font
        - font-family
        - font-style
        - font-variant
        - font-weight
        - font-size
        - line-height
    - text-decoration
    - text-align
    - vertical-align
    - letter-spacing
    - word-spacing
    - text-transform
    - white-space
    - text-shadow

- ユーザーインターフェースに関するプロパティ
    - cursor
    - resize

- アニメーションに関するプロパティ
    - transition
        - transition-property
        - transition-duration
        - transition-timing-function
        - transition-delay
    - animation
        - animation-name
        - animation-duration
        - animation-timing-function
        - animation-iteration-count
        - animation-direction
        - animation-play-state
        - animation-delay
        - animation-fill-mode
***

## CSSのメタ規則

セクションごとに適宜コメントを挿入する。

```css
/* Header */

.header {}

/* Footer */

.footer {}

/* Gallery */

.gallery {}
```

## class名の命名規則(要検討事項)

[BEM記法](https://gist.github.com/juno/6182957)に基づく。

参考サイト
- [MindBEMding – getting your head ’round BEM syntax](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
- [BEMという命名規則とSass 3.3の新しい記法](http://blog.ruedap.com/2013/10/29/block-element-modifier)

## css プリプロセッサ

SCSSを使用する。
