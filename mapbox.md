# Mapbox忘備録
Mapbox用の忘備録です。
さまざまな作業を雑然と置いておきます。

## Mapbox StudioのStyle編集画面の機能を試す

Mapbox Studio
https://studio.mapbox.com/styles/

### Component機能
スタイルレイヤごとの編集だけでなく、グループとして編集することができるらしい。
以下のQiitaの紹介記事を見る限り、Mapbox Style Specのmetadata属性（描画には直接関係しない属性）を活用しているようだ。

https://qiita.com/moritoru/items/78aeb5491a4b2627fa9d

ただ、Mapbox社API以外のデータソースについてはうまく読み込むことができなかった。
（自分が何か失敗しているのか、そういう仕様なのかは不明。）

外部ソースが読み込めれば、優秀なスタイルエディタとして利用できる気がするが、さすがにそこまで許してくれないか？
メタデータ内に記述された、Componennt（グループ化）を規定するスキーマのライセンスも気になるところ。

### Setting

- 衛星写真の表示
- ラスタタイル（OSM）の表示
- タイルグリッドの表示
- 文字の衝突範囲の表示
- インスペクターモードの重ね合わせ

衛星写真・ラスタタイル（OSM）は、地物の位置正確度の比較に利用できそう。
（衛星写真を利用して位置比較をする場合、著作権がどのような扱いになるか不明。）

タイルグリッドは、問題あるデータの検証に利用できる。

→QGIS 3.4では、レイヤ追加>ベクタ>pbfを選択すれば、データを読み込める。
プラグインを利用できれば、metaデータのあるデータセット（mbtilesやXYZのセット）を利用できるみたい。

文字の衝突範囲、インスペクタモードは、細かい地図調整に利用できそう。

Mapbox GL JSでは、注記・アイコンの衝突回避を自動で行っている。衝突範囲は指定できるので、このモードを見ながら微調整することになるだろう。



### Images

SVGファイル（.svg）をアップロードできるらしい。

SVGファイルは"Maki Icon editor"で編集できる。

https://labs.mapbox.com/maki-icons/editor/

このMaki Icon editorでSVGファイルを編集・出力し、AVGファイルをMapbox Studioにアップロードすればよい。
修正できる項目は、色、縁取り、背景色のみ。他に、名前やグループ名などの設定変更も可。
ちなみに、Mapbox Studioに登録できるSVGは、500までらしい。



### Share

Share > download から、style.jsonをダウンロードできる。


## Mapbox Studio上でのデータ編集

以下で可能。インポートしたデータの編集以外にも、イチから作ることもできる。

https://studio.mapbox.com/datasets/

背景に、OSMのほか、航空写真も選べる。（たぶん、自分で作ったスタイルも設定可能。）

トレースした場合の著作権はどうなるのだろうか？

## Mapbox GL JSの面白そうな機能
* 注記・記号の衝突範囲とその挙動の確認ができる。<br>
https://docs.mapbox.com/mapbox-gl-js/api/#map#showcollisionboxes
* メルカトル図法のスケールファクターを設定できる。<br>
https://docs.mapbox.com/mapbox-gl-js/api/#mercatorscale

<hr>

今後気づいた点を追加予定



