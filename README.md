# About-Javascript
####record the thing which maybe forgetten
--------------------------------------

--------------------------------------

- **Javascript DOM**

  1.	document.write + "html/css 标签";
  2.	prompt("这里是对话框显示部分","这里是文本框提示部分") = alert + inputtext + cancel +confirm;
  3.	confirm(str) = alert + confirm + cancel;
  4.	window.open("URL","para1","para2");
    - para1:
	    - _blank：在新窗口显示目标网页
	    - _self：在当前窗口显示目标网页
	    - _top：框架网页中在上部窗口中显示目标网页
    - para2:
    - ![github](./1.jpg)	
  5.	e.g.

  	```html
	var a = window.open(…);
	a.close(); // close the window
  	```
  6.	e.g.

  	```html
	<h2 id = "cc">My Beautiful girl</h2>
	js: var c = getElementById("cc");
	c.innerHTML = “the text which we like”;
	```

- **About JQuery**【学自锋利的jQuery】

  1.**第一章 认识jQuery**
  	- $("#foo") is the same as jQuery("#foo")
  	- compare with DOM

  	|compare|DOM|jQuery|
	|:---:|:---:|:---:|
	|-|网页所有内容加载完毕后执行<br />window.onload() = function(){...};|DOM结构绘制完毕后执行<br />$(document).ready(function(){...});<br />or briefly<br />$(function(){...});|
	|-|document.getElementById("cc").innerHTML|$("#cc").html()|
	|-|document.getElementById("cc").checked|$("cc").attr("checked")|
	|获得对象类型|DOM对象|jQuery对象|
	|互相转换|var cr = document.getElementById("cr");<br />var $cr = $(cr)<br />alert($cr.attr("checked"));|var $cr = $("#cr");<br />var cr = $cr[0];<br />or<br />var cr = $cr.get(0);<br />alert(cr.checked);|
	
  2.**Resolve conflicts**
  	
  	*jQuery几乎所有插件都被限制在命名空间内，通常全局对象都被存储在jQuery命名空间内，默认情况下，jQuery用$作为自身快捷键，所以当其他框架需要$控制权时，需要给出如下命令*
  	- 先导入其他框架
  		- 通过"jQuery.noConflict();"让出$的控制权，然后可以通过"jQuery(...)"来操作jQuery对象，此时可以在jQuery内部继续使用$符
  		
  		```html
  		jQuery.noConflict();
  		jQuery(function($){  			//这句的jQuery可以省略，从而定义匿名函数并定义形参为$
  			$("p").click(function(){	//当然也可以不传$为参数，然后内部继续使用jQuery，不使用快捷键操作
  				alert($(this).text());	//好纠结。。觉得怎样都不舒服呢。。所以还是别引入其他的框架好了，嗯【匿-】
  			})
  		})
  		```
  		- 或者 by "var $j = jQuery.noConflict();" 自定义快捷方式来操作jQuery对象&emsp;&emsp;&emsp;&nbsp;//*感觉这个不错吖么么哒*
  	- 先导入jQuery
  		- 直接用jQuery来工作就好了，不用"jQuery.onConflict()"来让出控制权&emsp;&emsp;&emsp;&emsp;&emsp;//*我的理解是后导入的框架覆盖了$的控制权，所以$的控制权本来就在人家身上，不用你让出来，你乖乖的用你自己的名字就好了，嗯【认真脸】*
  	
  3.**第二章 jQuery选择器**
	
	总的来说，给我感觉和css选择器规则相差不大，所以大致写一下加强记忆好了。至于优点，就是和之前js的getElementById相比更加简短了，还有就是容错率高了0.0。
	- 基本选择器
		- $("#test")&emsp;&emsp;&emsp;&emsp;//*选择id为test的元素*
		- $(".test")&emsp;&emsp;&emsp;&emsp;&nbsp;//*选择class为test的元素* 
		- $("p")&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;&nbsp;//*选择所有的p元素*
		- e.g. $(".test").css("background","#0fccefc"); $("#test,div,.cc").css("background","#cca343");
	- 层次选择器
		- $("body p")&emsp;&emsp;&emsp;&emsp;&nbsp;&nbsp;&nbsp;//*选择body中的所有p元素*
		- $("body > p")&emsp;&emsp;&emsp;&emsp;//*选择body中的所有p儿子元素[不包括孙子元素哦]*
		- $("#cc + div")&emsp;&emsp;&emsp;&emsp;//*选择id为cc的元素的下一个div兄弟元素*
			- 要是紧邻着的兄弟哦
			- e.g. [忘记写分号不要太在意- - ][明明只有你自己在意吧喂]
			
			![github](2.png)
			![github](3.png)
		- $("#cc ~ div")&emsp;&emsp;&emsp;//*选择id为cc的元素后面所有的div兄弟们*
		- by the way,后两种，在jQuery中有更好的写法
			- $(".one + div") == $(".one").next("div")
			- $(".one ~ div") == $(".one").nextAll("div")&emsp;&emsp;&emsp;//*个人感觉后一种写法更加方便记忆*
			- $(".one").sibling("div")&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;//*选择class为one的元素所有同辈的div元素，前面的也会被选上哦*
	- 过滤选择器
		- 基本过滤选择器[啊啊啊，不想敲了。。明天再敲或者干脆找个图片贴上怎么样0.0，嗯，今天就这样吧]
		- 不好意思。。弃坑了几天，刚刚分手情绪不够稳定，不过现在可以继续学习辣。虽然现在除了我没人看，但是觉得还是要解释一下的好呢。
		- 再有就是觉得选择这里，又看了两遍，觉得这种东西，没必要花费时间整理，大概了解之后用的时候现查就好了[记忆残患者!]
	- 不如说一下在练习的时候注意到的一些小细节
		- 一直以为开始标签和结束标签之间没有东西就可以简写成```<br />```这种，然后在配置jquery时狠狠被自己坑了一下
			```
			<script src = "jquery.min.js"></script>
			```
			要这样写才行。。被自己蠢哭。。
		- 还有就是
		
		```html
		$("p:contains('我')").css("background","#bbccaa");	//选择内容包含“我”的p元素，改变其背景色
		$("p:contains(我)").css("background","#bbccaa");	//发现参数的参数可以写单引号也可以不写，总觉得写上好一点，毕竟XHTML
		$("p:eq(3)").css("background","#bbccaa");		   //选择索引值为3的p元素，这时又不能写引号了，我理解是写了引号就会变成字符型，取的值就是3的ASCII码值了，达不到想要的效果了
		```
		- var $a = $(...);$a.length表示此时$a中得到的jquery对象个数
		- 在使用jquery选择器时不要随意加空格，很可能造成语义错误。e.g. $("p:hidden")和$("p :hidden")，前者是过滤选择器而后者是子代选择器。notice！
		- make a distinction between :find() and :filter()
			- $("div").find("#cc")&nbsp;&nbsp;选择div子元素中id为cc的元素，等同于$("div #cc");
			- $("div").filter("#cc")&nbsp;&nbsp;选择id为cc的div元素们
		- 可以代替if else的.toggle()
		
		```html
			$(button...).toggle(
			function(){
				//代码段a
			}.function(){
				//代码段b
			}
			)	//单击按钮会轮流执行代码a和代码b~懂什么叫轮流么！轮流！就是这么6！不懂我也不告诉你！【pia，打晕拖走】。。
		```
 
  4.**第三章 jQuery中的DOM操作**
  	- 查找节点
  		- 想要查找元素节点或者是属性节点，就是通过前一章学习的选择器+.text()获取相应元素的文本，或者是通过选择器+.attr("属性名")获取某元素相应属性的值。
  	- 增加节点和插入节点
  		- 通过```$("<p></p>")```来新建元素，其中参数完全遵循XHTML语法【XHTML大法好！】，其实就是和平时写html文件差不多啦，然后通过如下函数将该元素添加到相应的位置
  		
		```html
		var $test = $("<span id = "ture" class = "wtf">喵喵最喜欢帅哥辣么么哒</span>")
		<p>大家好<p>	//把html和js写在一起了，明白就好，实在没想好怎么布局
		```

		|函数名|使用方法|结果|
		|:---:|:---:|:---:|
		|appendTo()|$($test).appendTo("p")|大家好喵喵最喜欢.....|
		|prependTo()|$($test).prependTo("p")|喵喵最...么么哒大家好 |
		|insertAfter()|$($test).insertAfter("p")|大家好<br />喵..么么哒|
		|insertBefore()|$($test).insertBefore("p")|喵...么么哒<br />大家好|
  	- 删除节点
  		- 有empty(),remove()和detach()三种方法
  		- 最好理解的就是empty()了，$(selector).empty();清空选中标签的中的内容，相当于格式化当前标签了
  		  	- 原结构：![github](./4.png)
  		  	- 清空后：[窝才看不到这两个图辣么多]<br />![github](./5.png)
  		- 然后是remove和detach，二者总体上来讲是差不多的，可以删除选中的元素及其中子元素，同时返回一个指向被删除元素的指针，通过保存这个指针可以随心所欲的再把删除的元素插到你想插的地方【好污】，不同点就在于remove的元素再插回去后，通过js绑定的事件就失效了，而detach的元素再插回去事件仍然生效。
  			- 不得不说的事件一，appendTo方法同样可以把选中的元素挪动位置
  			- 不得不说的事件二，这两天写网页，其中有个功能是通过点击按钮来动态生成一个表单记录数据，我在设计样式时直接初始化的表单的一系列操作都是生效的，当我点击按钮事件来动态生成这个表单时，我绑定的js事件就失效了，后来通过点击按钮来show被隐藏的表单才实现了这一功能。然后今天看资料的时候才知道，原来好多js的方法只能绑定在页面初始化时就存在的元素上，不能绑在动态生成的元素上【当然是有方法解决使其可以绑在动态生成的元素上的】，所以我当时写的没有生效【然而我至今不明白为什么另一个动态生成的表单绑定的同样写法的事件就生效了。。】。觉得这个remove和detach的原理大概和这个类似【本来之前是写了很多我的纯YY的猜测的，然而我刚准备Preview的时候电脑崩了，所以我不准备再胡扯一遍了，还是明天本喵查查资料再来说说他们的原理吧。。。。】
  			- 不得不说的事件三，刚刚commit，然后因为网卡，新写的东西又没了。。。。。。。。。。。幸亏我提交之前预感不好就ctrl+C了，咩哈哈哈哈哈，我真是太机智了！！
  	- 
  5.**第四章**

























