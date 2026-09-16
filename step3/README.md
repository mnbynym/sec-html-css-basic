# Step 3 — div によるグループ化と共通コンテナ

## このステップのゴール

CSS からレイアウトを組みやすいように、関連する要素を [`<div>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/div) でグループ化する。
HTML はこのステップで最終形になる（以降のステップでは CSS だけを変更する）。

## やること

### HTML（`<div>` の追加のみ）

1. **ヘッダー**: ロゴとナビを `<div class="container header-inner">` で囲む
2. **サブ・ヘッダー**: パンくずリストを `<div class="container sub-header-inner">` で囲む
3. **記事一覧**: 4 件の `<article>` 全体を `<div class="post-list">` で囲む
4. **記事カード**: 画像以外の本文（タイトル・著者情報・要約・Read more）を
   `<div class="post-body">` で囲む
5. **フッター**: リンク集までの全体を `<div class="container footer-inner">` で囲み、
   ブランド部分を `<div class="footer-brand">`、リンク集の各列を `<div class="footer-col">` で囲む

### クラス名の一覧（このステップで追加する分）

追加するのはすべて `<div>`。Step 2 で付けたクラスはそのまま変えない。
`container header-inner` のように半角スペース区切りで 2 つ書くと、1 つのタグに
複数のクラスを付けられる（`container` は共通の中央寄せ、もう片方がその場所固有の名前）。

| 場所 | クラス名 | 役割 |
| --- | --- | --- |
| ヘッダー | `container header-inner` | ロゴとナビをひとまとめにして中央寄せ |
| サブ・ヘッダー | `container sub-header-inner` | パンくずをひとまとめにして中央寄せ |
| 記事一覧 | `post-list` | カード 4 件を囲む（Step 5 でグリッドにする） |
| 記事カード | `post-body` | 画像以外の本文のまとまり（4 か所） |
| フッター | `container footer-inner` | フッターの中身全体をひとまとめにして中央寄せ |
| フッター | `footer-brand` | ロゴとキャッチコピーの列 |
| フッター | `footer-col` | リンク集の各列（3 か所） |

### CSS（追加した div に対応するスタイル）

1. `.container` … [`max-width`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/max-width)`: 1200px` + [`margin`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/margin)`: 0 auto` で、コンテンツの幅を制限して中央寄せする
   共通コンテナ（`<main class="container">` にはすでに付けてあった）
2. `.sub-header-inner` … パンくず帯の上下に少しの余白
3. `.post-body` … カード本文の内側余白

## ポイント

- **`<div>` の使いどころ**: CSSやJSを適用するための「グループ化専用」の要素。
  あらかじめ用意されている `header` や `article` のような適切なセマンティック要素がない場合のみ用いること
- **コンテナパターン**: `max-width` + `margin: 0 auto` の共通クラス `.container` を
  ヘッダー / サブ・ヘッダー / メイン / フッターで再利用できるようにする
- **スタイリングの下準備**: クラス名やグループ化を先に整えておくことで、
  以降のステップは CSS の変更だけで進められる

## 表示の確認

広い画面で、コンテンツの幅が 1200px までに制限されて中央に寄れば OK。
カードの本文まわりに余白がつく。記事一覧はまだ縦一列のまま。
