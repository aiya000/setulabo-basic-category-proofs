# 圏Haskの任意の射`f`, `g`と関数合成演算子`.`が恒等律を満たすこと

```
    f :: A -> X
    g :: X -> A
と
  idX :: X -> X
  idX = id
    where
      -- Haskellのid
      id :: a -> a
      id x = x
は

idX . f
    .を展開
  = \x -> idX (f x)
    idXを展開
  = \x -> f x
    余分なラムダ式を除去
  = f

同様に

g . idX
  = \x -> g (id X)
  = \x -> g x
  = g
```
