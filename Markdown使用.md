# Markdown使用

```markdown
---
```

**显示效果**

---

#### 标题

```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

**显示效果**

# 一级标题

## 二级标题

### 三级标题

#### 四级标题

##### 五级标题

###### 六级标题

---

#### 字体

```markdown
*斜体文本*
_斜体文本_
**粗体文本**
__粗体文本__
***粗斜体文本***
___粗斜体文本___
~~删除线效果~~
<u>下划线文本</u>
创建脚注 [^脚注]
[^脚注]：我是脚注！！！
==高亮==
H~2~O 下标
X^2^ 上标
```

**显示效果**

*斜体文本*

_斜体文本_

**粗体文本**

***粗斜体文本***

___粗斜体文本___

~~删除线效果~~

<u>下划线</u>

创建脚注 [^脚注]

==高亮==

H~2~O

X^2^

[^脚注]:我是脚注！！！

---

#### 列表

```markdown
* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项

- 第一项
- 第二项
- 第三项

1. 第一项
2. 第二项
3. 第三项
```

**显示效果**

* 第一项
* 第二项
* 第三项

+ 第一项
+ 第二项
+ 第三项

- 第一项
- 第二项
- 第三项

1. 第一项
2. 第二项
3. 第三项

**嵌套**

1. 第一项
   - 1.1
     - 1.1.1
     - 1.1.2
   - 1.2
2. 第二项
   - 1.1
   - 1.2

---

#### 区块

```markdown
> 区块引用
> 啦啦啦
> 哈哈哈

> 最外层
> > 第一层
> > > 第二层
```

**显示效果**

> 区块引用
>
> 啦啦啦
>
> 哈哈哈



> 最外层
>
> >第一层
> >
> >> 第二层



**嵌套**

> 最外层
>
> > 第一层
> >
> > - 1.1
> > - 1.2
> > - 1.3
> >
> > 第一层一楼

---

#### 代码

```markdown
`可以在段落上标注一个函数或片段的代码`
``` java 代码块可以指定一种语言
`小型代码块`
```

**显示效果**

这里是一个函数`printf()`

---

#### 链接

```markdown
[链接名称](链接地址)

或者

<链接地址>

例如:
这是一个百度链接[baidu](www.baidu.com)

也可以通过一个变量来设置一个链接
这个链接是百度[baidu][baidu]
这个链接是淘宝[taobao][taobao]
[baidu]:https://www.baidu.com/
[taobao]:https://www.taobao.com/
```

**显示效果**

这是一个百度链接[baidu](https://www.baidu.com)

也可以只用引用链接<https://www.baidu.com>

这个链接是百度[baidu][baidu]

这个链接是淘宝[taobao][taobao]

[baidu]:https://www.baidu.com/
[taobao]:https://www.taobao.com/

---

#### 图片

```markdown
![alt 属性文本](图片地址)
![alt 属性文本](图片地址 "可选标题")
1、开头一个感叹号 !
2、接着一个方括号，里面放上图片的替代文字
3、接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上选择性的 'title' 属性的文字。


也可以使用变量的方式
菜鸟[cainiao][1]
[1]:http://static.runoob.com/images/runoob-logo.png


Markdown 还没有办法指定图片的高度与宽度，如果你需要的话，你可以使用普通的 <img> 标签
<img src="http://static.runoob.com/images/runoob-logo.png" width="50%">
```

**显示效果**

![alt baidu](http://static.runoob.com/images/runoob-logo.png)

![alt cainiao](http://static.runoob.com/images/runoob-logo.png "菜鸟")



菜鸟[cainiao][1]

[1]:http://static.runoob.com/images/runoob-logo.png



<img src="http://static.runoob.com/images/runoob-logo.png " width="30%">

---

#### 表格

```markdown
|左对齐  |右对齐 | 居中对齐 |
|:--- | ---:|:---:|
|单元格|单元格|单元格|
|单元格|单元格|单元格|

:- 设置内容和标题栏居中右对齐
-: 设置内容和标题栏居左对齐
:-: 设置内容和标题栏居中对齐
```

**显示效果**

| 左对齐 | 右对齐 | 居中对齐 |
| :----- | -----: | :------: |
| 单元格 | 单元格 |  单元格  |
| 单元格 | 单元格 |  单元格  |

---

#### 高级技巧

```markdown
目前支持的 HTML 元素有：<kbd> <b> <i> <em> <sup> <sub> <br>等 ，如：

使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑

\ 转义字符

当你需要在编辑器中插入数学公式时，可以使用两个美元符 $$ 包裹 TeX 或 LaTeX 格式的数学公式来实现。提交后，问答和文章页会根据需要加载 Mathjax 对数学公式进行渲染。
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
${$tep1}{\style{visibility:hidden}{(x+1)(x+1)}}
$$
```

**显示效果**

使用<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd>重启电脑
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
${$tep1}{\style{visibility:hidden}{(x+1)(x+1)}}
$$

---





