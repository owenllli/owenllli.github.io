# Admonitions 警示块

## 使用方法

```Markdown
!!! note

    这是没有设置标题的 note 类型警示块
```

!!! note

    这是没有设置标题的 note 类型警示块

## 修改标题

```Markdown
!!! note "这里是[标题](#Admonitions-警示块)"

    这是设置了标题的 note 类型警示块，你可以在标题里任意发挥创意，例如加一个超链接，等等
```

!!! note "这里是[标题](#Admonitions-警示块)"

    这是设置了标题的 note 类型警示块，你可以在标题里任意发挥创意，例如加一个超链接，等等

## 删除标题

```Markdown
!!! note ""

    与修改标题类似，可以通过在类型限定符后添加空字符串完全省略图标和标题。但请注意，这在折叠块中无效
```

!!! note ""

    与修改标题类似，可以通过在类型限定符后添加空字符串完全省略图标和标题。但请注意，这在折叠块中是无效的

## 可折叠块

```Markdown
??? note

    启用 Details 扩展后，将警示块的起始标记从 !!! 更改为 ???，即可将其渲染为一个可折叠块，并在块的右侧显示一个小型折叠切换按钮
```

??? note

    启用 Details 扩展后，将警示块的起始标记从 !!! 更改为 ???，即可将其渲染为一个可折叠块，并在块的右侧显示一个小型折叠切换按钮

### 自动展开

```Markdown
???+ note

    在 ??? 后面加一个 + 即可将折叠块默认设置为展开状态
```

???+ note

    在 ??? 后面加一个 + 即可将折叠块默认设置为展开状态

## 内联块

### 右部内联块

!!! info inline end "右侧内联块"

    这是一个通过 inline end 修饰的内联块，因此该块会被渲染到文字右侧，这可以用于侧边栏显示信息

```Markdown
!!! info inline end "标题"

    这是一个通过 inline end 修饰的内联块，因此该块会被渲染到文字右侧，这可以用于侧边栏显示信息
```

### 左部内联块

!!! info inline end "左侧内联块"

    这是一个只通过 inline 修饰的内联块，因此该块会被渲染到文字左侧，这同样可以用于侧边栏显示信息。另外，使用 inline 修饰符的警告框必须声明在你希望其旁边显示的内容块之前。如果没有足够的空间在目标内容块旁渲染警告框，例如在移动设备视口中，警告框将会自动扩展到视口的全宽度。

```Markdown
!!! info inline end "左侧内联块"

    这是一个只通过 inline 修饰的内联块，因此该块会被渲染到文字左侧，这同样可以用于侧边栏显示信息
```

## 支持类型

以下是 Material for MkDocs 支持的类型限定符，默认类型设置为 note:
`note`

!!! note

    这是一个 note 类型的警示块

`abstract`

!!! abstract

    这是一个 abstract 类型的警示块

`info`

!!! info

    这是一个 info 类型的警示块

`tip`

!!! tip

    这是一个 tip 类型的警示块

`success`

!!! success

    这是一个 success 类型的警示块

`question`

!!! question

    这是一个 question 类型的警示块

`warning`

!!! warning

    这是一个 warning 类型的警示块

`failure`

!!! failure

    这是一个 failure 类型的警示块

`danger`

!!! danger

    这是一个 danger 类型的警示块

`bug`

!!! bug

    这是一个 bug 类型的警示块

`example`

!!! example

    这是一个 example 类型的警示块

`quote`

!!! quote

    这是一个 quote 类型的警示块

## 自定义设置

### 恢复到旧版本

在版本 8.5.6 之前，警示块的外观与现在的外观略有区别。具体对比可以看下图。
(TODO:塞一张对比图)
如果你想恢复到旧版的外观，可以将以下的 CSS 添加到一个额外的样式表中，并在 mkdocs.yml 中引用它即可。

=== "`docs/stylesheets/xxx.css`"

    ``` css
    .md-typeset .admonition,
    .md-typeset details {
      border-width: 0;
      border-left-width: 4px;
    }
    ```

=== "`mkdocs.yml`"

    ``` yaml
    extra_css:
      - stylesheets/extra.css
    ```

### 自定义警示块

参见 [Custom admonitions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#custom-admonitions).
