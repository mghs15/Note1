# OOXML に関するメモ

## pptx のハイライトを削除
メモ帳の置換機能などで、以下のタグを削除すればよい（マーカーの色 `FFFF00` は適宜変更）。
テキストボックスの他、楕円や吹出等の図形も確認したが、設定内容は同じだった。

```
<a:highlight><a:srgbClr val="FFFF00"/></a:highlight>
```

ちなみに、Wordだと以下のようなタグで指定されている。
```
<w:highlight w:val="yellow"/></w:rPr>
```








