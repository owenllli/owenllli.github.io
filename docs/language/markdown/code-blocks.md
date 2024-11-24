# Code blocks 代码块

## 配置项

### 复制按钮

如果你已经在`docs.yml`中配置好了`content.code.copy`，那么针对某一特定的代码块，你可以使用如下的格式关闭代码块复制按钮。

````text
``` { .cpp .no-copy}
// .cpp 应当为任何的特定的代码语言，不能是其他的文字
```
````

```{ .cpp .no-copy}
#include <iostream>
int main()
{
    std::cout<<"Hello world!";
    return 0;
}
```

如果不需要语法高亮，可以把特定的语言换成`.text`，这样代码块就不会产生文本高亮了。

### 代码块内注解

与先前的注解方式略有不同，如果你想在一个代码块中显示注解，需要参考下面的格式。

````text
```cpp
#include <iostream>
int main()
{
    std::cout<<"Hello world!";
    return 0; // (1)!
}   // (2)
```

1. 注解必须放在注释语句内，而插入代码中的注解是 Insiders 特有的功能。
2. 如果你想显示这个注释符号(.cpp中是`//`)，那么删去序号后面的`!`即可。
````

```cpp
#include <iostream>
int main()
{
    std::cout<<"Hello world!";
    return 0; // (1)
}   // (2)!
```

1. 注解必须放在注释语句内，而插入代码中的注解是 Insiders 特有的功能。
2. 如果你不想显示这个注释符号(.cpp中是`//`)，那么在序号后面加一个`!`即可。但是需要注意，这种方式下每个注解只能渲染一个代码注释。如果需要添加多个代码注释，由于技术原因，注释字符无法被去除。

## 使用方法

### 添加代码块

代码块必须用三个反引号包裹，并单独成行。在开头的反引号后添加语言或语言简写以启用语法高亮。

````Markdown title="添加代码块"
``` py
import tensorflow as tf
```
````

```py
import tensorflow as tf
```

### 为代码块添加标题

可通过 `title="<标题>"` 为代码块添加自定义标题，提供额外的上下文信息。

````Markdown title="添加代码块标题"
``` py title="Hello world.py"
print('Hello world!')
```
````

``` py title="Hello world.py"
print('Hello world!')
```

### 为代码块添加行号

你可以使用`linenums="<start>"`来为代码块添加行号，其中`<start>`可以被任意正整数(未验证)替换，不止局限于从1开始计数，这对于阅读从大型项目中剥离的代码非常有帮助。

````Markdown title="带行号的代码块"
``` py linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
````

``` py linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

### 高亮选定行

通过 `hl_lines="<line1>..."` 参数高亮特定行，其中`<line1>`等即为要高亮的行数，中间以空格分隔或以连字符(`-`)连接。行号的计数与上一部分设置的起始行号`linenums`无关，而是从1开始计数。

=== "使用空格分隔的多行高亮"

    ```` markdown title="使用空格分隔的多行高亮"
    ``` py hl_lines="2 3"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```
    ````


    ``` py linenums="1" hl_lines="2 3"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```

=== "使用连字符表示的多行高亮"

    ```` markdown title="使用连字符表示的多行高亮"
    ``` py hl_lines="3-5"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```
    ````

    ``` py linenums="1" hl_lines="3-5"
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```

### 内联代码块语法高亮

启用`InLineHilite`后，使用下面的格式来应用内联代码块的语法高亮。

```Markdown title="内联代码块高亮"
我们使用`#!cpp int main()`函数来表明主函数。
```

我们使用`#!cpp int main()`函数来表明主函数。

### 嵌入外部文件(?)

未做研究，详见[Embedding external files](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/#embedding-external-files).

## 自定义样式

如果使用了 Pygments，那么Material for MkDocs 提供了颜色均衡的内置主题，可用于亮暗模式。相关内容详见[Customization](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/#customization)，可用于自定义代码块某部分语法高亮时显示的颜色，还可以自定义注解部分显示的宽度。
