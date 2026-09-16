# Step 4 — 応用の CSS（装飾・レイアウトなし）

## このステップのゴール

CSS で各パーツ（ヘッダー、カード、ボタン、フッター）を完成の見た目に仕上げる。
配置はまだ縦一列のままで、色・枠線・角丸・ホバーなどの「装飾」に集中する。

## やること

1. **デザイントークンの追加**: `:root` に残りの変数を追加する
   （2 番目の文字色・背景色、罫線、ボタン色、角丸）
2. **ヘッダー**:
   - `.site-header` に下罫線
   - `.nav-list a` を [`display`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/display)`: block` + [`padding`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/padding) で「ボックス状のリンク」にする
   - [`:hover`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Selectors/:hover) / [`:active`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Selectors/:active) で背景色を変え、`.is-current` で現在地を示す
3. **サブ・ヘッダー**: 薄いグレーの帯と、パンくずリンクの色
4. **ページ見出し**: `.page-title` のサイズ・太さ・中央揃え
5. **記事カード**:
   - `.post` に枠線（[`border`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/border)）・角丸・[`overflow`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/overflow)`: hidden`（角丸から画像がはみ出さないように）
   - タイトル・著者情報・要約の文字サイズ・太さ・色（リセットで消えた見出しの太字も付け直す）
   - `.avatar` を [`border-radius`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/border-radius)`: 50%` で円形にする
   - `.read-more` をボタンの見た目にする（背景色・角丸・[`transition`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/transition)）
     ※ここでは仮に `display: inline-block` にしておく（Step 5 で flex に置き換える）
6. **フッター**: 背景色・罫線・各パーツの文字スタイル

## ポイント

- **[擬似クラス](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Selectors/Pseudo-classes)**: `:hover` / `:active` でインタラクションを作る
- **リンクをボタンに見せる定番テクニック**: `padding` + 背景色 + `border-radius`
- **`transition`**: 背景色の変化をなめらかにする
- **`overflow: hidden`**: 角丸の内側に子要素を収める

## 表示の確認

縦一列のままだが、ナビのホバー、カードの枠、黒い Read more ボタン、
円形アバター、グレーのフッターなど、各パーツが完成の見た目になっていれば OK。
