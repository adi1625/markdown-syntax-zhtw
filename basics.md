Markdown语法简版
================

这页是个快速入门，它提供了一些范例来让你很快的学会它；

[语法说明][s] 页提供了完整详细的文件，说明每项功能；

每个范例都有提供输出的 预览 结果 及其 html 代码。

想试写MarkDown的话， [Dingus][d] 是一个网页应用程式，让你可以把你的 Markdown 文件转成 XHTML。

**Note:** 这份文件本身也是用 Markdown 写的，你也可以看看 [它的源码][src]

  [s]: https://github.com/adi1625/markdown-syntax-zhtw/blob/master/syntax.md  "Markdown Syntax"
  [d]: http://daringfireball.net/projects/markdown/dingus  "Markdown Dingus"
  [src]: https://github.com/adi1625/markdown-syntax-zhtw/blob/master/basics.md

## 段落、标题、区块代码 ##
一个段落是由一个以上的连接的行句组成，而一个以上的空行则会切分出不同的段落（空行的定义是显示上看起来像是空行，就被视为空行，例如有一行只有空白和 tab，那该行也会被视为空行），一般的段落不需要用空白或断行缩排。

Markdown 支援两种标题的语法，Setext 和 atx 形式。Setext 形式是用底线的形式，利用 `=` （最高阶标题）和 `-` （第二阶标题），Atx 形式在行首插入 1 到 6 个 `#` ，对应到标题 1 到 6 阶。

区块引言则使用 email 形式的 '`>`' 尖括号。

Markdown:

    A First Level Header
    ====================
    
    A Second Level Header
    ---------------------
  
    Now is the time for all good men to come to
    the aid of their country. This is just a
    regular paragraph.
  
    The quick brown fox jumped over the lazy
    dog's back.
    
    ### Header 3
  
    > This is a blockquote.
    > 
    > This is the second paragraph in the blockquote.
    >
    > ## This is an H2 in a blockquote

输出：

A First Level Header
====================

A Second Level Header
---------------------

Now is the time for all good men to come to
the aid of their country. This is just a
regular paragraph.

The quick brown fox jumped over the lazy
dog's back.

### Header 3

> This is a blockquote.
> 
> This is the second paragraph in the blockquote.
>
> ## This is an H2 in a blockquote
  
其页面代码为:

```html
<h1>A First Level Header</h1>

<h2>A Second Level Header</h2>

<p>Now is the time for all good men to come to
the aid of their country. This is just a
regular paragraph.</p>

<p>The quick brown fox jumped over the lazy
dog's back.</p>

<h3>Header 3</h3>

<blockquote>
    <p>This is a blockquote.</p>
    
    <p>This is the second paragraph in the blockquote.</p>
    
    <h2>This is an H2 in a blockquote</h2>
</blockquote>
```


### 修辞和强调 ###

Markdown 使用星号和底线来标记需要强调的区段。

Markdown:

    Some of these words *are emphasized*.
    Some of these words _are emphasized also_.
    
    Use two asterisks for **strong emphasis**.
    Or, if you prefer, __use two underscores instead__.

输出:

Some of these words *are emphasized*.
Some of these words _are emphasized also_.

Use two asterisks for **strong emphasis**.
Or, if you prefer, __use two underscores instead__.

其代码为:

```html
<p>Some of these words <em>are emphasized</em>.
Some of these words <em>are emphasized also</em>.</p>

<p>Use two asterisks for <strong>strong emphasis</strong>.
Or, if you prefer, <strong>use two underscores instead</strong>.</p>
```

## 列表 ##

无序列表使用星号、加号和减号来做为列表的项目标记，这些符号是都可以使用的，使用星号：

    *   Candy.
    *   Gum.
    *   Booze.

加号：

    +   Candy.
    +   Gum.
    +   Booze.

和减号

    -   Candy.
    -   Gum.
    -   Booze.

都会输出：

*   Candy.
*   Gum.
*   Booze.

其代码为:

```html
<ul>
<li>Candy.</li>
<li>Gum.</li>
<li>Booze.</li>
</ul>
```

有序的列表则是使用一般的数字接着一个英文句点作为项目标记：

    1.  Red
    2.  Green
    3.  Blue

输出：

1.  Red
2.  Green
3.  Blue

其代码为:

```html
<ol>
<li>Red</li>
<li>Green</li>
<li>Blue</li>
</ol>
```

如果你在项目之间插入空行，那项目的内容会备用 `<p>` 包起来，你也可以在一个项目内放上多个段落，只要在它前面缩排 4 个空白或 1 个 tab 。

    *   A list item.
    
        With multiple paragraphs.

    *   Another item in the list.

