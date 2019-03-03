f &&& gが三角形を可換にすること。

```haskell
(&&&) :: (a -> b) -> (a -> c) -> a -> (b, c)
f &&& g = \x -> (f x, g x)
```

例えばCharと
以下の射があったときに

- ord     : Char -> Int
- isSpace : Char -> Bool

以下の等式を満たす。

1. ord      =  fst . (ord &&& isSpace)
2. isSpace  =  snd . (ord &&& isSpace)

1.の証明

```
fst (x, _) = x
これを簡約する。

fst . (ord &&& isSpace)
    -- . を簡約
    = \x -> fst $ (ord &&& isSpace) x
    -- &&& を簡約
    = \x -> fst $ (\y -> (ord y, isSpace y)) x
    -- xを適用
    = \x -> fst (ord x, isSpace x)
    -- fstを適用
    = \x -> ord x
    = ord
```

2.の証明

1.の証明と同様。
