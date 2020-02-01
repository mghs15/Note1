# Tippecanoe Tips

[Tippecanoe](https://github.com/mapbox/tippecanoe)の使い方に関するメモ。

* Tippecanoeのデフォルト設定を見ていると、元データの地物を正確に表示することよりも、タイルサイズを小さくし、快適に閲覧することを重視しているように感じられる。地物をそれなりに正確にタイル化することを考えると、各種オプションをつける必要がある。

## 基本のオプション
* `-o` 出力するmbtilesのファイル名
* `-e` 出力するXYZタイル（pbf）のディレクトリ名
* `-l` タイル内のsource-layer名の指定
* `-f` 既存のファイル・ディレクトリを上書き

## 地物のマージ
* `--coalesce`を利用すると、同じ属性値を持つ地物をマージできるようである。
* その際は、`--reorder`を使わないと、すべてをマージすることができない。
* ラインを間引きする場合、`--no-simplification-of-shared-nodes`を合わせて使いように推奨されている。[この説明](https://github.com/mapbox/tippecanoe#line-and-polygon-simplification)を見ると、どうやら線を共有しているポリゴン同士でマージされるようである。

## XYZのファイルシステムへの展開の注意
* mbtilesではなく、pbfファイルへ展開する（`-e`）場合、`--no-tile-compression`をつけるべきのようである。
* `--no-tile-compression`をつけない場合、レンダリング時に"Unimplemented type 3"というエラーが出て、ベクトルタイルが表示されない。
* `tile-join`を使い場合も同様。

## PointのSimplification
* ポイントデータのSimplificationでは、大幅に間引きされるので、`--drop-rate=1`を指定するべきである。
* デフォルトは`--drop-rate=2.5`（ZLにつき2.5分の1になる）。

## LineのSimplification
* ラインデータを間引きしない場合、`--no-line-simplification`を指定する。
* 間引きかつマージを行う（`--coalesce`）場合、`--no-simplification-of-shared-nodes`を使う。

## タイルサイズの制御
* とりあえず、タイルサイズが大きくなりそうなら、`--no-tile-size-limit`と`--no-feature-limit`をつけておくべきかもしれない。

