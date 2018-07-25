### 一些查询的Python简单用法，记录一下

```python
list('你是谁') # 返回的结果是['你','是','谁']

Counter(all_data).most_common(vocab_size - 1)  # 保留最常见的前vocab_size - 1的data

```

#### shuffle与permutation的区别

函数shuffle与permutation都是对原来的数组进行重新洗牌（即随机打乱原来的元素顺序）；区别在于shuffle直接在原来的数组上进行操作，改变原来数组的顺序，无返回值。而permutation不直接在原来的数组上进行操作，而是返回一个新的打乱顺序的数组，并不改变原来的数组。

#### tf.placeholder(dtype, shape=None, name=None)

此函数可以理解为形参，用于定义过程，在执行的时候再赋具体的值。dtype：数据类型。常用的是tf.float32,tf.float64等数值类型；shape：数据形状。默认是None，就是一维值，也可以是多维，比如[2,3], [None, 3]表示列是3，行不定；name：名称。

#### tf.variable_scope和tf.name_scope
tf.variable_scope可以让变量有相同的命名，包括tf.get_variable得到的变量，还有tf.Variable的变量

tf.name_scope可以让变量有相同的命名，只是限于tf.Variable的变量

```python

import tensorflow as tf
 
with tf.variable_scope("foo"):
    a = tf.get_variable("bar", [1])
    print(a.name)                    #foo/bar:0
    b = tf.Variable("b", [1])
    print(b.name)                   #foo/Variable:0
 
with tf.variable_scope("bar"):
    a = tf.get_variable("bar", [1])
    print(a.name)                     #bar/bar:0
    b = tf.Variable("b", [1])
    print(b.name)                   #bar/Variable:0
 
with tf.name_scope("a"):
    a = tf.Variable([1])
    print(a.name)                      #a/Variable:0
 
with tf.name_scope("b"):
    b = tf.get_variable("b", [1])
    print(b.name)                #b_1:0
 
with tf.name_scope("b"):
    c = tf.get_variable("b", [1])

```
