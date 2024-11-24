# Buttons 按钮

Material for MkDocs 为按钮(包含主要按钮和次要按钮)提供了专门的样式，这些样式可以应用于任意链接、标签(label)或按钮(button)元素。这对于包含的引导用户行动(Call-to-Action)的文档或是登录页等可能特别有用。

## 使用方法

### 添加一个按钮

要将超链接渲染为按钮，只需在超链接后使用 `.md-button` 类选择器。如果特别设置了 primary color 和 accent color，按钮将自动应用选定的主题色。

```Markdown title="按钮示例"
[这是一个按钮](#Buttons-按钮-使用方法){ .md-button }
```

[这是一个按钮](#Buttons-按钮-使用方法){ .md-button }

### 主要按钮(Primary Buttons)

如果你想用选定的 primary color 填充按钮，而非透明的底色填充，那么你就需要用到主要按钮。使用方法见下。

```Markdown title="主要按钮"
[这是一个主要按钮](#Buttons-按钮-使用方法){ .md-button .md-button--primary }
```

[这是一个主要按钮](#Buttons-按钮-使用方法){ .md-button .md-button--primary }

### 带图标的按钮

```Markdown title="带图标的按钮"
[发送 :fontawesome-solid-paper-plane:](#Buttons-按钮-使用方法){ .md-button }
```

[发送 :fontawesome-solid-paper-plane:](#Buttons-按钮-使用方法){ .md-button }
