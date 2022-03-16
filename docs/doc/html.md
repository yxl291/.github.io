>#### src 和 href 的区别

src 和 href 都是用来引用外部的资源，它们区别如下：

- src：表示对资源的引用，它指向的内容会嵌入到当前标签所在的位置。src 资源时会将其指向的资源下载并应⽤到⽂档内，如在请求 js 脚本，img 图⽚和 frame 等元素。当浏览器解析到该元素时，会暂停其他资源的下载和处理，知道将该资源加载、编译、执⾏完毕，所以⼀般 js 脚本会放在底部⽽不是头部。

- href：表示超文本引用，它指向一些网络资源，建立和当前元素或本文档的链接关系。当浏览器识别到它他指向的⽂件时，就会并⾏下载资源，不会停⽌对当前⽂档的处理。 常用在 a、link 等标签上。

>#### 对 HTML 语义化的理解

语义化是指根据内容的结构化（内容语义化），选择合适的标签（代码语义化）。通俗来讲就是用正确的标签做正确的事情。

语义化的优点主要有以下两点：

- 对于机器友好，带有语义的文字表现力丰富，更适合搜索引擎的爬虫爬取有效信息，利于 SEO。除此之外，语义类还支持读屏软件，根据文章可以自动生成目录
- 对开发者友好，使用语义类标签增强了可读性，结构更加清晰，开发者也能清晰的看出网页的结构，便于团队的开发与维护。 常见的语义化标签：

```
<header></header>头部

<nav></nav>导航栏

<section></section>区块（有语义化的div）

<main></main>主要区域

<artical></artical>主要内容

<aside></aside>侧边栏

<footer></footer>底部

```

>#### DOCTYPE(⽂档类型) 的作⽤

DOCTYPE是HTML5中一种标准通用标记语言的文档类型声明，它的目的是告诉浏览器（解析器）应该以什么样（html或xhtml）的文档类型定义来解析文档，不同的渲染模式会影响到浏览器对于 CSS 代码甚⾄ JavaScript 脚本的解析。它必须声明在HTML⽂档的第⼀⾏。

浏览器渲染页面的两种模式（可通过document.compatMode获取）：

- CSS1Compat：标准模式（Strick mode），默认模式，浏览器使用W3C的标准解析渲染页面。在标准模式中，浏览器以其支持的最高标准呈现页面。

- BackCompat：怪异模式(混杂模式)(Quick mode )，浏览器使用自己的怪异模式解析渲染页面。在怪异模式中，页面以一种比较宽松的向后兼容的方式显示。

>#### display的block、inline和inline-block的区别

- block:会独占一行，多个元素会另起一行，可以width、height、margin和padding属性。

- inline:元素不会独占一行，设置width、height属性无效。但可以设置水平方向的margin和padding属性，不可以设置垂直方向的padding和margin。

- inline-block:将对象设置为inline对象，但对象的内容作为block对象呈现，之后的内联对象会被排列在同一行内。

>#### script标签中defer和async的区别

如果没有defer或async属性，浏览器会立即加载并执行相应的脚本。也就是说在渲染script标签之后的文档之前，不等待后续加载的文档元素，读到就开始加载和执行，这样就会阻塞后续文档的加载。
defer 和 async属性都是去异步加载外部的JS脚本文件，它们都不会阻塞页面的解析，其区别如下：

- 多个带async属性的标签，不能保证加载的顺序；多个带defer属性的标签，按照加载顺序执行。

- async属性，表示后续文档的加载和渲染与js脚本的加载和执行是并行进行的，即异步执行；有了defer属性，加载后续文档的过程和js脚本的加载(此时仅加载不执行)是并行进行的(异步)，js脚本的执行需要等到文档所有元素解析完成之后，DOMContentLoaded事件触发执行之前。

>#### 常⽤的meta标签有哪些

- charset，用来描述HTML文档的编码类型
    - `<meta charset="UTF-8" >`

