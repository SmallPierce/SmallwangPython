|      |      |      |      |
| ---- | ---- | ---- | ---- |
|      |      |      |      |
|      |      |      |      |
|      |      |      |      |

python数据类型
-----

[TOC]

### 二 字符串数据类型

> **字符串声明**

python3中字符串声明方法有：单引号、双引号、三个单引号、三个双引号

注意的是：

+ python中的字符串是一个高级工具，是不可变的序列
+ python中没有char类型，一个字符也是字符串
+ python中双引号和单引号括起来的内容，单双引号不可以混用，如果在字符串中本身有包含字符串，可以使用转义字符
+ python中字符串单引号和双引号括起来是一样的，不同的是，如果单引号括起来的字符串中包含单引号的话，我们需要使用转义字符

> **字符串编码**

在python3中，字符串分别为str、和unicode两种数据类型，str类型采用的是ASCII编码，unicode类型采用的unicode编码。所以如果想使用中文、日文或者其他的语言问题，就必须的使用unicode编码来实现。

所以在python3中要显示的明文字符串是unicode编码，就必须在前面加上一个`u`或者换`U`，如下

```python
>>> str = u"中国"
>>> str
'中国'
```

在于其他平台或者其他语言交互的时候，编码显得尤为重要，优势编码格式对应不上，就会显示出乱码，调试起来也非常不方便。所以我们可以在python头文件中声明编码的格式，声明如下
`#_*_coding:utf-8_*_`

**对于读写文本文件，遵循的方式是：用那种编码格式读，就用那种编码格式写，反之亦然**

> **字符串格式化**

在python中有两种格式化的方法：

+ 占位符

```pythoin
>>> str =u'中国%s,happy birthday for %d years old'%("china",70)
>>> print(str)
中国china,happy birthday for 70 years old
```

下面列出了占位符的各种用法：

| 占位符 | 用途                                      | 占位符 | 用法                                   |
| ------ | ----------------------------------------- | ------ | -------------------------------------- |
| `%%`   | %百分号标记                               | `%c`   | 格式化字符及其ascii码                  |
| `%d`   | 格式化整数                                | `%u`   | 格式化无符号整型                       |
| `%o`   | 格式化无符号八进制数                      | `%x`   | 格式化无符号十六进制                   |
| `%X`   | 格式化无符号十六进制数大写                | `%f`   | 格式化浮点数字                         |
| `%e`   | 使用科学计数法格式化浮点数                | `%p`   | 用十六进制数格式化变量的地址           |
| *      | 定义宽度或者小数精度                      | -      | 用作左对齐                             |
| +      | 在正数前面显示加号                        | #      | 在八进制前面显示0，在十六进制前面显示x |
| m.n    | m显示的是最小宽度<br /> n是小数点后面位数 |        |                                        |

+ format

```python
>>> str =u'中国{},happy birthday for {} years old'.format("china",70)
>>> print(str)
中国china,happy birthday for 70 years old
'中国china,happy birthday for 70 years old'
>>> str =u'中国{name},happy birthday for {age} years old'.format(age=70, name = 'China')
>>> str
'中国China,happy birthday for 70 years old'
```

