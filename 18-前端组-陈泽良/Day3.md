# CSS基础入门   
## 一、上节课知识复习
● HTML骨架结构，抽象的：
```
	<!DOCTYPE …… >
	<html>
		<head>
			网页的配置
		</head>
		<body>
			给用户看的
		</body>
	</html>
``` 
● DTD：文档类型声明Doc Type Declaration。一共有7种DTD，3种HTML4.01的，3种XHTML1.0的，1种HTML5.
三个小种： strict（更为严格，不能用u、b、i标签）、transitional（不怎么严格）、frameset
XHTML总体上要比HTML严格，比如必须是小写字母标签等等。

● 字符集Charset.
1	<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
UTF-8	： 字符全，每一个汉字3个字节，所以文件尺寸大。
gb2312(gbk) ： 字符少，每一个汉字2个字节，所以文件尺寸小。

● 关键词、页面描述
```
<meta name="Keywords" content="词" />
<meta name="Description" content="页面描述" />

● title标签就是页面标题

● HTML就是负责描述语义的，所以就是用标签对儿的形式来给文本增加语义。
h1~h6  标题
p 段落
p标签要注意的是，里面只能放文本、图片、表单元素

● img图片
完整语法，两个属性src和alt！
src：  source资源，    alt ： alternate 替代物
<img src="路径" alt="替代文本，当图片不能显示的时候，显示这里的文字" />
```
图片里面的路径，相对路径，从html出发，找到图片。 
```
<img src="" alt="" />
<img src="../../0.png" alt="" />    
```
● a标签，超级链接
a是英语anchor锚的意思。
a标签常用的就是三个属性：
页面内的锚点，用name属性或者id属性
<a name="grjj"></a>
<a id="grjj"></a>
如果想跳转到某个锚点：
```
<a href="#grjj"></a>
```
## 二、列表
列表有3种   
**1,无序列表**   
无序列表，用来表示一个列表的语义，并且每个项目和每个项目之间，是不分先后的。
ul就是英语unordered list，“无序列表”的意思。
li 就是英语list item ， “列表项”的意思。    
**2,有序列表**  
ordered list  有序列表，用ol表示,   
**3,定义列表**  
定义列表也是一个组标签，不过比较复杂，出现了三个标签：  dl表示definition list 定义列表  
dt表示definition title	定义标题    
dd表示definition description     定义表述词儿dt、dd只能在dl里面；dl里面只能有dt、dd. 

## 三、div和span
div和span是非常重要的标签，div的语义是division“分割”； span的语义就是span“范围、跨度”。这两个东西，都是最最重要的“盒子”。  div在浏览器中，默认是不会增加任何的效果改变的，但是语义变了，div中的所有元素是一个小区域。
div标签是一个容器级标签，里面什么都能放，甚至可以放div自己.
span也是表达“小区域、小跨度”的标签，但是是一个“文本级”的标签。就是说，span里面只能放置文字、图片、表单元素。span里面不能放p、h、ul、dl、ol、div。span里面是放置小元素的，div里面放置大东西的：
## 四、表单
 表单就是收集用户信息的，就是让用户填写的、选择的。form是英语表单的意思。form标签里面有action属性和method属性：action属性就是表示，表单将提交到哪里。 method属性表示用什么HTTP方法提交，有get、post两种。  
 **1,文本框**     
 ```
 <input type="text" />
 ```    
 input表示“输入”，指的是这是一个“输入小部件”，
type表示“类型”，
text表示“文本”，指的是类型是一个文本框的输入小部件。
这是一个自封闭标签，自此自封闭标签有：
```
1	<meta name=”Keywords” content=”” />
2	<img src=”” alt=”” />
3	<input type=”text” />
``` 
**2,密码框**
```
<input type="password" />
``` 
**3,单选按钮**  
单选按钮，天生是不能互斥的，如果想互斥，必须要有相同的name属性。name就是“名字”。    
```
1	<input type="radio" name="xingbie" /> 男
2	<input type="radio" name="xingbie" /> 女
默认被选择，就应该书写checked=”checked”
3	<input type="radio" name="sex" checked="checked">
``` 
**4,复选框**    
也是input标签，type是checkbox。 
```
1	<p>
2		请选择你的爱好：
3		<input type="checkbox" name="aihao"/> 睡觉
4		<input type="checkbox" name="aihao"/> 吃饭
5		<input type="checkbox" name="aihao"/> 足球
6		<input type="checkbox" name="aihao"/> 篮球
7		<input type="checkbox" name="aihao"/> 乒乓球
8		<input type="checkbox" name="aihao"/> 打豆豆
9	</p>
```
复选框，最好也是有相同的name（虽然他不需要互斥，但是也要有相同的name）

# PLUS  
# 回文词
题目:输入一个字符串，判断它是否为回文串以及镜像串。输入字符串保证不含数字0。所谓 回文串，就是反转以后和原串相同，如abba和madam。所谓镜像串，就是左右镜像之后和原串相同，如2S和3AIAE。
注意，并不是每个字符在镜像之后都能得到一个合法字符。在本题中，每个字符的镜像如图所示（空白项表示该字符镜像后不能得到一个合法字符）。  
<img src="https://img2018.cnblogs.com/blog/1274972/201902/1274972-20190208093824720-689934345.png">    
输入的每行包含一个字符串（保证只有上述字符。不含空白字符），判断它是否为回文 串和镜像串（共4种组合）。每组数据之后输出一个空行。

样例输入：

NOTAPALINDROME

ISAPALINILAPASI

2A3MEAS

ATOYOTA

样例输出：

NOTAPALINDROME -- is not a palindrome.

ISAPALINILAPASI -- is a regular palindrome.

2A3MEAS -- is a mirrored string.

ATOYOTA -- is a mirrored palindrome.    

分析:本题关键在于判断字符串是否为镜像串,judge函数的作用是返回字母或数字的镜像,另外,这里还用到了常量数组s2大大节省了代码量.
```
#include<iostream>
#include<cstdio>
#include<cstring>
#include<cctype>
using namespace std;
const char* s1 = "A   3  HIL JM O   2TUVWXY51SE Z  8 ";
const char* s2[]= {"not a palindrome","a regular palindrome","a mirrored string","a mirrored palindrome"};
char judge(char ch);
int main()
{
	char s[30];
	while(cin>>s)
	{
		int len=strlen(s);
		int m=1,n=1;
		for(int i=0;i<(len+1)/2;i++)
		{
			if(s[i]!=s[len-1-i])m=0;
			if(judge(s[i])!=s[len-1-i])n=0;
		}
		cout<<s<<" -- is "<<s2[n*2+m]<<".\n\n";
	}
	return 0;
}
char judge(char ch)
{
	if(isalpha(ch))
	{
		return s1[ch- 'A'];
	}
	return s1[ch-'0'+25];
}
```
