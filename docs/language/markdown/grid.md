# Grid 网格

Material for MkDocs 让您可以轻松将部分内容排布成网格，用于对表达相似意义或具有同等重要性的模块进行分组。网格布局非常适合构建索引页面，以简要概览文档的某一大部分内容。

## 使用方法

网格布局有两种类型：

1. 卡片网格(card grids)：将每个元素包装成悬停时会浮动的卡片。
2. 通用网格(generic grids)：可以将任意块元素排列成矩形形状。

### 卡片网格

卡片网格可以为每个网格项提供悬停时的精美卡片。其语法有两种：列表(list)语法、块(block)语法，分别支持不同的使用场景。

#### 列表语法

列表语法是卡片网格的一种快捷语法，它由带有 `grid` 和 `cards` 类的 `<div>` 包裹的无序（或有序）列表组成。例如下面的示例。

``` markdown title="列表卡片示例"
<div class="grid cards" markdown>

- :fontawesome-brands-html5: __HTML__ 用于文章内容和结构的构建
- :fontawesome-brands-js: __JavaScript__ 用于实现网页交互
- :fontawesome-brands-css3: __CSS__ 可以避免文字溢出容器
- :fontawesome-brands-internet-explorer: __Internet Explorer__ ... 您哪位?

</div>
```

<div class="grid cards" markdown>

- :fontawesome-brands-html5: __HTML__ 用于文章内容和结构的构建
- :fontawesome-brands-js: __JavaScript__ 用于实现网页交互
- :fontawesome-brands-css3: __CSS__ 可以避免文字溢出容器
- :fontawesome-brands-internet-explorer: __Internet Explorer__ ... 您哪位?

</div>

列表语法支持任意种类的Markdown语法，只需确保外层 `<div>` 定义了 markdown 属性即可。以下是一个较为复杂的示例(来自官方文档)，包含了图标的设置和超链接等。

``` markdown title="更复杂的列表卡片示例"
- :material-clock-fast:{ .lg .middle } __光速安装！__

    ---

    通过 [`pip`](https://squidfunk.github.io/mkdocs-material/getting-started/#with-pip) 安装 [`mkdocs-material`](https://pypistats.org/packages/mkdocs-material)，一分钟都不需要！

    [:octicons-arrow-right-24: Getting started](https://squidfunk.github.io/mkdocs-material/getting-started/)

- :fontawesome-brands-markdown:{ .lg .middle } __区区 Markdown 而已__

    ---

    你只需要专注于内容，生成响应式、可搜索的静态网页就交给我们吧！

    [:octicons-arrow-right-24: Reference](https://squidfunk.github.io/mkdocs-material/reference/)

- :material-format-font:{ .lg .middle } __为你量身打造！__

    ---

    换颜色、换字体、换语言、换图标、换logo、诸如此类，仅需短短几行就能实现。

    [:octicons-arrow-right-24: Customization](https://squidfunk.github.io/mkdocs-material/customization/)

- :material-scale-balance:{ .lg .middle } __基于 MIT 协议开源__

    ---

    Material for MkDocs 基于 MIT 协议开源，你可以在 [GitHub](https://github.com/squidfunk/mkdocs-material) 上自由访问此项目。

    [:octicons-arrow-right-24: License](https://squidfunk.github.io/mkdocs-material/license/)

</div>
```

<div class="grid cards" markdown>

