## 属性相关
### .val()
是一个读写双用的方法，用来处理`input`的`value`，当方法没有参数的时候返回`input`的`value`值，当传递了一个参数的时候，方法修改`input`的`value`值为参数值
```JavaScript
$('input').val()

$('input').val('newValue')
```

### .attr()
获取元素特定属性的值
```JavaScript
$( "em" ).attr( "title" )   //获取em标签的titile属性值
```
为元素属性赋值
```JavaScript
$( "#greatphoto" ).attr({
  alt: "Beijing Brush Seller",
  title: "photo by Kelly Clark"
});
```

### .removeAttr()
为匹配的元素集合中的元素移除一个属性（attribute）

```JavaScript
$('div').removeAttr('id')  //移除div标签的id属性
```
`.removeAttr() `方法使用原生的 JavaScript `removeAttribute() `函数,但是它的优点是可以直接在一个 jQuery 对象上调用该方法，并且它解决了跨浏览器的属性名不同的问题。

### .prop() / .removeProp()
这两个方法是用来操作元素的`property`的，`property`和`attibute`是非常相似的概念，详情参考 **[jQuery的 attr 与 prop](http://www.cnblogs.com/dolphinX/p/3348582.html)**

## CSS 操作
### .css()
#### .css(propertyName) / .css(propertyNames)
使用和`attr`相似，用来处理元素的css
获取元素style特定`property`的值
```JavaScript
var color = $( this ).css( "background-color" )

var styleProps = $( this ).css([
  "width",
  "height",
  "color",
  "background-color"
])
```
#### .css(propertyName,value)
设置元素style特定`property`的值
```JavaScript
$( this ).css( "background-color", "yellow" )

$( this ).css({
  "background-color": "yellow",  //有中横线的也可以使用驼峰命名法，但不能在外层加""
  "font-weight": "bolder"
})
```

### .addClass() / .removeClass()
#### .addClass()
为元素添加class，不是覆盖原class，是追加，也不会检查重复
```JavaScript
$( "p" ).addClass( "active" )   //给p标签添加active css样式
```
#### .removeClass()
移除元素单个/多个/所有class
```JavaScript
$( "p" ).removeClass( "active" )   //给p标签移除active css样式
```

### .hasClass()
检查元素是否包含某个class，返回`true` / `false`
```JavaScript
$( "#mydiv" ).hasClass( "active" )  //检查id为mydiv的元素是否包含active css样式
```

### .toggleClass()
toggle是切换的意思，方法用于切换
```JavaScript
<div class="test">hello world</div>
```
第一次执行
```JavaScript
$( "div.test" ).toggleClass( "new" )

<div class="test new">hello world</div>
```
第二次执行
```JavaScript
$( "div.test" ).toggleClass( "new" )
<div class="test">hello world</div>
```
