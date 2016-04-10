# zmdeditor
modifier of marked.js

marked.js的扩展，综合Editor.md（https://pandao.github.io/editor.md/）和Markdown Plus（https://github.com/tylingsoft/markdown-plus）的特性，更易与现有系统集成。

正在开发中……


# 用法

1. 标题

    支持h1-h6六种标题，前面用n个`#`表示hn，如下：

        # 标题1
        ## 标题2
        ### 标题3
        #### 标题4
        ##### 标题5
        ###### 标题6

2. 粗体

    加粗，前后各用两个`*`(`-`等效，一般用`*`)包裹，效果：**加粗**。如下：

        **这里是加粗文字**

3. 删除线

    文字上添加删除线，前后各用两个`~`包裹，如下：

        ~~这里是删除线的内容~~

4. 下划线

    待补充

5. 高亮显示

    在文本前后各添加两个=，本文会被高亮显示：

        ==这里是高亮显示的文本==

5. 引用

    引用的文字在行首用`>`标识，如下：

        > 这里是引用的名人名言

6. 行内代码

    代码分为行内代码和代码块两种，行内代码在代码前后用`标识，就是Esc下面那个键的英文字符，如下：

        `这里面是行内代码`

7. 代码块

    只要把某段的缩进比正文多4个字符，这段文字就变成代码块，本文档所有使用例子都是作为代码块出现的。

8. 表格

    写表格要用下面的格式，其中第二行的---表示对应列的文字居中，:---表示左对齐，---:表示右对齐，:---:和---效果相同。

        th1 | th2 | th3
        ---|---:|:---
        tr1td1a | tr1td2 | tr1td3c
        tr2td1 | tr2td2b | tr2td3

9. 插入图片

    使用下面的语句插入图片：

        ![image](https://github.com/fluidicon.png)

    如果要规定图片的大小

10. 插入分割线

    短线（`-`）、星号（`*`）、下划线（`_`）的任意组合，三个以上即可形成一个横的长分割线：

        ---

11. 无序列表

    就是最常用的ul， 每个列表项的行首用`-`、`+`、`*`分割皆可。如：

        - 无序列表项1
            - 子项1
            - 子项2
            * 子项3
        + 无序列表项2
        * 无序列表项3

12. 行内autolink

    在尖括号内添加邮箱样式或:/样式，会自动生成响应的a链接：

        <zhfchdev@gmail.com>

    会被解析为：

        <a href="mailto:zhfchdev@gmail.com">mailto:zhfchdev@gmail.com</a>

13. 超链接

    格式：[展示文字](链接 "title")，链接可以用<>包裹，超链接点击会在新页面中打开：

        [链接名](<http://www.leaffork.com> "LEAFFORK")

14. 页内锚点

    没有单独的锚点设计，不过可以用HTML+超链接的形式完成，如：

        [hello](#new)
        <div id="new"></div>

    此时的超链接被点击时不会打开新标签页。

依赖：

jquery >= 1.9

[Raphael.js](https://github.com/DmitryBaranovskiy/raphael)

[highlight](https://highlightjs.org/ "highlight")

[squenceDiagram](http://bramp.github.io/js-sequence-diagrams/)

[printArea](https://github.com/RitsC/PrintArea)

[公式使用参考](https://meta.wikimedia.org/wiki/Help:Displaying_a_formula)

[Katex](https://github.com/Khan/KaTeX)

[各种图](https://github.com/knsv/mermaid)


