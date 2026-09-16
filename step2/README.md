# Step 2 — HTML コンテンツの完成と基本の CSS（レイアウトなし）

## このステップのゴール

HTML のコンテンツをこのステップでそろえ、CSS の土台（リセット CSS の導入・デザイントークン・基本設定）を作る
（`<div>` によるグループ化は Step 3 で行う）。
フォントと文字色・リンク色が変わり、リストの点が消える。

## やること

### HTML（コンテンツを完成させる）

1. [`<head>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/head) に Inter 公式配信（rsms.me）のウェブフォント、リセット CSS（destyle.css）、`style.css` の 3 つの読み込みを追加する
2. ヘッダーのテキストロゴ「MDN」を [SVG](https://developer.mozilla.org/ja/docs/Web/SVG) ロゴ（オリジナルをコピー&ペースト）に差し替える
3. ヘッダーの下に、パンくずリスト入りのサブ・ヘッダー（`<nav class="sub-header">`）を追加する
4. 記事カードを 3 件コピーして追加･編集し、合計 4 件にする
5. フッターにリンク集の 3 列（MDN / Contribute / Developers）を追加する
6. 後のステップで CSS から選択できるように、各タグへクラス名を付けておく（下の一覧どおりに付ければ OK）

### クラス名の一覧

このステップの CSS は要素セレクタしか使わないが、Step 3 以降でこれらのクラスを使って
スタイルを当てていく。命名で悩まないよう、次の表のとおりに付けること。

**ヘッダー**

| タグ | クラス名 | 役割 |
| --- | --- | --- |
| [`<header>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/header) | `site-header` | サイト全体のヘッダー |
| ロゴの [`<a>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/a) | `logo` | MDN ロゴのリンク |
| [`<nav>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/nav) | `global-nav` | メインメニュー |
| メニューの [`<ul>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/ul) | `nav-list` | メニュー項目のリスト |
| 「Blog」の `<a>` | `is-current` | 現在表示中のページを表す（状態クラス） |

**サブ・ヘッダー**

| タグ | クラス名 | 役割 |
| --- | --- | --- |
| `<nav>` | `sub-header` | パンくず入りの薄いグレーの帯 |
| [`<ol>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/ol) | `breadcrumb` | パンくずリスト |

**メイン**

| タグ | クラス名 | 役割 |
| --- | --- | --- |
| [`<main>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/main) | `container` | 中央寄せの共通コンテナ |
| [`<h1>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/Heading_Elements) | `page-title` | ページ見出し「Blog it better」 |

**記事カード（4 件とも同じ構成）**

| タグ | クラス名 | 役割 |
| --- | --- | --- |
| [`<article>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/article) | `post` | 記事カード 1 件分 |
| アイキャッチの [`<img>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/img) | `post-image` | 記事のアイキャッチ画像 |
| [`<h2>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/Heading_Elements) | `post-title` | 記事タイトル |
| 著者情報の [`<p>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/p) | `post-meta` | 著者・日付・読了時間のまとまり |
| 著者画像の `<img>` | `avatar` | 著者アイコン（円形にする予定） |
| 著者名の [`<span>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/span) | `author` | 著者名 |
| 読了時間の `<span>` | `readtime` | 読了時間 |
| 要約の `<p>` | `post-summary` | 記事の要約文 |
| Read more の `<a>` | `read-more` | ボタンの見た目にするリンク |

**フッター**

| タグ | クラス名 | 役割 |
| --- | --- | --- |
| [`<footer>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/footer) | `site-footer` | サイト全体のフッター |
| 「MDN」の `<p>` | `footer-logo` | フッターのロゴ文字 |
| キャッチコピーの `<p>` | `footer-tagline` | ロゴ下の一文 |
| 各列見出しの `<h2>` | `footer-heading` | リンク集の列タイトル（3 か所） |
| 各列の `<ul>` | `footer-list` | リンク集のリスト（3 か所） |
| 最後の `<p>` | `copyright` | 帰属表記 |

### CSS（`style.css` を新規作成）

1. **デザイントークン**: [`:root`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Selectors/:root) に[カスタムプロパティ](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/--*)で色とフォントを定義する
   （このステップで使う分だけ。残りは Step 3 で追加する）
2. **基本設定**（リセット自体は destyle.css に任せる）:
   - `body` … フォント（[`font-feature-settings`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/font-feature-settings)`: "ss02"` で本家と同じ判別用字形）、文字色、背景色
   - `img` … [`display`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/display)`: block` と [`max-width`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/max-width)`: 100%`（親からはみ出さない）
   - `a` … リンク色（destyle.css が消した色を付け直す）とホバー時の下線

## ポイント

- **クラス命名の考え方**: 見た目ではなく「場所・役割」で名付ける（`site-header` `post-title`）。状態を表すものには `is-` を付ける（`is-current`）
- **カスタムプロパティ（CSS 変数）**: 色やフォントを 1 か所にまとめて [`var()`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Values/var) で使い回す
- **Web フォントの読み込み**: [`preconnect`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Attributes/rel/preconnect) + [`<link rel="stylesheet">`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/link) の定番パターン
- **リセット CSS（destyle.css）**: ブラウザのデフォルト･スタイルは既存のリセットファイルにまとめて消してもらい、自分はデザインだけを書く

## 表示の確認

まだ縦一列で、リセットの効果により見出しの大きさや余白も消えてフラットな見た目になる。
フォントが Inter に変わり、リンクが青、リストの点が消えていれば OK。