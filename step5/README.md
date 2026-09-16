# Step 5 — レイアウトの CSS（レスポンシブなし）

## このステップのゴール

Flexbox と Grid で要素を配置し、ページ全体のレイアウトを完成させる。
まずはモバイル想定の 1 カラムがベース（複数カラム化は Step 6）。

## やること

1. **ヘッダー**: `.header-inner` を [`display`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/display)`: flex` にしてロゴとナビを横並びにする
   - `.logo` にも `display: flex`（SVG の下にできる余分なすき間をなくす）
   - `.nav-list` を `display: flex` にしてメニューを横並びにする
2. **パンくず**: `.breadcrumb` を `display: flex` + [`gap`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/gap) にする
3. **記事カード**:
   - `.post` を [`flex-direction`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/flex-direction)`: column` の縦積み flex にする
   - `.post-image` を [`width`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/width)`: 100%` + [`aspect-ratio`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/aspect-ratio)`: 2 / 1` + [`object-fit`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/object-fit)`: cover` で統一サイズにする
   - `.post-body` を flex（縦）+ [`flex-grow`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/flex-grow)`: 1` にする
   - `.post-meta` を flex にしてアバター・著者・日付を横一列に揃える
   - `.read-more` の `display: inline-block` を削除し、
     [`align-self`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/align-self)`: flex-end` + [`margin-top`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/margin-top)`: auto` に置き換える（常にカードの右下に配置）
4. **記事一覧**: `.post-list` を `display: grid`（1 列 + `gap`）にする
5. **フッター**: `.footer-inner` と `.footer-list` を grid にし、`.copyright` を中央寄せにする

## ポイント

- **[Flexbox](https://developer.mozilla.org/ja/docs/Web/CSS/Guides/Flexible_box_layout/Basic_concepts)**: 横並び（ヘッダー・著者情報）と縦積み（カード内部）の使い分け
- **`margin-top: auto`**: flex 内で要素を末尾（カード下端）に押しやるテクニック
- **`aspect-ratio` + `object-fit: cover`**: 画像を切り抜いてサイズを統一する
- **[Grid](https://developer.mozilla.org/ja/docs/Web/CSS/Guides/Grid_layout/Basic_concepts)**: [`grid-template-columns`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/grid-template-columns) と `gap` による一覧の整列

## 表示の確認

ヘッダーが横並びになり、コンテンツが中央寄せ、カードが整った 1 カラムで並べば OK。
どのカードでも Read more ボタンが右下に揃っていることを確認する。
