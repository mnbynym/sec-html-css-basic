# Step 6 — レスポンシブ対応

## このステップのゴール

[メディアクエリ](https://developer.mozilla.org/ja/docs/Web/CSS/Guides/Media_queries/Using)を追加して、画面幅に応じてカラム数が変わるようにする。
これでチュートリアルは完成（「完成」フォルダと同じ内容になる）。

## やること

CSS の末尾に「レスポンシブ対応」セクションを追加する。

1. **タブレット以上（[`@media`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/At-rules/@media) の `min-width: 768px`）**:
   - `.page-title` を少し大きくする
   - `.post-list` を 2 列にする
   - `.footer-inner` を 2 列にする
2. **デスクトップ以上（`min-width: 1024px`）**:
   - `.post-list` を 3 列にする
   - `.footer-inner` を `2fr 1fr 1fr 1fr` の 4 列にする

## ポイント

- **モバイルファースト**: ベース（メディアクエリの外）をモバイル用の 1 カラムで書き、
  `min-width` のメディアクエリで広い画面向けの上書きを重ねていく
- **ブレイクポイント**: 768px / 1024px という代表的な境界の考え方
- **Grid とレスポンシブの相性**: [`grid-template-columns`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/grid-template-columns) を 1 行書き換えるだけで
  カラム数が変わる（HTML には一切手を入れない）
- **[`fr` 単位](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Values/flex_value)**: `2fr 1fr 1fr 1fr` のような比率指定
- **差分の目印**: `style.css` 内の「★ Step 6」コメントが、このステップで追加した箇所

## 表示の確認

ブラウザの幅を変えながら（または開発者ツールのデバイスモードで）、
1 列 → 2 列 → 3 列とレイアウトが切り替われば完成。
767px / 768px、1023px / 1024px の境界で切り替わることも確認してみよう。
