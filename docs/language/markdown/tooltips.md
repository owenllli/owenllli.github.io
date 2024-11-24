# Tooltips 提示信息

技术文档中人们通常会使用许多缩写，而对于一些项目的新用户来说，这些缩写可能需要额外的解释。为了解决这个问题，Material for MkDocs 使用了一系列 Markdown 扩展来实现全站范围的术语表功能。

## 配置项

### 改进的提示信息

在启用该项功能后，Material for MkDocs 会用更美观的小型工具提示替代浏览器对 title 属性的渲染逻辑。(?)

启用后，工具提示将应用于以下元素：

- __内容部分__：带有 `title` 属性的元素、永久链接和代码复制按钮。

- __页眉部分__：主页按钮、标题、配色方案切换器和代码库链接。

- __导航部分__：被省略号缩短的链接（如 `...`）。

## 使用方法

### 添加提示信息

#### 超链接

Markdown 语法允许为每个链接指定 title 属性，当启用了改进的信息提示后，这些 title 属性将显示为精美的工具提示。

``` markdown title="行内语法的具有提示信息的超链接"
[把鼠标悬停在超链接上面](#添加提示信息 "这里是提示信息")
```

[把鼠标悬停在超链接上面](#添加提示信息 "这里是提示信息")

你还可以使用引用超链接，示例如下。

``` markdown title="使用引用超链接的具有提示信息的超链接"
[把鼠标悬停在超链接上面][hoveringInfo]

    [hoveringInfo]: #添加提示信息 "这里是提示信息"
```

[把鼠标悬停在超链接上面][hoveringInfo]

    [hoveringInfo]: #添加提示信息 "这里是提示信息"

#### 其他元素

对于其他元素，可以通过启用 `Attribute Lists` 扩展来为元素添加提示信息。

``` markdown title="带提示信息的图标"
:material-information-outline:{ title="Important information" }
```

:material-information-outline:{ title="Important information" }

### 添加缩写提示

缩写提示是一种类似于 URL 和脚注的特殊语法，可以为文本中的术语或缩写定义工具提示。其语法类似如下示例。

``` markdown title="缩写示例"
HTML 规范目前正在由 W3C 维护.

<!-- 方括号内的是想要说明的缩写，冒号后面跟着的即为缩写的全称解释 -->
*[HTML]: Hyper Text Markup Language, 超文本标记语言
*[W3C]: World Wide Web Consortium, 万维网联盟
```

HTML 规范目前正在由 W3C 维护.

*[HTML]: Hyper Text Markup Language, 超文本标记语言
*[W3C]: World Wide Web Consortium, 万维网联盟

### 添加术语表

如果你有为所有网页的同一术语都添加提示信息，那么你可能需要新建一个术语表。详情可见[Adding a glossary](https://squidfunk.github.io/mkdocs-material/reference/tooltips/#adding-a-glossary).
