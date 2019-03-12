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
### 兄弟以及上下元素查询
- JS

- JQ
$el.siblings();
## 获取或设置属性
- JS
- JQ

## CSS样式
### 操作css
### width/height
### position/offset
### scrollTop

## DOM操作
### 创建节点
### 添加节点
### 删除节点


## 事件绑定
### 入口函数对比
### 绑定事件
### 移除事件

## 动画实现