输出：

*   A list item.

    With multiple paragraphs.

*   Another item in the list.

其代码为:

```html
<ul>
<li><p>A list item.</p>
<p>With multiple paragraphs.</p></li>
<li><p>Another item in the list.</p></li>
</ul>
```

### 链接 ###

Markdown 支援两种形式的链接语法： *行内* 和 *参考* 两种形式，两种都是使用方括号来把文字转成链接。

行内形式形式是直接在后面用括号直接接上链接：

    This is an [example link](http://example.com/).

输出：

This is an [example link](http://example.com/).

其代码为:

```html
<p>This is an <a href="http://example.com/">example link</a>.</p>
```

你也可以选择性的加上 title 属性：

    This is an [example link](http://example.com/ "With a Title").

输出：

This is an [example link](http://example.com/ "With a Title").

其代码为:

```html
<p>This is an <a href="http://example.com/" title="With a Title">
example link</a>.</p>
```

参考形式的链接让你可以为链接定一个名称，之后你可以在文件的其他地方定义该链接的内容：

    I get 10 times more traffic from [Google][1] than from
    [Yahoo][2] or [MSN][3].

    [1]: http://google.com/        "Google"
    [2]: http://search.yahoo.com/  "Yahoo Search"
    [3]: http://search.msn.com/    "MSN Search"

输出：

I get 10 times more traffic from [Google][1] than from
[Yahoo][2] or [MSN][3].

[1]: http://google.com/        "Google"
[2]: http://search.yahoo.com/  "Yahoo Search"
[3]: http://search.msn.com/    "MSN Search"

其代码为:

```html
<p>I get 10 times more traffic from <a href="http://google.com/"
title="Google">Google</a> than from <a href="http://search.yahoo.com/"
title="Yahoo Search">Yahoo</a> or <a href="http://search.msn.com/"
title="MSN Search">MSN</a>.</p>
```

title 属性是选择性的，链接名称可以用字母、数字和空格，但是不分大小写：

    I start my morning with a cup of coffee and
    [The New York Times][NY Times].

    [ny times]: http://www.nytimes.com/

输出：

I start my morning with a cup of coffee and
[The New York Times][NY Times].

[ny times]: http://www.nytimes.com/

其代码为:

```html
<p>I start my morning with a cup of coffee and
<a href="http://www.nytimes.com/">The New York Times</a>.</p>
```


### 图片 ###

图片的语法和链接很像。

行内形式（title 是选择性的）：

    ![alt text](/path/to/img.jpg "Title")

参考形式：

    ![alt text][id]

    [id]: /path/to/img.jpg "Title"

上面两种方法都会输出：

![alt text](/path/to/img.jpg "Title")

其代码为:

```html
<img src="/path/to/img.jpg" alt="alt text" title="Title" />
```

### 代码 ###
    
在一般的段落文字中，你可以使用反引号 `` ` `` 来标记代码区段，区段内的 `&`、`<` 和 `>` 都会被自动的转换成 HTML 实体，这项特性让你可以很容易的在代码区段内插入 HTML 码：

    I strongly recommend against using any `<blink>` tags.

    I wish SmartyPants used named entities like `&mdash;`
    instead of decimal-encoded entites like `&#8212;`.

输出：

I strongly recommend against using any `<blink>` tags.

I wish SmartyPants used named entities like `&mdash;`
instead of decimal-encoded entites like `&#8212;`.

其代码为:

```html
<p>I strongly recommend against using any
<code>&lt;blink&gt;</code> tags.</p>

<p>I wish SmartyPants used named entities like
<code>&amp;mdash;</code> instead of decimal-encoded
entites like <code>&amp;#8212;</code>.</p>
```

如果要建立一个已经格式化好的代码区块，只要每行都缩排 4 个空格或是一个 tab 就可以了，而 `&`、`<` 和 `>` 也一样会自动转成 HTML 实体。

Markdown:

    If you want your page to validate under XHTML 1.0 Strict,
    you've got to put paragraph tags in your blockquotes:

        <blockquote>
            <p>For example.</p>
        </blockquote>

输出：

If you want your page to validate under XHTML 1.0 Strict,
you've got to put paragraph tags in your blockquotes:

    <blockquote>
        <p>For example.</p>
    </blockquote>

其代码为:

```html
<p>If you want your page to validate under XHTML 1.0 Strict,
you've got to put paragraph tags in your blockquotes:</p>

<pre><code>&lt;blockquote&gt;
    &lt;p&gt;For example.&lt;/p&gt;
&lt;/blockquote&gt;
</code></pre>
```

