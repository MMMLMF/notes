### 一些查询的Python简单用法，记录一下

```python
list('你是谁') # 返回的结果是['你','是','谁']

Counter(all_data).most_common(vocab_size - 1)  # 保留最常见的前vocab_size - 1的data

```

shuffle与permutation的区别

函数shuffle与permutation都是对原来的数组进行重新洗牌（即随机打乱原来的元素顺序）；区别在于shuffle直接在原来的数组上进行操作，改变原来数组的顺序，无返回值。而permutation不直接在原来的数组上进行操作，而是返回一个新的打乱顺序的数组，并不改变原来的数组。
