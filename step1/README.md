# Step 1 — HTML の基本コンテンツ（CSS なし）

## このステップのゴール

CSS を使わずに、ページの「骨組み」となる HTML を書く。
ブラウザのデフォルトの見た目のままで OK。

## やること

1. HTML の基本構造（[`<!DOCTYPE html>`](https://developer.mozilla.org/ja/docs/Glossary/Doctype)、[`<html lang="ja">`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/html)、[`<head>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/head)、[`<body>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/body)）を書く
2. ページを 3 つの大きなブロックで組み立てる
   - [`<header>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/header) … テキストのロゴ「MDN」と、[`<nav>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/nav) + [`<ul>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/ul) によるメニュー（9 項目）
   - [`<main>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/main) … [`<h1>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/Heading_Elements) の見出しと、記事カード 1 件
   - [`<footer>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/footer) … ブランド名とキャッチコピー
3. 記事カード 1 件を [`<article>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/article) で作る
   - [`<img>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/img) でサムネイル画像（オリジナルの画像リンクをコピー&ペースト）
      - [`alt`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/img#alt) 属性の記述
   - [`<h2>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/Heading_Elements) に記事タイトル
   - 著者情報の行（アバター画像・著者名・[`<time>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/time) による日付・読了時間）
   - 要約文と「Read more」リンク

## ポイント

- **[セマンティック HTML](https://developer.mozilla.org/ja/docs/Glossary/Semantics)**: `header` / `nav` / `main` / `article` / `footer` を役割どおりに使う
- **画像のアクセシビリティ**: 意味のある画像には `alt` で説明を、装飾的な画像には `alt=""` を付ける


## 表示の確認

`index.html` をブラウザで開く。スタイルなしの縦一列の表示になるが、見出し・リスト・画像・リンクが正しい構造で並んでいれば OK。
