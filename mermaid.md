http://knsv.github.io/mermaid/

##FlowChart

画流程图首先要指定一个方向，共有四个可选方向：

* TB / TD - 从上到下
* BT - 从下到上
* RL - 从右向左
* LR - 从左向右

使用graph+方向来开始一个代码块，如：

    graph LR
    A --> B

可以画出一个两个节点A、B，包含一个从左到右的指向（注意写箭头的时候是两个短线）。

相同内容的文字会被认为是一个节点，如果文本内容很长，该节点多次出现就会弄得代码很长，而且也可能两个节点文字相同，这种情况可以借助id来实现：

    graph LR
    id1[A] --> id2[B]
    id2 --> id3[A]

这样第一个A和第二个A被认为是不同的节点。

有时候我们想在文本里加入括号，比如想输入id[(A)]，发现是不能正确渲染的，此时在文本上加入引号可以解决这个问题：

    id["(A)"]

如果想在文本里加入引号，那就要用html字符了：

    id["A double quote:#quot;"]

节点上可以加入点击事件和样式：

    graph LR;
        A-->B;
        click A functionName "Tooltip for a callback"
        click B "http://www.github.com" "This is a tooltip for a link"
        style A fill:#f9f,stroke:#333,stroke-width:4px;
        style B fill:#ccf,stroke:#f66,stroke-width:2px,stroke-dasharray: 5, 5;

可以加入默认样式：

    graph LR;
        classDef default fill:#f9f,stroke:#333,stroke-width:4px;

mermaid的文档中还提到了classDef定义普通样式，但是没有效果，不知道是不是这个版本里取消了。

关于fontawesome，需要的话可以自行参考：[fontawesome](http://knsv.github.io/mermaid/#messages)

### 节点形状

刚才看到，`id[A]`画出了一个方形的框，文本内容是A，除此之外，可以用`()`画圆角框，`(())`画圆框，`>]`画旗形框，`{}`画菱形框。

### 连接线型

`-->`画出一个实线的有向箭头，`---`无向实线，`-.->`画虚线，`==>`画粗实线，`--text-->`或`-->|text|`在有向实线上加文字，`--text---`或`---|text|`在无向实线上加文字（前两道后三道短线），`-.text.->`或`-.->|text|`在虚线上加文字，`==text==>`或`==>|text|`在粗实线上加文字）。

### 子图

可以用subgraph开启子图：

    graph TB
         subgraph one
         a1-->a2
         end
         subgraph two
         b1-->b2
         end
         subgraph three
         c1-->c2
         end
         c1-->a2



### code
### 形状展示
```
graph LR
    id1["(A"] --> id2>A]
    id2 --> id3(A)
    id3 --> id4((A))
    id4 --> id5{A}
```

### 线型展示
```
graph LR
    A --> B
    B --- C
    C -.-> D
    D ==> E
    H -- with text --> I
    I --> |with text|J
    J -- with text --- K
    K --- |with text|L
    O -. with text .-> P
    P -.-> |with text|Q
    Q == with text ==> R
    R ==> |with text|S
```

```
graph TB
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
    c1-->a2
```

```
graph LR;
    A-->B;
    C-->D
    click A functionName "Tooltip for a callback"
    click B "http://www.github.com" "This is a tooltip for a link"
    style A fill:#f9f,stroke:#333,stroke-width:4px;
    style B fill:#ccf,stroke:#f66,stroke-width:2px,stroke-dasharray: 5, 5;
```

```
graph TD
    B["fa:fa-twitter for peace"]
    B-->C[fa:fa-ban forbidden]
    B-->D(fa:fa-spinner);
    B-->E(A fa:fa-camera-retro perhaps?);
```




