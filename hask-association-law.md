圏Haskの任意の射`f`, `g`と関数合成演算子`.`がを満たすことの証明。

```
(.) :: (b -> c) -> (a -> b) -> (a -> c)
f . g = \x -> f (g x)

((0 <=) . fromIntegral) . ord
    括弧の中を展開
  = (\x -> 0 <= (fromIntegral x)) . ord
    余分な括弧を除去
  = (\x -> 0 <= fromIntegral x) . ord
    (. ord)を展開
  = \y -> (\x -> 0 <= fromIntegral x) (ord y)
    xに(ord y)を関数適用
  = \y -> 0 <= fromIntegral (ord y)

(0 <=) . (fromIntegral . ord)
    括弧の中を展開
  = (0 <=) . (\x -> fromIntegral (ord x))
    ((0 <=) .)を展開
  = \y -> (0 <=) ((\x -> fromIntegral (ord x)) y)
    xにyを関数適用
  = \y -> (0 <=) (fromIntegral (ord y))
    余分な括弧を除去
  = \y -> 0 <= fromIntegral (ord y)

なので

((0 <=) . fromIntegral) . ord
  = (0 <=) . (fromIntegral . ord)
```
