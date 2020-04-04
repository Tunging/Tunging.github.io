---
layout: post
title: python base
categories: [python]
description: notes when learn python base knowledge
keywords: python
---

# python base 

## Truthy and falsy values
```
The following values are evaluated to False in Python:

constants defined to be false: None and False,
zero of any numeric type: 0, 0.0,
empty sequences and containers: "", [], {}.
```


### or & and 的用法
```python
truthy_integer = False or 5 and 100  # 100
```
结果为什么是100呢？and有限级比or高，所以执行的顺序是 ```5 and 100``` ,返回的是 ```100```，然后是```False or 100 ```,所以结果是 ```100```

### 懒惰执行规则
```python
# division is never evaluated, because the first argument is True
lazy_or = True or (1 / 0)  # True
 
# division is never evaluated, because the first argument is False
lazy_and = False and (1 / 0)  # False
```
总结一下大概是
```and```时，返回第一个非True,如果都是True,返回最后遇到的True值   ```Flase and 1``` = False, ```True and 2``` = 2, ```2 and False``` = False, ```2 and 3``` = 3
```or```时，返回第一个非Flase，如果都是Flase，返回最后一个Flase值  ```False or None``` = None ，都是false，返回最后一个False值，也就是None

## 