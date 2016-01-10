# Casper-ja

A fork of [TryGhost/Casper](http://github.com/tryghost/casper), the default theme for [Ghost](http://github.com/tryghost/ghost/) blogging engine. This solves the issues heppen with Japanese contents, and, adds some minor adjustments for readability.

Note that we decided to use *gothic* (sans-serif) rather than *mincho* (serif) due to limited number of clients which have beautiful serif fonts, while you can use `mincho` branch to use mincho up to your preference.

ブログエンジンGhostの[Ghost](http://github.com/tryghost/ghost/)デフォルトテーマであるCasperを日本語対応させたフォークです。日本語のコンテンツを扱う際に発生する問題を修正し、また読みやすさの面で日本語に合わせて若干の修正を行っています。

綺麗な日本語の明朝体を表示できる環境がまだ完全に普及しきっていないことを考慮して、オリジナルでは本文はセリフ体であるところを、記事本文はゴシック体に変更しています。明朝体を利用したい場合、`mincho`ブランチを利用することができます。

## 方針

1. できるかぎりオリジナルの雰囲気を尊重する

2. 多くの環境で、高品質なフォントで表示されるようにする

3. Webフォントは新たに追加しない

## 修正した問題

1. 見出しにおいて、任意の合字（discretionary ligatures）が有効化されているため、意図しない組文字化が行われてしまうこと（[https://github.com/TryGhost/Casper/pull/227](https://github.com/TryGhost/Casper/pull/227)）

## 日本語に合わせた調整

1. 日本語フォントを指定しました
   優先順位: 游ゴシック→ヒラギノ角ゴ→メイリオ
   （`mincho`は: 游明朝→ヒラギノ明朝→S明朝E）
   
   ただし見出しはメイリオ→ヒラギノ角ゴ→游ゴシックです。これは元々指定されているOpen Sans Boldとの調和を考慮した結果です。

2. 斜体をほとんどの部分で利用しないようにしました

3. 字間を調整しました

## その他の変更

1. `pre`や`code`などに指定されているInconsolataはOSにデフォルトで入っているフォントではないのでConsolasとMonacoにフォールバックするようにしました（Webフォントを読み込んでいないのはバグ？）

## 好みが分かれそうなところ

記事本文の欧文には、日本語フォントの従属欧文を利用せず、Open Sans（ゴシック体版）あるいはMerriweather（明朝体版）にしました。これは日本語で使ったフォントとの調和も悪くないように感じたので、方針1に沿ったという理由からです。従属欧文を利用したい場合は、`assets/css/screen.css`内を`Merriweather`または`Open Sans`で検索し、日本語フォントと同時に指定されている部分について、当該欧文フォント名を削除してください。

例:

変更前
```
body {
    ...
    font-family: "Open Sans", "游ゴシック体", "Yu Gothic", YuGothic, "ヒラギノ角ゴ Pro", "Hiragino Kaku Gothic Pro", "メイリオ", "Meiryo", sans-serif;
    ...
}
```

変更後
```
body {
    ...
    font-family: "游ゴシック体", "Yu Gothic", YuGothic, "ヒラギノ角ゴ Pro", "Hiragino Kaku Gothic Pro", "メイリオ", "Meiryo", sans-serif;
    ...
}
```

## Copyright & License (for the modifications)

Copyright (c) 2016 @mecab - Released under the MIT License.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

----

Original readme follows:

----

# Casper

The default theme for [Ghost](http://github.com/tryghost/ghost/).

To download, visit the [releases](https://github.com/TryGhost/Casper/releases) page.

## Copyright & License

Copyright (c) 2013-2016 Ghost Foundation - Released under the MIT License.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
