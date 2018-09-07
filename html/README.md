
# HTML编码规范


## 代码风格


### 缩进与换行

 * 使用tab 4宽表示缩进。
 * 每行不得超过120个字符。


### 命名

 * class` 必须单词全字母小写，单词间以 `-` 分隔。
 * `class` 必须代表相应模块或部件的内容或功能，不得以样式信息进行命名。

```html
<!-- good -->
<div class="sidebar"></div>

<!-- bad -->
<div class="left"></div>
```

 * 元素 `id` 必须保证页面唯一。
 * 元素 `id` 建议单词`J_`开头，单词采用小驼峰命名。同项目必须保持风格一致。
 * `id`、`class`命名，在避免冲突并描述清楚的前提下尽可能短。

```html
<!-- good -->
<div id="J_navBar"></div>
<!-- bad -->
<div id="navigation"></div>

<!-- good -->
<p class="comment"></p>
<!-- bad -->
<p class="com"></p>

<!-- good -->
<span class="author"></span>
<!-- bad -->
<span class="red"></span>
```

 * 使用id或者特定的class前缀作为 `hook 脚本`。

```html
<!-- good -->
<div id="J_hook"></div>
<div class="hook"></div>

<!-- bad -->
<div id="hook"></div>
<div class="hook"></div>
```
 * 同一页面，应避免使用相同的 `name` 与 `id`。


### 标签


 * 标签名必须使用小写字母。

```html
<!-- good -->
<p>Hello StyleGuide!</p>

<!-- bad -->
<P>Hello StyleGuide!</P>
```

 * 对于无需自闭合的标签，不允许自闭合，常见无需自闭合标签有input、br、img、hr等

```html
<!-- good -->
<input type="text" name="title">

<!-- bad -->
<input type="text" name="title" />
```

 *  `HTML5`中规定允许省略的闭合标签，不允许省略闭合标签。

```html
<!-- good -->
<ul>
    <li>first</li>
    <li>second</li>
</ul>

<!-- bad -->
<ul>
    <li>first
    <li>second
</ul>
```


 * 标签使用必须符合标签嵌套规则。如 div 不得置于 p 中，tbody 必须置于 table 中。详细的标签嵌套规则参见[HTML DTD](http://www.cs.tut.fi/~jkorpela/html5.dtd)中的 `Elements` 定义部分。


 * `HTML` 标签的使用应该遵循标签的语义。

- p - 段落
- h1,h2,h3,h4,h5,h6 - 层级标题
- strong,em - 强调
- ins - 插入
- del - 删除
- abbr - 缩写
- code - 代码标识
- cite - 引述来源作品的标题
- q - 引用
- blockquote - 一段或长篇引用
- ul - 无序列表
- ol - 有序列表
- dl,dt,dd - 定义列表

```html
<!-- good -->
<p>Esprima serves as an important <strong>building block</strong> for some JavaScript language tools.</p>

<!-- bad -->
<div>Esprima serves as an important <span class="strong">building block</span> for some JavaScript language tools.</div>
```


 * 标签的使用应尽量简洁，减少不必要的标签。

```html
<!-- good -->
<img class="avatar" src="image.png">

<!-- bad -->
<span class="avatar">
    <img src="image.png">
</span>
```



### 属性


 * 属性名必须使用小写字母。

```html
<!-- good -->
<table cellspacing="0">...</table>

<!-- bad -->
<table cellSpacing="0">...</table>
```


 * 属性值必须用双引号包围。

```html
<!-- good -->
<script src="esl.js"></script>

<!-- bad -->
<script src='esl.js'></script>
<script src=esl.js></script>
```

 * 布尔类型的属性，建议不添加属性值。

```html
<input type="text" disabled>
<input type="checkbox" value="1" checked>
```


 * 自定义属性建议以 `xxx-` 为前缀，推荐使用 `data-`。


## 通用


### DOCTYPE


 * 使用 `HTML5` 的 `doctype` 来启用标准模式，建议使用大写的 `DOCTYPE`。

```html
<!DOCTYPE html>
```

 * 启用 IE Edge 模式。

```html
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

 * 在 `html` 标签上设置正确的 lang 属性。

```html
<html lang="zh-CN">
```


### 编码


 * 页面必须使用精简形式，明确指定字符编码。指定字符编码的 `meta` 必须是 `head` 的第一个直接子元素。

```html
<html>
    <head>
        <meta charset="UTF-8">
        ......
    </head>
    <body>
        ......
    </body>
</html>
```

 *  `HTML` 文件使用无 `BOM` 的 `UTF-8` 编码。


### CSS和JavaScript引入


 * 引入 `CSS` 时必须指明`rel="stylesheet"`。

```html
<link rel="stylesheet" src="page.css">
```


 * 引入 `CSS` 和 `JavaScript` 时无须指明 `type` 属性。

 * 在 `head` 中引入页面需要的所有`CSS`资源。

 * `JavaScript`应当放在页面末尾或采用异步加载。

 * 引用外部资源的`URL`协议部分与页面相同，省略协议前缀。


## head


### title

 * 页面必须包含 `title` 标签声明标题。
 * `title` 必须作为`head`的直接子元素，并紧随 `charset` 声明之后。（title 中如果包含 ascii 之外的字符，浏览器需要知道字符编码类型才能进行解码，否则可能导致乱码。）


```html
<head>
    <meta charset="UTF-8">
    <title>页面标题</title>
</head>
```

### favicon

 * 保证 `favicon` 可访问。（在 Web Server根目录放置 favicon.ico 文件或者使用 link 指定 favicon。）

```html
<link rel="shortcut icon" href="path/to/favicon.ico">
```

### viewport

 * 移动设备需指定页面的 `viewport`。


## 图片

 *  禁止`img`的`src`取值为空。延迟加载的图片也要增加默认的`src`。（src取值为空，会导致部分浏览器重新加载一次当前页面，参考：<https://developer.yahoo.com/performance/rules.html#emptysrc>） 
 *  避免为 `img` 添加不必要的 `title` 属性。
 *  为重要图片添加 `alt` 属性。
 * 建议 添加 `width` 和 `height` 属性，以避免页面抖动。


## 表单


### 控件标题

 * 有文本标题的控件必须使用 `label` 标签将其与其标题相关联。

```html
<label><input type="checkbox" name="confirm" value="on"> 我已确认上述条款</label>

<label for="username">用户名：</label> <input type="textbox" name="username" id="username">
```


### 按钮

 * 使用 `button` 元素时必须指明 `type` 属性值。（button 元素的默认 type 为 submit）
 * IE默认 `type` 是 `"button"` , 其他浏览器（包括 `W3C` 规范）默认 `type` 是 `"submit"`

```html
<button type="submit">提交</button>
<button type="button">取消</button>
```