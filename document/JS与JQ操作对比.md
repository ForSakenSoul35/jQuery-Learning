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
### width/height
- JS
- JQ
### position/offset
- JS
- JQ
### scrollTop
- JS
- JQ

## DOM操作
### 创建节点
### 添加节点
### 删除节点


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
