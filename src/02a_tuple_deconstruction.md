# Tuple Deconstruction

```volpe
[a, b] = [-4, 2]
# a = -4
# b = 2
```

```volpe
x = [0, [1, 2], [3, [4, 5]]]

[a, b, c] = x
# a = 0
# b = [1, 2]
# c = [3, [4, 5]]

[a, [b, c], [d, e]] = x
# a = 0
# b = 1
# c = 2
# d = 3
# e = [4, 5]
```
