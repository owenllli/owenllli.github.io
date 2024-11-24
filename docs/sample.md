---
tags:
  - example tag #标签
comments: ture #开启评论区
search:
  #boost: 2 #站内搜索权值提升
  #boost: 0.5 #站内搜索权值下降
  exclude: true #搜索内容时不检索此页面
hide:
  - tags #隐藏标签
  - footer #隐藏“上一页”“下一页”
  - navigation #隐藏导航栏
  - toc #隐藏 toc
---


# Markdown 基本语法

本文依照Material for mkdocks的官方文档制作，目的是记录未来可能会用到的Markdown格式，本文中的许多Markdown格式均不具有普适性，仅可在pymdownx扩展支持下的Material for mkdocs中生效。

## Admonitions 警示块

### 使用方法

```Markdown
!!! note

    这是没有设置标题的 note 类型警示块
```

!!! note

    这是没有设置标题的 note 类型警示块

### 修改标题

```Markdown
!!! note "这里是[标题](#Admonitions-警示块)"

    这是设置了标题的 note 类型警示块，你可以在标题里任意发挥创意，例如加一个超链接，等等
```

!!! note "这里是[标题](#Admonitions-警示块)"

    这是设置了标题的 note 类型警示块，你可以在标题里任意发挥创意，例如加一个超链接，等等

### 删除标题

```Markdown
!!! note ""

    与修改标题类似，可以通过在类型限定符后添加空字符串完全省略图标和标题。但请注意，这在折叠块中无效
```

!!! note ""

    与修改标题类似，可以通过在类型限定符后添加空字符串完全省略图标和标题。但请注意，这在折叠块中是无效的

### 可折叠块

```Markdown
??? note

    启用 Details 扩展后，将警示块的起始标记从 !!! 更改为 ???，即可将其渲染为一个可折叠块，并在块的右侧显示一个小型折叠切换按钮
```

??? note

    启用 Details 扩展后，将警示块的起始标记从 !!! 更改为 ???，即可将其渲染为一个可折叠块，并在块的右侧显示一个小型折叠切换按钮

#### 自动展开

```Markdown
???+ note

    在 ??? 后面加一个 + 即可将折叠块默认设置为展开状态
```

???+ note

    在 ??? 后面加一个 + 即可将折叠块默认设置为展开状态

### 内联块

#### 右部内联块

!!! info inline end "右侧内联块"

    这是一个通过 inline end 修饰的内联块，因此该块会被渲染到文字右侧，这可以用于侧边栏显示信息

```Markdown
!!! info inline end "标题"

    这是一个通过 inline end 修饰的内联块，因此该块会被渲染到文字右侧，这可以用于侧边栏显示信息
```

#### 左部内联块

!!! info inline end "左侧内联块"

    这是一个只通过 inline 修饰的内联块，因此该块会被渲染到文字左侧，这同样可以用于侧边栏显示信息。另外，使用 inline 修饰符的警告框必须声明在你希望其旁边显示的内容块之前。如果没有足够的空间在目标内容块旁渲染警告框，例如在移动设备视口中，警告框将会自动扩展到视口的全宽度。

```Markdown
!!! info inline end "左侧内联块"

    这是一个只通过 inline 修饰的内联块，因此该块会被渲染到文字左侧，这同样可以用于侧边栏显示信息
```

### 支持类型

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

### 自定义设置

#### 恢复到旧版本

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

#### 自定义警示块