- :material-clock-fast:{ .lg .middle } __光速安装！__

    ---

    通过 [`pip`](https://squidfunk.github.io/mkdocs-material/getting-started/#with-pip) 安装 [`mkdocs-material`](https://pypistats.org/packages/mkdocs-material)，一分钟都不需要！

    [:octicons-arrow-right-24: Getting started](https://squidfunk.github.io/mkdocs-material/getting-started/)

- :fontawesome-brands-markdown:{ .lg .middle } __区区 Markdown 而已__

    ---

    你只需要专注于内容，生成响应式、可搜索的静态网页就交给我们吧！

    [:octicons-arrow-right-24: Reference](https://squidfunk.github.io/mkdocs-material/reference/)

- :material-format-font:{ .lg .middle } __为你量身打造！__

    ---

    换颜色、换字体、换语言、换图标、换logo、诸如此类，仅需短短几行就能实现。

    [:octicons-arrow-right-24: Customization](https://squidfunk.github.io/mkdocs-material/customization/)

- :material-scale-balance:{ .lg .middle } __基于 MIT 协议开源__

    ---

    Material for MkDocs 基于 MIT 协议开源，你可以在 [GitHub](https://github.com/squidfunk/mkdocs-material) 上自由访问此项目。

    [:octicons-arrow-right-24: License](https://squidfunk.github.io/mkdocs-material/license/)

</div>

当屏幕空间不足时（例如在移动设备上），网格项会拉伸到视口的全宽；在有相当足够的空间时，比例如当设置了隐藏两侧边栏时，网格则可以显示 3 项或更多内容。

#### 块语法

块语法允许卡片与其他任意元素结合排列。只需将 `card` 类添加到网格中的任意块元素上即可。

``` markdown title="块级卡片示例"
<div class="grid" markdown>

:fontawesome-brands-html5: __HTML__ 用于文章内容和结构的构建
{ .card }
:fontawesome-brands-js: __JavaScript__ 用于实现网页交互
{ .card }
:fontawesome-brands-css3: __CSS__ 可以避免文字溢出容器
{ .card }
> :fontawesome-brands-internet-explorer: __Internet Explorer__ ... 您哪位?

</div>
```

<div class="grid" markdown>

:fontawesome-brands-html5: __HTML__ 用于文章内容和结构的构建
{ .card }
:fontawesome-brands-js: __JavaScript__ 用于实现网页交互
{ .card }
:fontawesome-brands-css3: __CSS__ 可以避免文字溢出容器
{ .card }
> :fontawesome-brands-internet-explorer: __Internet Explorer__ ... 您哪位?

</div>

这种语法虽然初看略显繁琐，但可以自由混合卡片和其他元素，并且能自动适应网格布局。

### 通用网格

通用网格允许将任意块元素，例如警示块(admonitions)、代码块(code blocks)、内容选项卡(content tabs)等排列成网格。只需用带有 `grid` 类的 `<div>` 标签包裹一组块元素即可。下面是一个简单的示例。

``` markdown title="通用网格示例"
<div class="grid" markdown>

=== "无序列表"

    * 长太息以掩涕兮，哀民生之多艰。
    * 余虽好修姱以鞿羁兮，謇朝谇而夕替。
    * 既替余以蕙纕兮，又申之以揽茝。

=== "有序列表"

    1. 既替余以蕙纕兮，又申之以揽茝。
    2. 亦余心之所善兮，虽九死其犹未悔。
    3. 怨灵修之浩荡兮，终不察夫民心。

``` title="选项卡代码块"
=== "无序列表"

    * 众女嫉余之蛾眉兮，谣诼谓余以善淫。
    * 固时俗之工巧兮，偭规矩而改错。
    * 背绳墨以追曲兮，竞周容以为度。

=== "有序列表"

    1. 忳郁邑余侘傺兮，吾独穷困乎此时也。
    2. 宁溘死以流亡兮，余不忍为此态也。
    3. 鸷鸟之不群兮，自前世而固然。

</div>
```

上面的内容会被渲染为如下样式。

<div class="grid" markdown>

=== "无序列表"

    * 长太息以掩涕兮，哀民生之多艰。
    * 余虽好修姱以鞿羁兮，謇朝谇而夕替。
    * 既替余以蕙纕兮，又申之以揽茝。

=== "有序列表"

    1. 既替余以蕙纕兮，又申之以揽茝。
    2. 亦余心之所善兮，虽九死其犹未悔。
    3. 怨灵修之浩荡兮，终不察夫民心。

``` title="选项卡代码块"
=== "无序列表"

    * 众女嫉余之蛾眉兮，谣诼谓余以善淫。
    * 固时俗之工巧兮，偭规矩而改错。
    * 背绳墨以追曲兮，竞周容以为度。

=== "有序列表"

    1. 忳郁邑余侘傺兮，吾独穷困乎此时也。
    2. 宁溘死以流亡兮，余不忍为此态也。
    3. 鸷鸟之不群兮，自前世而固然。
```

</div>
