# Images 图片

虽然图片是 Markdown 的核心语法之一，但其在实际的使用中可能并不方便。Material for MkDocs 提供了更加舒适的图片处理体验，包括图片对齐样式和图片标题支持的功能。

## 配置项

### 图片灯箱(?)

<!-- 本网站未配置 -->
如果您想为文档添加图片缩放功能，可以使用与 Material for MkDocs 完美集成的 `glightbox` 插件。通过 pip 安装：

``` bash
pip install mkdocs-glightbox
```

然后在 `mkdocs.yml` 中添加以下配置：

``` yaml
plugins:
  - glightbox
```

建议查看插件的[配置选项](https://github.com/blueswen/mkdocs-glightbox#usage)以获得最佳效果。

## 使用方法

### 图片对齐

启用 Attribute Lists 后，可以通过添加 align 属性（如 align=left 或 align=right）来对齐图片。

<!-- 检查图片的相对路径如何设置 -->
=== "左对齐"

    ``` markdown title="图片左对齐"
    ![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa?text=–%20Image%20–){ align=left }
    ```

    <div markdown>

    ![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa?text=–%20Image%20–){ align=left width=300 }

    国破山河在，城春草木深。
    感时花溅泪，恨别鸟惊心。
    烽火连三月，家书抵万金。
    白头搔更短，浑欲不胜簪。

    </div>

=== "右对齐"

    ``` markdown title="图片右对齐"
    ![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa?text=–%20Image%20–){ align=right }
    ```

    <div markdown>

    ![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa?text=–%20Image%20–){ align=right width=300 }

    风急天高猿啸哀，渚清沙白鸟飞回。
    无边落木萧萧下，不尽长江滚滚来。
    万里悲秋常作客，百年多病独登台。
    艰难苦恨繁霜鬓，潦倒新停浊酒杯。

    </div>

=== "居中对齐?"

    为什么没有居中对齐？  
    `align` 属性不支持居中对齐，因此 Material for MkDocs 不支持此选项。你可以改用图片标题/说明语法，但加不加标题都是可以的。

如果屏幕宽度不足以在图片旁边显示文本（例如在移动设备上），图片会自动拉伸至视口的全宽。(?)

### 图片标题/说明

Markdown 语法本身并不支持给图片添加标题，但我们可以借助 HTML 的 `<figure>` 和 `<figcaption>` 标签来实现标题功能。如下所示。

``` markdown title="带标题的图片"
<figure markdown="span">
  ![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa?text=–%20Image%20–){ width="300" }
  <figcaption>Image caption</figcaption>
</figure>
```

<figure markdown="span">
  ![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa?text=–%20Image%20–){ width="300" }
  <figcaption>Image caption</figcaption>
</figure>

#### 更简单的方式

使用 Caption 插件，你可以为任何 Markdown 块元素(包括图片)添加标题。

``` markdown title="带标题的图片"
![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa?text=–%20Image%20–){ width="300" }
/// caption
这里是标题喵喵喵
///
```

![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa?text=–%20Image%20–){ width="300" }
/// caption
这里是标题喵喵喵
///

### 图片延时加载

现代浏览器支持通过 loading=lazy 指令对图片进行延迟加载。在不支持该功能的浏览器中，该功能则会自动降级为正常加载。(?)

``` markdown tite="手动设置图片延时加载"
![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa?text=–%20Image%20–){ loading=lazy }
```

![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa?text=–%20Image%20–){ loading=lazy }

### 亮暗模式图片切换

如果您启用了颜色模式切换功能，那么就可以分别为亮色模式和暗色模式分别设置不同的图片，只需在图片的 URL 中添加 `#only-light` 或 `#only-dark` 的哈希标记即可。

``` markdown title="为亮暗模式分别使用不同的图片"
![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa&text=-+Image+-#only-light)
![Image title](https://dummyimage.com/600x400/21222c/d5d7e2&text=-+Image+-#onlydark)
```

![Image title](https://dummyimage.com/600x400/f5f5f5/aaaaaa&text=-+Image+-#only-light)
![Image title](https://dummyimage.com/600x400/21222c/d5d7e2&text=-+Image+-#onlydark)

> 如果你自定义了颜色方案，请参看[Custom light scheme](https://squidfunk.github.io/mkdocs-material/reference/images/#light-and-dark-mode-custom-light-scheme)和[Custom dark scheme](https://squidfunk.github.io/mkdocs-material/reference/images/#light-and-dark-mode-custom-dark-scheme).
