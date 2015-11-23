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

  1.rules
  	- $("#foo") is the same as jQuery("#foo")
  	- compare with DOM

  	|compare|DOM|jQuery|
	|:---:|:---:|:---:|
	|-|网页所有内容加载完毕后执行<br />window.onload() = function(){...};|DOM结构绘制完毕后执行<br />$(document).ready(function(){...});<br />or briefly<br />$(function(){...});|
	||document.getElementById("cc").innerHTML|$("#cc").html()|
	||document.getElementById("cc").checked|$("cc").attr("checked")|
	|获得对象类型|DOM对象|jQuery对象|
	|互相转换|var cr = document.getElementById("cr");<br />var $cr = $(cr)<br />alert($cr.attr("checked"));|var $cr = $("#cr");<br />var cr = $cr[0];<br />or<br />var cr = $cr.get(0);<br />alert(cr.checked);|
