# JS与JQ操作对比

## 选择器查询

### 查询方式
- JS
1. document.querySelector()
2. document.querySelectorAll()
- JQ
$("selector")

### class查询
- JS
1. document.getElementsByClassName("");
2. document.querySelectorAll(".class")
- JQ
$(".class")
### ID查询
- JS
1. document.getElementById("")
2. document.querySelectorAll("")
- JQ
$("#id")
### 属性查询
- JS
document.querySelectorAll("a[target=_blank]")
// querySelector("[attribute]")
// querySelector("[attribute = value]")
// querySelector("[attribute~=value]")
// querySelector("[attribute^=value]")
// querySelector("[attribute$=value]")
- JQ
$("a[target=_blank]")
### 后代查询
- JS
el.querySelectorAll("选择器")
- JQ
el.find("")
### 兄弟元素查询
- JS 通过展开运算符...将el.parentNode.children转化为数组 再通过filter方法
1. [...el.parentNode.children].filter((child)=>
  child!== el
)
2. 兼容ie10以下
Array.prototype.filter.call(el.parentNode.children,(child)=>child!== el)
- JQ
$el.siblings();

### 上下元素查询
 - JS 
 上一个元素：el.previousElementSibling;
 下一个元素：el.nextElementSibling;
 - JQ
 上一个元素：$el.prev()
  下一个元素：$el.next()

### 获取body
- JS
document.body()
- JQ
$("body")
### 获取或设置属性
- JS
获取属性
el.getAttribute();
设置属性
el.setAttribute();
p.setAttribute("class","ptext");
- JQ
$el.attr();
一个参数为获取属性
两个参数为设置属性

## CSS样式
### 操作css
- JS
获取css属性值
兼容性：
ie6-8 没有getComputedStyle()方法 可以使用IE的currentStyle
el.getComputedStyle()获取当前元素所有最终使用的css属性值 返回的是一个css样式
对象
getComputedStyle(当前操作的元素，当前元素的伪类（一般不写 写null）)
el.getComputedStyle(box,null).属性名：null的意思是不返回伪类元素
window.getComputedStyle(box,null).lineHeight;//返回line height
el.styel.属性名 只能获取行内样式的属性值

设置css el.style.属性名
- JQ
获取css $el.css("属性名")
设置css  $el.css("属性名"，"属性值")

### 添加类class
- JS
el.classList.add("className")
- JQ
$el.addClass("className")
### 移除类
- JS 
el.classList.remove("className")
- JQ
$el.removeClass("className")
### 判断类
- JS
el.classList.contains("className")
- JQ
$el.hasClass("className")
### 切换类(从有到无)
- JS
el.classList.toggle("className")
- JQ
$el.toggleClass("className")

### 获取页面高度
1. 屏幕信息
获取屏幕可视区域的宽高
screen.height 屏幕高度
screen.availHeight 屏幕可用高度
2. 浏览器信息
- JS
    浏览器高度 window.outerHeight 跟浏览器大小有关系
    浏览器器内可用高度 window.innerHeight//包括了水平滚动条的高度 跟浏览器大小有关系
- JQ $(window).height
3. 页面信息body
body.offsetHeight body总高度 包括滚动条滚动的部分
body.clientHeight body展示的高度 表示body在浏览器内展示的高度（跟浏览器大小有关系）
4.元素
绝对位置
每个元素都有offsetTop和offsetLeft属性表示该元素左上角与父元素左上角的距离
相对位置：
  
### width/height
- JS
- JQ
### position/offset  
offset 获取元素距离document的位置
position 获取元素距离有定位的父元素的位置
- JS
position:
  left:el.offsetLeft top:el.offsetTop

- JQ
$el.position() 返回值为对象 {left:100,top:100}
$el.offset()
### scrollTop  scrollLeft 页面被卷曲的高度/宽度
- JS

- JQ
$(window).scrollTop;
## DOM操作
### 获取/设置文本内容
- JS
获取 el.textContent;
设置 el.textContent= ""
- JQ
$el.text()
### 获取HTML内容
- JS
获取 el.innerHTML()
设置 el.innerHTML(htmlstring)
- JQ
$el.html()
### 创建节点
- JS 
var el = '<p>我是通过HTML创建的</p>'
var el = document.createElement("p")
p.innerHTML= "我是通过js创建的"
- JQ
var $el = $('<p></p>').text("我是通过jq创建的")
### 添加节点
1. append
- JS
el.appendChild(newEl)
- JQ
$el.append(newEL)
newEL.appendTo($el)
2. prePend
- JS 
el.insertBefore(newEl,el.firstChild)
- JQ
$el.prepend(htmlString)
$el.prepend(newEl)
### 删除节点（元素）
- JS
el.parentNode.removeChild(el);//移除自己
- JQ
$el.remove()

## 事件绑定
### 入口函数对比
### 绑定事件
### 移除事件

## 动画实现


1. filter
数组过滤方法  用于把Array的某些元素过滤掉 返回剩下的元素
接收一个函数 filter方法依次作用于每个元素 然后根据返回值是true还是false决定保留或者丢弃该元素
2. JQ  find方法和children方法
find方法找元素的所有后代
children方法只返回元素的儿子元素
3. offset scroll client
width height
获取元素的宽度和高度(就是设置的css样式width的值)
$(el).width();
$(el).innerWidth();//padding+width
$(el).outerWidth();//padding+width+border
$(el).outerWidth(true);//padding+width+border+margin

设置元素的宽度和高度
$(el).width(400);

获取页面可视区域的宽高
$(window).width()