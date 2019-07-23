# HTML5+CSS3
## 常用元素
**section元素**                     
section元素用来定义文章中的章节（通常应该有标题和段落内容）可以用来定义文档特定内容的区块.
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>section元素的使用方法</title>
    </head>
    <body>
        <section>
            <h1>这是一个section元素</h1>
            <p>这是一个内容区域</p>
            <section>
                <h2>A</h2>
                <p>A的内容</p>
            </section>
            <section>
                <h2>B</h2>
                <p>B的内容</p>
            </section>
        </section>
    </body>
</html>
```
**aside元素**   
aside元素表示一个页面的一部分， 它的内容跟这个页面的其它内容的关联性不强，或者是没有关联，单独存在。aside元素通常显示成侧边栏(sidebar)或一些插入补充内容。通常用来在侧边栏显示一些定义，比如目录、索引、术语表等；也可以用来显示相关的广告宣传，作者的介绍，Web应用，相关链接，当前页内容简介等。
aside元素使用注意事项： 
不要使用aside元素标记括号中的文字，因为这种类型的文本被认为是主内容的一部分。  
使用例子：
```
    <article>  
      <p>  
        The Disney movie <em>The Little Mermaid</em> was   
        first released to theatres in 1989.   
      </p>  
      <aside>  
        The movie earned $87 million during its initial release.   
      </aside>  
      <p>  
        More info about the movie...   
      </p>  
    </article>  
<article>
```
**article元素**     
Article元素(article)故名思议，可以表示论坛帖子、杂志或新闻文章、博客、用户提交的评论、交互式组件，或者其他独立的内容项目。它的主要语义为表示自己是一个独立的内容结构。每一个article元素内部结构都应该是相似的，比如都应该包含一个头标题(h1-h6元素)等。   
article元素用法：   
当article元素嵌套使用时，则该元素代表与父元素有关的文章。例如，代表博客评论的article元素可嵌套在代表博客文章的article元素中。
article元素中文章作者的信息可通过address元素表示，但是不适用于嵌套的article元素。
article元素中文章的发布日期和时间可通过time元素的pubdate属性表示。  
代码样例:
```
<article class="film_review">  
  <header>  
    <h2>侏罗纪公园</h2>  
  </header>  
  <section class="main_review">  
    <p>Dinos were great!</p>  
  </section>  
  <section class="user_reviews">  
    <article class="user_review">  
      <p>Way too scary for me.</p>  
      <footer>  
        <p>  
          Posted on <time datetime="2015-05-16 19:00">May 16</time> by Lisa.   
        </p>  
      </footer>  
    </article>  
```
**nav元素** 
Nav元素可以用作页面导航的链接组，在导航链接组里面有很多的链接，点击每个链接可以链接到其他页面或者当前页面的其他部分，并不是所有的链接组都要被放在nav元素里面，我们只需要把最主要的、基本的、重要的放在nav元素里面即可。  
比如说页脚底部如果有个版权申明，我们就不建议使用nav元素，而是使用footer元素是最合适的。一个页面中我们可用多个nav元素作为整体或者不同部分的导航.    
nav元素的用法:
```
<body>
<h1>nav的使用方法</h1>
<nav>
<ul>
<li>
<a href=”nav元素.html”>首页</a>
</li>
<li>
<a href=”aside元素.html”>aside</a>
</li>
<li>
<a href=”section元素.html”>section</a>
</li>
</ul>
</nav>
</body>
```
**pubdate元素**   
这是一个可选的,boolean值属性，它可以用到article元素中的time元素上，意思是time元素代表了文章（article元素的内容）或者整个网页的发布日期    
```
<!DOCTYPE html>
<meta charset="utf-8">
<article>
	<header>
		<h1>关于<time datetime="2010-10-29">10月29日</time>的舞会的通知</h1>
		<p>发布日期
			<time datetime="2010-10-11" pubdate>2010年10月11日</time>
		</p>
	</header>
	<p>大家好，我是法律系三年级的代表......</p>
</article>
```
**header元素**    
header元素是一种具有引导和导航作用的结构元素，通常用来放置整个页面或页面内的一个内容区块的标题，但也可以包含其他的内容，比如在header里面放置logo图片、搜索表单等等。  
注意：一个页面内并没有限制header的出现次数，也就是说我们可以在同一页面内，不同的内容区块上分别加上一个header元素。
用例:
```
<body>
<header>
<h1>网页标题</h1>
</header>
<article>
<header>
<h1>文章标题</h1>
</header>
<p>文章正文部分</p>
</article>
</body>
```
**hgroup元素**  
hgroup元素是将标题和他的子标题进行分组的元素。hgroup元素一般会把h1-h6的元素进行分组，比如在一个内容区块的标题和他的子标题算是一组。通常情况下，文章只有一个主标题时，是不需要hgroup元素的.             
当我们的同一个区块下面的标题，有主标题和子标题的时候，我们就需要hgroup元素进行包裹.
用例:
```
<article>
<header>
<hgroup>
<h1>文章主标题</h1>
<h2>文章子标题</h2>
</hgroup>
<p><time datetime=”2014-10-08”>2014年10月08日</time></p>
</header>
<p>文章正文</p>
</article>
```