# Math 数学功能

## 配置项

### 可选的库

`MathJax` 和 `KaTeX` 是两个流行的数学公式渲染库，用于在浏览器中显示数学内容。虽然两者提供类似的功能，但它们使用不同的语法并具有不同的配置选项。本章提供了如何将它们与 Material for MkDocs 集成的有关信息。

- MathJax 是一个功能强大且灵活的库，支持多种输入格式（如 LaTeX、MathML、AsciiMath）和输出格式（如 HTML、SVG、MathML）。

- KaTeX 是一个轻量级的库，专注于速度和简单性。它支持 LaTeX 语法的子集，并能够将数学公式渲染为 HTML 或 SVG。

本网页使用 `MathJax` 进行数学公式的渲染。

### 二者对比

在决定使用 MathJax 还是 KaTeX 时，有几个关键的因素需要考虑：

- __速度__：KaTeX 通常比 MathJax 更快。如果您的网站需要快速渲染大量复杂公式，KaTeX 可能是更好的选择。

- __语法支持__：MathJax 支持更广泛的 LaTeX 命令，并且可以处理多种数学标记语言（如 AsciiMath 和 MathML）。如果您需要高级的 LaTeX 功能，MathJax 或许更合适。

- __输出格式__：两者都支持 HTML 和 SVG 输出。然而，MathJax 还提供 MathML 输出，这对于可访问性很重要，因为屏幕阅读器可以读取 MathML。

- __可配置性__：MathJax 提供更多的配置选项，使用户能够更精确地控制其行为。如果您有特定的渲染需求，MathJax 可能是更灵活的选择。

- __浏览器支持__：虽然两个库在现代浏览器中都表现良好，MathJax 对旧版浏览器的兼容性更好。如果您的受众使用各种浏览器（包括旧版），MathJax 可能更安全。

总结：KaTeX 以速度和简洁著称，而 MathJax 提供更多功能和更好的兼容性，但速度较慢。选择使用哪一个主要取决于您的具体需求和限制。

## 使用方法

### 块级元素

块级数学公式必须用 `#!latex $$...$$` 或 `#!latex \[\]` 包裹，并占用单独的行。

``` latex title="块级数学公式"
$$
\cos x=\sum_{k=0}^{\infty}\frac{(-1)^k}{(2k)!}x^{2k}
$$
```

$$
\cos x=\sum_{k=0}^{\infty}\frac{(-1)^k}{(2k)!}x^{2k}
$$

### 内联行内元素

行内数学公式必须用 `#!latex $...$` 或 `#!latex \(...\)` 包裹。

``` latex title="行内数学公式"
设 $n$ 是偶数, 则 $\exists \in \mathbb{Z}$, 使得 $n = 2k$. 反之, 若 $\exists k \in \mathbb{Z}$, 使得 $n = 2k$, 则 $n$ 为偶数.
```

设 $n$ 是偶数, 则 $\exists k \in \mathbb{Z}$, 使得 $n = 2k$. 反之, 若 $\exists k \in \mathbb{Z}$, 使得 $n = 2k$, 则 $n$ 为偶数.