- keywords，页面关键词 
    - `<meta name="keywords" content="关键词" />`

- description，页面描述
    - `<meta name="description" content="想要描述的内容" />`

- refresh，页面重定向和刷新 
    - `<meta http-equiv="refresh" content="0;url=" />`

- viewport，适配移动端，开发人员可以控制视口的大小和比例 
    - `<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">`

>#### HTML5有哪些更新

- 新增语义化标签：nav、header、footer、aside、section、article

- 音频、视频标签：audio、video

- 数据存储：localStorage、sessionStorage

- canvas（画布）、Geolocation（地理定位）、websocket（通信协议）

- input标签新增属性：placeholder、autocomplete、autofocus、required

- history API：go、forward、back、pushstate

>#### 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？

- 行内元素有：`a b span img input select strong`

- 块级元素有：`div ul ol li dl dt dd h1 h2 h3 h4 h5 h6 p`

- 常见的空元素（标签内没有内容的 HTML 标签被称为空元素。空元素是在开始标签中关闭的。）: `<br> <hr> <img> <input> <link> <meta>`

>#### iframe 有哪些优点和缺点？

- **优点**
    - 用来加载速度较慢的内容（如广告）
    - 可以使脚本可以并行下载
    - 可以实现跨子域通信

- **缺点**
    - iframe 会阻塞主页面的 onload 事件
    - 无法被一些搜索引擎索识别
    - 会产生很多页面，不容易管理

>#### 重定向和转发

转发是服务器行为，重定向是客户端行为。

- **转发**
    - 是服务器请求资源,服务器直接访问目标地址的URL,把那个URL的响应内容读取过来,然后把这些内容再发给浏览器.浏览器根本不知道服务器发送的内容从哪里来的,因为这个跳转过程实在服务器实现的，并不是在客户端实现的所以客户端并不知道这个跳转动作，所以它的地址栏还是原来的地址.

- **重定向**
    - 是服务端根据逻辑,发送一个状态码,告诉浏览器重新去请求那个地址.所以地址栏显示的是新的URL.

>#### title和h1的区别 （**SEO**）

- **定义**
    - title:概括网站信息，告诉了搜索引擎和用户该网站的内容主题。
    - h1:文章主题内容，告诉蜘蛛我们网站最主要的内容是什么。（淘宝logo是由h1标签包裹了一个a标签）
- **区别**
    - title显示网页标题；h1显示网页内容；
    - title比h1更重要
- **场景**
    - 网站的logo都是由h1标签包裹（告诉爬虫网站内容内容）

>#### b和strong的区别
- **定义**
    - b:实体标签，用以给文字加粗；
    - strong：逻辑标签，用以加强字符语气；
- **区别**
    - b只用来加粗字体；
    - strong表示标签内字符比较重要；
    （为了符合css3规范，尽量少用b标签，使用strong）
>#### i和em的区别
- **定义**
    - i:实体标签，用以给文字倾斜；
    - em：逻辑标签，用以加强内容；
- **区别**
    - i只用来倾斜字体；
    - em表示标签内字符比较重要，用以强调；
    （i更多用在字体图标，em用以术语上，一些专业名词）
>#### img里面title和alt的区别
- **区别一**
    - title:鼠标移入到图片显示的值；
    - alt:图片无法加载时显示的值；
- **区别二**
    - 在seo的层面上，蜘蛛抓取不到图片的内容，所以前端要在些img标签的时候为了增加seo效果要加入alt属性来描述这张图是什么内容或者关键词；
>#### png、jpg、gif图片解释一下，分别什么时候用？
- **png** 无损压缩，尺寸体积比jpg/jpeg的大，适合小图标；
- **jpg** 采用压缩算法，有一点失真，比png小，适合做中大图片； 
- **gif** 一般做动图； 
- **webp** 同时支持无损和有损压缩，相同质量的图片，webp有更小的体积，兼容性不是很好； 