参见 [Custom admonitions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#custom-admonitions).

## Annotations 注解

注解(Annotations)是一项可以在文档中任何位置插入的一个小标记，点击后会展开一个工具提示、可以显示任意包含 Markdown 的内容。

### 使用方法

#### 添加注解

注解由两部分内容组成：

- 标记（Marker）: 放置在 .annotate 类块中，可以放在任何地方。
- 内容（Content）: 位于标记块下方的列表中。

```Markdown title="使用注解添加注释"
豫章(1)故郡，洪都新府。星分翼轸，地接衡庐。襟三江而带五湖，控蛮荆而引瓯越。物华天宝，龙光射牛斗之墟；人杰地灵，徐孺(2)下陈蕃之榻。雄州雾列，俊采星驰。(3)
{ .annotate }

1. 滕王阁在今江西省南昌市。南昌，为汉豫章郡治。唐代宗当政之后，为了避讳唐代宗的名（李豫），“豫章故郡”被替换为“南昌故郡”。所以现在滕王阁内的石碑以及苏轼的手书都作“南昌故郡”。
2. 徐孺子的省称。徐孺子名稚，东汉豫章南昌人，当时隐士。据《后汉书•徐稚传》，东汉名士陈蕃为豫章太守，不接宾客，惟徐稚来访时，才设一睡榻，徐稚去后又悬置起来。
3. 注解内容来自[百度汉语](https://hanyu.baidu.com/s?wd=%E6%BB%95%E7%8E%8B%E9%98%81%E5%BA%8F&from=poem)。
```

豫章(1)故郡，洪都新府。星分翼轸，地接衡庐。襟三江而带五湖，控蛮荆而引瓯越。物华天宝，龙光射牛斗之墟；人杰地灵，徐孺(2)下陈蕃之榻。雄州雾列，俊采星驰。(3)
{ .annotate }

1. 滕王阁在今江西省南昌市。南昌，为汉豫章郡治。唐代宗当政之后，为了避讳唐代宗的名（李豫），“豫章故郡”被替换为“南昌故郡”。所以现在滕王阁内的石碑以及苏轼的手书都作“南昌故郡”。
2. 徐孺子的省称。徐孺子名稚，东汉豫章南昌人，当时隐士。据《后汉书•徐稚传》，东汉名士陈蕃为豫章太守，不接宾客，惟徐稚来访时，才设一睡榻，徐稚去后又悬置起来。
3. 注解内容来自[百度汉语](https://hanyu.baidu.com/s?wd=%E6%BB%95%E7%8E%8B%E9%98%81%E5%BA%8F&from=poem)。

#### 嵌套注解

启用 `pymdownx.superfences` 后，可以通过将 `.annotate` 类添加到注解内容的列表项中来实现注解嵌套，并可以继续重复该过程。

```Markdown title="使用嵌套注解"
豫章(1)故郡，洪都新府。星分翼轸，地接衡庐。襟三江而带五湖，控蛮荆而引瓯越。物华天宝，龙光射牛斗之墟；人杰地灵，徐孺下陈蕃之榻。雄州雾列，俊采星驰。(2)
{ .annotate }

1. 滕王阁在今江西省南昌市。南昌，为汉豫章郡治。唐代宗当政之后，为了避讳唐代宗的名(1)，“豫章故郡”被替换为“南昌故郡”。所以现在滕王阁内的石碑以及苏轼的手书都作“南昌故郡”。
   { .annotate }

   1. 唐代宗李豫（726 年 11 月 11 日 － 779 年 6 月 10 日），初名李俶，陇西狄道（今甘肃省临洮县）人。唐朝第九位皇帝。

2. 注解内容来自[百度汉语](https://hanyu.baidu.com/s?wd=%E6%BB%95%E7%8E%8B%E9%98%81%E5%BA%8F&from=poem)。
```

豫章(1)故郡，洪都新府。星分翼轸，地接衡庐。襟三江而带五湖，控蛮荆而引瓯越。物华天宝，龙光射牛斗之墟；人杰地灵，徐孺下陈蕃之榻。雄州雾列，俊采星驰。(2)
{ .annotate }

1. 滕王阁在今江西省南昌市。南昌，为汉豫章郡治。唐代宗当政之后，为了避讳唐代宗的名(1)，“豫章故郡”被替换为“南昌故郡”。所以现在滕王阁内的石碑以及苏轼的手书都作“南昌故郡”。
   { .annotate }

   1. 唐代宗李豫（726 年 11 月 11 日 － 779 年 6 月 10 日），初名李俶，陇西狄道（今甘肃省临洮县）人。唐朝第九位皇帝。

2. 注解内容来自[百度汉语](https://hanyu.baidu.com/s?wd=%E6%BB%95%E7%8E%8B%E9%98%81%E5%BA%8F&from=poem)。

#### 与警示块结合

注解可以添加到提示块的标题和内容中，你只需要在提示块类型限定符后添加 annotate 修饰符即可实现，这与内联块的工作方式类似。

```Markdown
!!! note annotate "这是标题(1)"

    这是正文(2)，这是一段很水的正文。

1. 这是针对标题的注解
2. 这是针对正文的注解
```

!!! note annotate "这是标题(1)"

    这是正文(2)，这是一段很水的正文。

1. 这是针对标题的注解
2. 这是针对正文的注解

#### 与选项卡结合

内容选项卡支持注解，但 `.annotate` 类只能添加到单个内容选项卡块中，不能直接添加到整个选项卡容器上。

```Markdown title="带注解的选项卡"
=== "滕王阁序(节选)"

    时维九月，序属三秋。潦水尽而寒潭清，烟光凝而暮山紫。俨骖騑(1)于上路，访风景于崇阿；临帝子之长洲，得天人之旧馆。层峦耸翠，上出重霄；飞阁流丹，下临无地。鹤汀凫渚，穷岛屿之萦回；桂殿兰宫，即冈峦之体势。
    { .annotate }

    1. 驾车的马匹。

=== "梦游天姥吟留别"

    海客谈瀛洲(1)，烟涛微茫信难求，越人语天姥，云霞明灭或可睹。天姥连天向天横，势拔五岳掩赤城。天台四万八千丈，对此欲倒东南倾。我欲因之梦吴越，一夜飞度镜湖月。湖月照我影，送我至剡溪。谢公宿处今尚在，渌水荡漾清猿啼。脚著谢公屐，身登青云梯。半壁见海日，空中闻天鸡。千岩万转路不定，迷花倚石忽已暝。熊咆龙吟殷岩泉，栗深林兮惊层巅。云青青兮欲雨，水澹澹兮生烟。列缺霹雳，丘峦崩摧。洞天石扉，訇然中开。青冥浩荡不见底，日月照耀金银台。霓为衣兮风为马，云之君兮纷纷而来下。虎鼓瑟兮鸾回车，仙之人兮列如麻。忽魂悸以魄动，恍惊起而长嗟。惟觉时之枕席，失向来之烟霞。世间行乐亦如此，古来万事东流水。别君去兮何时还？且放白鹿青崖间。须行即骑访名山。安能摧眉折腰事权贵，使我不得开心颜！
    { .annotate }

    1. 古代传说中的东海三座仙山之一（另两座叫蓬莱和方丈）。
```

=== "滕王阁序(节选)"

    时维九月，序属三秋。潦水尽而寒潭清，烟光凝而暮山紫。俨骖騑(1)于上路，访风景于崇阿；临帝子之长洲，得天人之旧馆。层峦耸翠，上出重霄；飞阁流丹，下临无地。鹤汀凫渚，穷岛屿之萦回；桂殿兰宫，即冈峦之体势。
    { .annotate }

    1. 驾车的马匹。

=== "梦游天姥吟留别"

    海客谈瀛洲(1)，烟涛微茫信难求，越人语天姥，云霞明灭或可睹。天姥连天向天横，势拔五岳掩赤城。天台四万八千丈，对此欲倒东南倾。我欲因之梦吴越，一夜飞度镜湖月。湖月照我影，送我至剡溪。谢公宿处今尚在，渌水荡漾清猿啼。脚著谢公屐，身登青云梯。半壁见海日，空中闻天鸡。千岩万转路不定，迷花倚石忽已暝。熊咆龙吟殷岩泉，栗深林兮惊层巅。云青青兮欲雨，水澹澹兮生烟。列缺霹雳，丘峦崩摧。洞天石扉，訇然中开。青冥浩荡不见底，日月照耀金银台。霓为衣兮风为马，云之君兮纷纷而来下。虎鼓瑟兮鸾回车，仙之人兮列如麻。忽魂悸以魄动，恍惊起而长嗟。惟觉时之枕席，失向来之烟霞。世间行乐亦如此，古来万事东流水。别君去兮何时还？且放白鹿青崖间。须行即骑访名山。安能摧眉折腰事权贵，使我不得开心颜！
    { .annotate }

    1. 古代传说中的东海三座仙山之一（另两座叫蓬莱和方丈）。

#### 在其他元素中使用注解

通过 `Attribute Lists` 扩展，可以为大多数元素添加注解，但该扩展存在一些限制。例如，某些情况下需要结合 `Markdown in HTML` 扩展，使用带 .annotate 类的 `<div>` 包裹任意元素。使用这种方法，注解就可以被应用于块引用、列表等多种不被 Attribute Lists 支持的元素上了。但是，代码块的注解语法与此处的不同，这点我们后面会再次提及。
另外，数据表(data tables)不支持注解，这点可能会在官方的后续更新中解决。

```Markdown title="使用HTML来实现注解"
<div class="annotate" markdown>

> 壬戌之秋，七月既望(1)，苏子与客泛舟游于赤壁之下。清风徐来，水波不兴。举酒属客，诵明月之诗，歌窈窕之章。少焉，月出于东山之上，徘徊于斗牛之间。白露横江，水光接天。纵一苇之所如，凌万顷之茫然。浩浩乎如冯虚御风，而不知其所止；飘飘乎如遗世独立，羽化而登仙。

</div>

1.  农历每月十六。农历每月十五日为“望日”，十六日为“既望”。
```

<div class="annotate" markdown>

> 壬戌之秋，七月既望(1)，苏子与客泛舟游于赤壁之下。清风徐来，水波不兴。举酒属客，诵明月之诗，歌窈窕之章。少焉，月出于东山之上，徘徊于斗牛之间。白露横江，水光接天。纵一苇之所如，凌万顷之茫然。浩浩乎如冯虚御风，而不知其所止；飘飘乎如遗世独立，羽化而登仙。

</div>

1. 农历每月十六。农历每月十五日为“望日”，十六日为“既望”。

## Buttons 按钮

Material for MkDocs 为按钮(包含主要按钮和次要按钮)提供了专门的样式，这些样式可以应用于任意链接、标签(label)或按钮(button)元素。这对于包含的引导用户行动(Call-to-Action)的文档或是登录页等可能特别有用。

### 使用方法

#### 添加一个按钮

要将超链接渲染为按钮，只需在超链接后使用 `.md-button` 类选择器。如果特别设置了 primary color 和 accent color，按钮将自动应用选定的主题色。

```Markdown title="按钮示例"
[这是一个按钮](#Buttons-按钮-使用方法){ .md-button }
```

[这是一个按钮](#Buttons-按钮-使用方法){ .md-button }

#### 主要按钮(Primary Buttons)

如果你想用选定的 primary color 填充按钮，而非透明的底色填充，那么你就需要用到主要按钮。使用方法见下。

```Markdown title="主要按钮"
[这是一个主要按钮](#Buttons-按钮-使用方法){ .md-button .md-button--primary }
```

[这是一个主要按钮](#Buttons-按钮-使用方法){ .md-button .md-button--primary }

#### 带图标的按钮

```Markdown title="带图标的按钮"
[发送 :fontawesome-solid-paper-plane:](#Buttons-按钮-使用方法){ .md-button }
```

[发送 :fontawesome-solid-paper-plane:](#Buttons-按钮-使用方法){ .md-button }

## Code blocks 代码块

### 配置项

#### 复制按钮

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

#### 代码块内注解

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

### 使用方法

#### 添加代码块

代码块必须用三个反引号包裹，并单独成行。在开头的反引号后添加语言或语言简写以启用语法高亮。

````Markdown title="添加代码块"
``` py
import tensorflow as tf
```
````

```py
import tensorflow as tf
```

#### 为代码块添加标题

可通过 `title="<标题>"` 为代码块添加自定义标题，提供额外的上下文信息。

````Markdown title="添加代码块标题"
``` py title="Hello world.py"
print('Hello world!')
```
````

``` py title="Hello world.py"
print('Hello world!')
```

#### 为代码块添加行号

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

#### 高亮选定行

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

#### 内联代码块语法高亮

启用`InLineHilite`后，使用下面的格式来应用内联代码块的语法高亮。

```Markdown title="内联代码块高亮"
我们使用`#!cpp int main()`函数来表明主函数。
```

我们使用`#!cpp int main()`函数来表明主函数。

#### 嵌入外部文件(?)

未做研究，详见[Embedding external files](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/#embedding-external-files).

### 自定义样式

如果使用了 Pygments，那么Material for MkDocs 提供了颜色均衡的内置主题，可用于亮暗模式。相关内容详见[Customization](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/#customization)，可用于自定义代码块某部分语法高亮时显示的颜色，还可以自定义注解部分显示的宽度。

## Content tabs 选项卡

有时，将不同的内容分组到不同的选项卡下是很有用的，例如描述如何在不同语言下编写功能相同的代码时。Material for MkDocs 提供了美观且实用的选项卡功能，可以将代码块和其他的内容分组显示。

### 配置项

#### 锚点链接

为了更方便地链接和共享内容选项卡，每个内容选项卡都会自动添加一个锚点链接。你可以复制选项卡的链接，并在同一页面或其他页面上创建链接。
TODO:测试一下，这部分还没尝试过

```markdown
=== "选项卡1"
    [选项卡2][tab2]
    [tab3]: #锚点链接--选项卡2

=== "选项卡2"
    [选项卡3][tab3]
    [tab3]: #锚点链接--选项卡3

=== "选项卡3"
    [锚点链接][tabAnchor]
    [tabAnchor]: #锚点链接
```

=== "选项卡1"
    [选项卡2][tab2]
    [tab3]: #锚点链接--选项卡2

=== "选项卡2"
    [选项卡3][tab3]
    [tab3]: #锚点链接--选项卡3

=== "选项卡3"
    [锚点链接][tabAnchor]
    [tabAnchor]: #锚点链接

#### 选项卡关联

启用下方的功能后，整个文档站点中的所有内容选项卡将根据标签相关联。当用户点击某个选项卡时，具有相同标签的选项卡将同步切换。
选项卡基于标签而非顺序关联，这意味着无论选项卡在容器中的顺序如何，标签相同的选项卡都会同时激活。此外，此功能与即时加载完全集成，并可在页面加载之间保持状态。

``` yaml title="mkdocs.yml"
theme:
  features:
    - content.tabs.link
```

### 使用方法

#### 分组代码块

代码块是内容选项卡的主要服务对象，可以视为内容选项卡的一种特殊情况。带有单个代码块的选项卡始终不会添加水平间距(?)。

```` text title="代码块分组"
=== "C"

    ``` c
    #include <stdio.h>

    int main() {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` cpp
    #include <iostream>

    int main() {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```
````

=== "C"

    ``` c
    #include <stdio.h>

    int main() {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` cpp
    #include <iostream>

    int main() {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```

#### 分组其他内容

当一个内容选项卡包含多个代码块时，它会显示出水平间距。垂直间距不会自动添加，但可以通过将选项卡嵌套在其他块中来实现(?)。

```text title="包含其他内容的选项卡"
=== "无序列表"

    * 白日依山尽
    * 黄河入海流

=== "有序列表"

    1. 欲穷千里目
    2. 更上一层楼
```

=== "无序列表"

    * 白日依山尽
    * 黄河入海流

=== "有序列表"

    1. 欲穷千里目
    2. 更上一层楼

#### 选项卡嵌套

启用 SuperFences 后，内容选项卡可以嵌套任意内容，包括进一步的内容选项卡，还可以嵌套在其他块（如提示块或引用块）中。例如：
TODO:未验证如何嵌套多层选项卡

````text title="套娃"
!!! example

    === "无序列表"

        ``` markdown
        * 白日依山尽
        * 黄河入海流
        ```

    === "有序列表"

        === "欲穷"
            千里目

        === "更上"
            一层楼
````

!!! example

    === "无序列表"

        ``` markdown
        * 白日依山尽
        * 黄河入海流
        ```

    === "有序列表"

        === "欲穷"
            千里目
            
        === "更上"
            一层楼

## Data tables 数据表

Material for MkDocs 为数据表格定义了默认样式，这是一种在项目文档中呈现表格数据的极佳方式。此外，通过引入第三方库和额外的 JavaScript，还可以实现可排序表格等自定义功能。

### 使用方法

数据表格可以在项目文档的任何位置使用，支持包含内联代码块、图标以及表情符号等任意的 Markdown 内容。

```Markdown title="数据表"
<!-- (1)! -->
| 作者 | 诗篇|
<!-- (2)! -->
| --- | --- |
| 李白 | 《将进酒》|
| 杜甫 | 《春望》  |
| 韩愈 | 《师说》  |
```

1. 这些`|`分隔符不对齐也是可以的
2. 这些`-`想写多少都可以，甚至只有一个也是可以的

| 作者 | 诗篇|
| --- | --- |
| 李白 | 《将进酒》|
| 杜甫 | 《春望》  |
| 韩愈 | 《师说》  |

#### 对齐方式

如果你需要将某一列的内容对齐到左侧、居中或右侧，可以在分隔符中使用 `:` 来实现。

=== "左侧对齐"

    ``` markdown hl_lines="2" title="左侧对齐的数据表"
    | 作者 | 诗篇|
    | :--- | :--- |
    | 李白 | 《将进酒》|
    | 杜甫 | 《春望》  |
    | 韩愈 | 《师说》  |
    ```

    | 作者 | 诗篇|
    | :--- | :--- |
    | 李白 | 《将进酒》|
    | 杜甫 | 《春望》  |
    | 韩愈 | 《师说》  |

=== "居中对齐"

    ``` markdown hl_lines="2" title="居中对齐的数据表"
    | 作者 | 诗篇|
    | :--: | :--: |
    | 李白 | 《将进酒》|
    | 杜甫 | 《春望》  |
    | 韩愈 | 《师说》  |
    ```

    | 作者 | 诗篇|
    | :--: | :--: |
    | 李白 | 《将进酒》|
    | 杜甫 | 《春望》  |
    | 韩愈 | 《师说》  |

=== "靠右对齐"

    ``` markdown hl_lines="2" title="靠右对齐的数据表"
    | 作者 | 诗篇|
    | ---: | ---: |
    | 李白 | 《将进酒》|
    | 杜甫 | 《春望》  |
    | 韩愈 | 《师说》  |
    ```

    | 作者 | 诗篇|
    | ---: | ---: |
    | 李白 | 《将进酒》|
    | 杜甫 | 《春望》  |
    | 韩愈 | 《师说》  |

### 自定义设置

#### 表格排序

如果需要让数据表格支持排序，可以引入 `tablesort`，该功能已与 Material for MkDocs 原生集成，并通过额外的 JavaScript 支持即时加载。详见[Sortable tables](https://squidfunk.github.io/mkdocs-material/reference/data-tables/#sortable-tables).
更多关于 `tablesort` 的内容详见[tablesort](https://tristen.ca/tablesort/demo/).

#### 从外部文件导入表格

使用插件[mkdocs-table-reader-plugin](https://timvink.github.io/mkdocs-table-reader-plugin/)，使得你能够从一个CSV或Excel文件中导入一个表格。

## Diagrams 图表

图表可以帮助传达不同技术组件之间复杂的关系和相互连接，是项目文档的极佳补充。Material for MkDocs 集成了 Mermaid.js，这是一个非常流行且灵活的绘图工具。下面的使用方法也都是基于 Mermaid 的语法进行的，Mermain的教程可以[在此处查看](https://mermaid.js.org/ecosystem/tutorials.html)。
TODO:学会怎么使用Mermaid画图

### 使用方法

#### 流程图(Flowcharts)

流程图用于表示工作流或过程。步骤会以各种节点形式呈现，并通过边连接，描述步骤的执行顺序。

```` markdown title="流程图"
``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```
````

``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```

#### 序列图(Sequence Diagrams)

序列图描述了多个对象或参与者之间的交互顺序，以及它们之间的信息交换。

```` markdown title="序列图"
``` mermaid
sequenceDiagram
  autonumber
  Alice->>John: Hello John, how are you?
  loop Healthcheck
      John->>John: Fight against hypochondria
  end
  Note right of John: Rational thoughts!
  John-->>Alice: Great!
  John->>Bob: How about you?
  Bob-->>John: Jolly good!
```
````

``` mermaid
sequenceDiagram
  autonumber
  Alice->>John: Hello John, how are you?
  loop Healthcheck
      John->>John: Fight against hypochondria
  end
  Note right of John: Rational thoughts!
  John-->>Alice: Great!
  John->>Bob: How about you?
  Bob-->>John: Jolly good!
```

#### 状态图(State Diagrams)

状态图用于描述系统的行为，将其分解为有限数量的状态及状态之间的转换。

```` markdown title="状态图"
``` mermaid
stateDiagram-v2
  state fork_state <<fork>>
    [*] --> fork_state
    fork_state --> State2
    fork_state --> State3

    state join_state <<join>>
    State2 --> join_state
    State3 --> join_state
    join_state --> State4
    State4 --> [*]
```
````

``` mermaid
stateDiagram-v2
  state fork_state <<fork>>
    [*] --> fork_state
    fork_state --> State2
    fork_state --> State3

    state join_state <<join>>
    State2 --> join_state
    State3 --> join_state
    join_state --> State4
    State4 --> [*]
```

#### 类图(Class Diagrams)

类图是面向对象编程的核心，用于通过建模类及它们之间的关系来描述系统结构。

```` markdown title="类图"
``` mermaid
classDiagram
  Person <|-- Student
  Person <|-- Professor
  Person : +String name
  Person : +String phoneNumber
  Person : +String emailAddress
  Person: +purchaseParkingPass()
  Address "1" <-- "0..1" Person:lives at
  class Student{
    +int studentNumber
    +int averageMark
    +isEligibleToEnrol()
    +getSeminarsTaken()
  }
  class Professor{
    +int salary
  }
  class Address{
    +String street
    +String city
    +String state
    +int postalCode
    +String country
    -validate()
    +outputAsLabel()  
  }
```
````

``` mermaid
classDiagram
  Person <|-- Student
  Person <|-- Professor
  Person : +String name
  Person : +String phoneNumber
  Person : +String emailAddress
  Person: +purchaseParkingPass()
  Address "1" <-- "0..1" Person:lives at
  class Student{
    +int studentNumber
    +int averageMark
    +isEligibleToEnrol()
    +getSeminarsTaken()
  }
  class Professor{
    +int salary
  }
  class Address{
    +String street
    +String city
    +String state
    +int postalCode
    +String country
    -validate()
    +outputAsLabel()  
  }
```

#### 实体关系图(E-R图, Entity-Relationship Diagrams)

实体关系图由实体类型组成，并描述实体之间的关系，常用于特定领域的知识建模。

```` markdown title="E-R图"
``` mermaid
erDiagram
  CUSTOMER ||--o{ ORDER : places
  ORDER ||--|{ LINE-ITEM : contains
  LINE-ITEM {
    string name
    int pricePerUnit
  }
  CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```
````

``` mermaid
erDiagram
  CUSTOMER ||--o{ ORDER : places
  ORDER ||--|{ LINE-ITEM : contains
  LINE-ITEM {
    string name
    int pricePerUnit
  }
  CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```

#### 其他类型的图表

除了上述类型，Mermaid.js 还支持饼图、甘特图、用户旅程、Git 图及需求图。然而，Material for MkDocs 对这些图表的支持有限，尤其是在移动端的表现不佳，因此不建议使用这些图表。
另外，虽然 Mermaid.js 的所有功能应开箱即用，但 Material for MkDocs 当前仅为流程图、序列图、类图、状态图和实体关系图调整了字体和颜色。
