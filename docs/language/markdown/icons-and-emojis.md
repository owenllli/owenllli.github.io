# Icons and Emojis 图标和表情

Material for MkDocs 的一大亮点是几乎无需额外的设置便可在项目文档中使用超过 10,000 个图标和数千种表情。此外，你还可以在 `mkdocs.yml`、自己的文档和模板中添加并使用自定义图标。

## 在库内搜索图标和表情

你可以使用 [material for mkdocs 的官方搜索功能](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/#search)来搜索并复制(相对路径)你想使用的表情或图标。仅支持英文搜索。
目前，Material for MkDocs 内置了以下四种图标集，上方的搜索功能也只能在这四个部分里寻找图标。

- :material-material-design: – [Material Design]
- :fontawesome-brands-font-awesome: – [FontAwesome]
- :octicons-mark-github-16: – [Octicons]
- :simple-simpleicons: – [Simple Icons]

## 使用方法

### Emojis

在 Markdown 中使用 emoji 时，将表情符号的短代码放在两个冒号之间即可使用。如果使用(官方推荐)的 Twemoji 表情，则可以在 [Emojipedia](https://emojipedia.org/twitter/) 中查找短代码。

``` title="smile emoji"
:smile:
```

<!-- TODO:看看这个markdown有没有什么区别，如果有区别记得扩展到整个文档 -->

<div markdown>

:smile:

</div>

### Icons

在`mkdocs.yml`中配置后，icons也可以像emoji一样使用，通过引用主题自带图标的有效相对路径(位于 `.icons` 目录下)，并将路径中的 `/` 替换为 `-`。

``` title="face laugh wink icon"
:fontawesome-regular-face-laugh-wink:
```

<div  markdown>

:fontawesome-regular-face-laugh-wink:

</div>

#### 添加颜色

启用 Attribute Lists 后，可以通过特殊语法为图标添加自定义 CSS 类。参考[with color](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/#with-colors).

#### 添加动效

与上一部分类似，你也可以通过自行定义 CSS 来实现图标的动效。参考[with animations](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/#with-animations).

### 侧边栏的Emojis和Icons

借助内置的 typeset 插件，可以在标题中使用图标和表情符号，这些内容同样会在侧边栏中渲染，插件也会保留 Markdown 和 HTML 的格式。
然而这个插件仅限 Insiders 版本使用。

## 自定义样式

### 在模板中使用图标

进行主题扩展、使用模板时才会用得上，详见[Using icons in templates](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/#using-icons-in-templates).
