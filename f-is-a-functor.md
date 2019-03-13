# 関手`F : Sets -> Tord`が関手の定義を満たすこと。

```
Setsの任意の対象について、恒等射は明らかに保存されている。

F(st) = ≦00
F(ts) = ≦00
F(sc) = ≦02
F(tc) = ≦02

F(st ○ ts)
    = F(id_△▲∴)
    = ≦00
    = ≦00  ○ ≦00
    = F(st) ○ F(ts)

F(sc ○ ts)
    = F(tc)
    = ≦02
    = ≦02  ○ ≦00
    = F(sc) ○ F(ts)

F(tc ○ st)
    = F(sc)
    = ≦02
    = ≦02  ○ ≦00
    = F(tc) ○ F(st)
```
