# rsvgパッケージ（R）

rsvgパッケージでsvgをビットマップとして読み込むときに、悩んだ点があったのでメモ。


rsvg()で読み込む際は、svgのviewBoxの大きさによっては読み込めない。
viewBoxのwidth/heightが一定以下（viewBoxとは別のwidth/height属性が指定されていないとき）であると駄目なようだ。

解決策は、viewBoxとは別のwidth/height属性に100pxなどと具体的な値を設定してあげればよい。
