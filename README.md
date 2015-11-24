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
  5.	
  ```html
      var a = window.open(…);
      a.close(); // close the window
  ```
  6.	
  ```html
      <h2 id = "cc">My Beautiful girl</h2>
      js: var c = getElementById("cc");
          c.innerHTML = “the text which we like”;
```

- **About JQuery**

  1.**Rules**
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
  		- 或者 by "var $j = jQuery.noConflict();" 自定义快捷方式来操作jQuery对象 //感觉这个不错吖么么哒
  	- 先导入jQuery
  		- 直接用jQuery来工作就好了，不用"jQuery.onConflict()"来让出控制权 //我的理解是后导入的框架覆盖了$的控制权，所以$的控制权本来就在人家身上，不用你让出来，你乖乖的用你自己的名字就好了，嗯【认真脸】 
