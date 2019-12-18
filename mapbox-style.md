# Mapbox Styleに関するあれこれ

[Mapbox Style Specification](https://docs.mapbox.com/mapbox-gl-js/style-spec/)に準拠して、地図デザインを行う際のTips、躓いた点、やりたいことなどのメモ

## 縦書き
text-writing-modeを利用すると、縦書きに対応できる。
* text-letter-spacingは縦書きにも効く。
* 長符「ー」が横書きのまま表示される。これは、mapbox-gl.js内の横書き用文字→縦書き用文字の変換リストにないため。試しに、`"ー":"｜",` を追加してテストしてみたらうまくいった。
* データドリブンな表現はできないので、データの属性値に応じて、縦横の指定を行うのはできない。その代わり、縦書きか横書きかの優先度を指定する。
* text-variable-anchor等と合わせて、なるべく多くの注記を表示するという運用を想定しているのかもしれない。


