# CSS基础入门
## 一、行高和字号
**1.1 行高**    
CSS中，所有的行，都有行高。盒模型的padding，绝对不是直接作用在文字上的，而是作用在“行”上的。为了严格保证字在行里面居中, 行高、字号，一般都是偶数。这样，它们的差，就是偶数，就能够被2整除。     
**1.2 单行文本垂直居中**    
需要注意的是，这个小技巧，行高=盒子高。只适用于单行文本垂直居中！！不适用于多行。    
如果想让多行文本垂直居中，需要设置盒子的padding：

**1.3 font属性**    
● 使用font属性，能够将字号、行高、字体，能够一起设置。
1	font: 14px/24px “宋体”; 
等价于三行语句：    
```
1	font-size:14px; 
2	line-height:24px;   
3	font-family:"宋体"; 
```
font-family就是“字体”。family是“家庭”、“伐木累”的意思   
● 网页中不是所有字体都能用哦，因为这个字体要看用户的电脑里面装没装，比如你设置：
```
1	font-family: "华文彩云";
```
如果用户电脑里面没有这个字体，那么就会变成宋体。页面中，中文我们只使用： 微软雅黑、宋体、黑体。如果页面中，需要其他的字体，那么需要切图。
英语：Arial 、 Times New Roman.     
font属性能够将font-size、line-height、font-family合三为一：
```
1	font:12px/30px  "Times New Roman","Microsoft YaHei","SimSun";  
```
 行高可以用百分比，表示字号的百分之多少。一般来说，都是大于100%的，因为行高一定要大于字号。
 ```
1	font:12px/200% “宋体”
//等价于  
1	font:12px/24px “宋体”;
``` 
## 二、超级链接的美化
### 超级链接就是a标签
**2.1 伪类**    
也就是说，同一个标签，根据用户的某种状态不同，有不同的样式。这就叫做“伪类”。类就是工程师加的，比如div属于box类，很明确，就是属于box类。但是a属于什么类？不明确。因为要看用户有没有点击、有没有触碰。所以，就叫做“伪类”。伪类用冒号来表示。        
a标签有4种伪类：    
```
1			a:link{
2				color:red;
3			}
4			a:visited{
5				color:orange;
6			}
7			a:hover{
8				color:green;
9			}
10			a:active{
11				color:black;
12			}
```
**:link**表示用户没有点击过这个链接的样式。 是英语“链接”的意思。   
**:visited**表示用户访问过了这个链接的样式。 是英语“访问过的”的意思。   
**:hover**表示用户鼠标悬停的时候链接的样式。 是英语“悬停”的意思。   
**:active**	表示用户用鼠标点击这个链接，但是不松手，此刻的样式,是英语“激活”的意思。  
**2.2 超级链接的美化**  
a标签在使用的时候，非常的难。因为不仅仅要控制a这个盒子，也要控制它的伪类。    
我们一定要将a标签写在前面，:link、:visited、:hover、:active这些伪类写在后面。  
a标签中，描述盒子；     伪类中描述文字的样式、背景。
```
1			.nav ul li a{
2				display: block;
3				width: 120px;
4				height: 40px;
5			}
6			.nav ul li a:link ,.nav ul li a:visited{
7				text-decoration: none;
8				background-color: yellowgreen;
9				color:white;
10			}
11			.nav ul li a:hover{
12				background-color: purple;
13				font-weight: bold;
14				color:yellow;
15			}
``` 
## 三、background系列属性
**3.1 background-color属性**    
背景颜色属性。  
css2.1中，颜色的表示方法有哪些？一共有三种：单词、rgb表示法、十六进制表示法    
**用英语单词来表示**    
能够用英语单词来表述的颜色，都是简单颜色。
红色：
1	background-color: red;   

**用rgb方法来表示** 
红色：
```
1	background-color: rgb(255,0,0);
```
rgb表示三原色“红”red、“绿”green、“蓝”blue。光学显示器，每个像素都是由三原色的发光原件组成的，靠明亮度不同调成不同的颜色的。
用逗号隔开，r、g、b的值，每个值的取值范围0~255，一共256个值。
如果此项的值，是255，那么就说明是纯色：    
**十六进制表示法**  
红色：
```
background-color: #ff0000;
```
所有用#开头的值，都是16进制的。  
**3.2 background-image**    
用于给盒子加上背景图片：
```
1	background-image:url(images/wuyifan.jpg);
```
url()表示网址，uniform resouces locator 同意资源定位符
images/wuyifan.jpg 就是相对路径。     
**3.3 background-repeat属性**   
设置背景图是否重复的，重复方式的。
repeat表示“重复”。  
也就是说，background-repeat属性，有三种值：    
```
1	background-repeat:no-repeat;   //不重复
2	background-repeat:repeat-x;    //横向重复
3	background-repeat:repeat-y;    //纵向重复
``` 
**3.4 background-position属性**   
position就是“位置”的意思。background-position就是背景定位属性。    
```
1	background-position:向右移动量 向下移动量;
``` 
**3.5 background-attachment**
背景是否固定。
```
1	background-attachment:fixed;
```
背景就会被固定住，不会被滚动条滚走。

**3.6 background综合属性**  
background属性和border一样，是一个综合属性：  
```
1	background:red url(1.jpg) no-repeat 100px 100px fixed;
```
等价于：
```
1	background-color:red;
2	background-image:url(1.jpg);
3	background-repeat:no-repeat;
4	background-position:100px 100px;
5	background-attachment:fixed;
``` 





