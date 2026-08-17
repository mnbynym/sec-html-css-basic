# Step 4 — レイアウトの CSS（レスポンシブなし）

## このステップのゴール

Flexbox と Grid で要素を配置し、ページ全体のレイアウトを完成させる。
まずはモバイル想定の 1 カラムがベース（複数カラム化は Step 5）。

## やること

1. **共通コンテナ**: `.container` を追加する（`max-width: 1200px` + `margin: 0 auto` で中央寄せ）
2. **ヘッダー**: `.header-inner` を `display: flex` にしてロゴとナビを横並びにする
   - `.logo` にも `display: flex`（SVG の下にできる余分なすき間をなくす）
   - `.nav-list` を `display: flex` にしてメニューを横並びにする
3. **パンくず**: `.breadcrumb` を `display: flex` + `gap` にする
4. **記事カード**:
   - `.post` を `flex-direction: column` の縦積み flex にする
   - `.post-image` を `width: 100%` + `aspect-ratio: 2 / 1` + `object-fit: cover` で統一サイズにする
   - `.post-body` を flex（縦）+ `flex-grow: 1` にする
   - `.post-meta` を flex にしてアバター・著者・日付を横一列に揃える
   - `.read-more` の `display: inline-block` を削除し、
     `align-self: flex-end` + `margin-top: auto` に置き換える（常にカードの右下に配置）
5. **記事一覧**: `.post-list` を `display: grid`（1 列 + `gap`）にする
6. **フッター**: `.footer-inner` と `.footer-list` を grid にし、`.copyright` を中央寄せにする

## 学ぶポイント

- **コンテナパターン**: `max-width` + `margin: 0 auto` によるコンテンツ幅の管理
- **Flexbox**: 横並び（ヘッダー・著者情報）と縦積み（カード内部）の使い分け
- **`margin-top: auto`**: flex 内で要素を末尾（カード下端）に押しやるテクニック
- **`aspect-ratio` + `object-fit: cover`**: 画像を切り抜いてサイズを統一する
- **Grid**: `grid-template-columns` と `gap` による一覧の整列

## 表示の確認

ヘッダーが横並びになり、コンテンツが中央寄せ、カードが整った 1 カラムで並べば OK。
どのカードでも Read more ボタンが右下に揃っていることを確認する。
