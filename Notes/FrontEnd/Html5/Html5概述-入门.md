# Html5学习笔记

## H5概述
`HTML5` 是 HTML 标准的下一个重要版本，用来替代 `HTML 4.01`，`XHTML 1.0` 以及 `XHTML 1.1`。HTML5 也是一种在万维网上构建和呈现内容的标准


### 新特性
`H5`引入了许多新元素和属性帮助我们构建现代化的网站

- **新的语义化元素**： 比如 `<header>`，`<footer>` 和 `<section>`。
- **表单 2.0**： 改进了 HTML Web 表单，为 `<input>` 标签引入了一些新的属性。
- **持久的本地存储**： 为了不通过第三方插件实现。
- **WebSocket**： 用于 Web 应用程序的下一代双向通信技术。
- **服务器推送事件**： HTML5 引入了从 `Web` 服务器到 `Web` 浏览器的事件，也被称作服务器推送事件（SSE）。
- **Canvas**： 支持用 `JavaScript` 以编程的方式进行二维绘图。
- **音频和视频**： 在网页中嵌入音频或视频而无需借助第三方插件。
- **地理定位**： 用户可以选择与我们的网页共享他们的地理位置。
- **微数据**： 允许我们创建 HTML5 之外的自定义词汇表，以及使用自定义语义扩展网页。
- **拖放**： 把同一网页上的条目从一个位置拖放到另一个位置。

### 向后兼容
HTML5 被设计为尽可能的对现有浏览器向后兼容。新特性都是建立在现有特性的基础上，并且允许我们为旧浏览器提供备用内容

## HTML5 语法
`HTML5` **并没有** `XHTML` 中需要小写标签名，属性要带引号，属性必须有一个值以及必须闭合所有空元素的语法规则

---------
`H5`更具灵活性

- 标签名大写
- 属性的双引号**可选**
- 属性值**可选**
- 闭合空元素**可选**

### DOCTYPE
- 使用简单的语法来指定如下形式的 `DOCTYPE`

```html
<!DOCTYPE html>
<!--不区分大小写-->
```

### 字符编码
- 使用简单的语法指定字符编码

```html
<meta charset="UTF-8">
<!--不区分大小写-->
```

### `<script>` 标签
- `HTML5` 移除了所需的额外信息，我们可以使用如下所示的简单语法
```html
<script src="scriptfile.js"></script>
```

### `<link>` 标签

```html
<link rel="stylesheet" href="stylefile.css">
```

### HTML5 元素
- H5元素使用起始标签和结束标签标记
- 标签使用尖括号之间的标签名限定
- 起始标签和结束标签的区别在于后者标签名前面包含一个斜杠
- HTML5 标签名不区分大小写，可以全部大写或者混合使用，
   > - 虽然最常见的约定是**始终使用小写**
- 大多数元素都包含一些内容
  > - **空白元素**:不能包含任意内容
  > - `br`，`hr`，`link` 和 `meta`   

------------------------
> **Notes**  
> [HTML5 标签参考](http://wiki.jikexueyuan.com/project/html5/tags-reference.html)

### HTML5 属性简述
元素可以包含属性（`attributes`）,用来给一个元素设置各种属性（`properties`）

- 有些属性被定义为**全局**的，可以用在任何元素上，
- 而其他的被定义为元素**特有的**
- HTML5 属性不区分大小写，可以全部大写或者混合使用
  > - 尽管最常见的约定是**始终使用小写**

-----------------
> **Notes**  
> [HTML5 属性](http://wiki.jikexueyuan.com/project/html5/attributes.html)

### HTML5 文档
为了得到更好的结构，引入了下面的标签
- `section`： 这个标签表示一个通用的文档或者应用程序节。它可以和 `h1`-`h6` 一起使用来表示文档结构。
- `article`： 这个标签表示文档内容的一个**独立块**，比如博客条目或者报纸上的文章。
- `aside`： 这个标签表示与页面其他部分略微相关的内容块。
- `header`： 这个标签表示一个*节的头部*。
- `footer`： 这个标签表示一个节的脚注，可以包含*作者，版权*等信息。
- `nav`： 这个标签表示用于导航文档的节。
- `dialog`： 这个标签可以用于标记会话。
- `figure`： 这个标签可以用于关联标题和某些嵌入内容，*比如图表和视频*。

> **Demo**

```html
<!DOCTYPE html>
<html>
<head>
   <meta charset="utf-8">
   <title>...</title>
</head>
<body>
  <header>...</header>
  <nav>...</nav>
  <article>
    <section>
      ...
    </section>
  </article>
  <aside>...</aside>
  <footer>...</footer>
</body>
```

## HTML5 事件
- [HTML5 事件列表](http://wiki.jikexueyuan.com/project/html5/events.html)