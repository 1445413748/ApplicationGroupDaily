# CSS基础入门       
## 一、上节课知识复习   
css属性:    
● 加粗，倾斜，下划线 ：
```
1	font-weight:bold;   
2	font-style:italic;      
3	text-decoration:underline;      
```
● 背景颜色、前景色：   
```
1	background-color:red;   
2	color:red;          
```
● class和id的区别
class用于css的，id用于js的。    
1）class页面上可以重复。id页面上唯一，不能重复。        
2）一个标签可以有多个class，用空格隔开。但是id只能有id。       
● 选择器    
说IE6层面兼容的：    标签选择器、id选择器、类选择器、后代、交集选择器、并集选择器、通配符。  
1	p   
2	#box    
3	.spec   
4	div p   
5	div.spec    
6	div,p7	*   
IE7能够兼容的：儿子选择器、下一个兄弟选择器    
1	div>p   
2	h3+p    
IE8能够兼容的： 
```
1	ul li:first-child   
2	ul li:last-child    
```
● css两个性质：     
1） 继承性。有一些属性给祖先元素，所有的后代元素都集成上了。    
2)哪些属性能继承：color、font-、text-、line-
## 二、权重问题深入
**2.1同一个标签，携带了多个类名，有冲突：**
```
1		<p class="spec1 spec2">我是什么颜色？</p>
2		<p class="spec2 spec1">我是什么颜色？</p>
```
和在标签中的挂类名的书序无关，只和css的顺序有关：
```
1			.spec2{
2				color:blue;
3			}
4			.spec1{
5				color:red;
6			}
```
红色的。因为css中red写在后面。  
**2.2 !important标记**
```
1		<style type="text/css">
2			p{
3				color:red !important;
4			}
5			#para1{
6				color:blue;
7			}
8			.spec{
9				color:green;
10			}
11		</style>
```
important是英语里面的“重要的”的意思。我们可以通过语法：k:v !important;
来给一个属性提高权重。这个属性的权重就是无穷大。    
## 三、盒模型
**3.1 盒子中的区域**    
一个盒子中主要的属性就5个：width、height、padding、border、margin。
width是“宽度”的意思，CSS中width指的是内容的宽度，而不是盒子的宽度。
height是“高度”的意思，CSS中height指的是内容的高度，而不是盒子的高度
padding是“内边距”的意思
border是“边框”
margin是“外边距”    
**3.2 border**  
就是边框。边框有三个要素：粗细、线型、颜色。    
颜色如果不写，默认是黑色。另外两个属性不写，显示不出来边框。   
border是一个大综合属性，    
**1**	border:1px solid red;
就是把4个边框，都设置为1px宽度、线型实线、red颜色。   
border属性能够被拆开，有两大种拆开的方式：    
1） 按3要素:border-width、border-style、border-color   
2） 按方向：border-top、border-right、border-bottom、border-left   
按3要素拆开：
1	border-width:10px;   
2	border-style:solid;         
3	border-color:red;   
等价于border:10px solid red;一个border是由三个小属性综合而成：border-width  border-style   border-color。  
## 四、标准文档流
宏观的讲，我们的web页面和photoshop等设计软件有本质的区别：web页面的制作，是个“流”，必须从上而下，像“织毛衣”。而设计软件，想往哪里画个东西，都能画。    
我们要看看标准流有哪些微观现象：    
**1） 空白折叠现象：**  
比如，如果我们想让img标签之间没有空隙，必须紧密连接：
```
	<img src="images/0.jpg" /><img src="images/1.jpg" /><img src="images/2.jpg" />
```         

**2） 高矮不齐，底边对齐：**    
**3） 自动换行，一行写不满，换行写。**    
**4.1 块级元素和行内元素**  
标准文档流等级森严。标签分为两种等级：    
**1）块级元素**   
● 霸占一行，不能与其他任何元素并列  
● 能接受宽、高  
● 如果不设置宽度，那么宽度将默认变为父亲的100%。  
**2） 行内元素**    
● 与其他行内元素并排    
● 不能设置宽、高。默认的宽度，就是文字的宽度。    
    
在HTML中，我们已经将标签分过类，当时分为了：文本级、容器级。
文本级：p、span、a、b、i、u、em 
容器级：div、h系列、li、dt、dd      
CSS的分类和上面的很像，就p不一样：
所有的文本级标签，都是行内元素，除了p，p是个文本级，但是是个块级元素。所有的容器级标签都是块级元素。    
**4.2 块级元素和行内元素的相互转换**   
块级元素可以设置为行内元素:display: inline;     
行内元素可以设置为块级元素:display: block;      
css中一共有三种手段，使一个元素脱离标准文档流：    
1） 浮动    
2） 绝对定位    
3） 固定定位    
## 五、浮动
性质:   
**1 浮动的元素脱标**  
**2 浮动的元素互相贴靠**    
**3 浮动的元素有“字围”效果**

