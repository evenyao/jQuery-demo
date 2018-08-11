# 关于 jQuery DOM 常见api范例
## 创建元素
只需要把DOM字符串传入`$`方法即可返回一个 jQuery 对象
```JavaScript
var obj = $('<div class="test"><p><span>Done</span></p></div>')
```

## 添加元素
### .append()
在 `a 标签`里面添加内容是`b的p标签`
```JavaScript
$( "a" ).append( "<p>b</p>" )
```
**[JSBin](http://jsbin.com/bajegebudu/edit?html,js,output)**

其他例子
```JavaScript
$( ".inner" ).append( "<p>Test</p>" )
$( "p" ).append( "<strong>Hello</strong>" )
$( "p" ).append( $( "strong" ) )
```

### .appendTo()
相反，把对象插入到目标元素尾部。
即在 `a 标签` 里面添加内容是`b的p标签`
```JavaScript
$( "<p>b</p>" ).appendTo( "a" )
```
**[JSBin](http://jsbin.com/bajegebudu/3/edit?html,js,output)**

### .prepend()
向对象头部追加内容，用法和`append`类似，内容添加到最开始
```JavaScript
$( ".inner" ).prepend( "<p>Test</p>" )
```
### .prependTo()
也是相反，把对象插入到目标元素头部。用法和`prepend`类似
```JavaScript
$( "<p>Test</p>" ).prependTo( ".inner" )
```
<br>
### .before()
在对象前面（不是头部，而是外面，相当于插入进来变成邻居）插入内容。传递参数和`append`类似
```JavaScript
$( ".inner" ).before( "<p>Test</p>" )
```
**[JSBin](http://jsbin.com/kikocoluqo/1/edit?html,js,output)**

### .insertBefore()
相反，把`<p>Test</p>`对象插入到`.inner`之前（同样不是头部，是同级）
```JavaScript
$( "<p>Test</p>" ).insertBefore( ".inner" )
```
**[JSBin](http://jsbin.com/kikocoluqo/edit?html,js,output)**

### .after()
和`before`相反，在对象后面（不是尾部，而是外面，和对象并列同级）插入内容。参数传递和`append`类似
```JavaScript
$( ".inner" ).after( "<p>Test</p>" )
```
**[JSBin](http://jsbin.com/kikocoluqo/4/edit?html,js,output)**
### ..insertAfter()
把`<p>Test</p>`插入到`.inner`之后，同前面的`.insertBefore`用法
```JavaScript
$( "<p>Test</p>" ).insertAfter( ".inner" )
```
**[JSBin](http://jsbin.com/xocacuvaha/1/edit?html,js,output)**

## 删除元素
### .remove()
删除被选元素（及其子元素）
```JavaScript
$("#div1").remove();
```
**[JSBin](http://jsbin.com/kotevifota/2/edit?html,js,output)**

也可以添加一个可选的选择器参数来过滤匹配的元素
```JavaScript
$('div').remove('.test')
```
**[JSBin](http://jsbin.com/regibojaro/edit?html,js,output)**
<br>
### .empty()
清空被选择元素内所有子元素
```JavaScript
$('body').empty()
```

### .detach()
`.detach()` 和`.remove()`一样，但 `.detach()`保存所有 jQuery 数据和被移走的元素相关联。
当需要移走一个元素，不久又将该元素插入DOM时，这种方法很有用。

## 包裹元素
### .wrap()
为每个对象包裹一层HTML结构
```HTML
<div class="container">
  <div class="inner">Hello</div>
  <div class="inner">World</div>
</div>
```
使用包裹元素
```JavaScript
$( ".inner" ).wrap( "<div class='new'></div>" )
```
查看结果
```HTML
<div class="container">
  <div class="new">
    <div class="inner">Hello</div>
  </div>
  <div class="new">
    <div class="inner">World</div>
  </div>
</div>
```

### .wrapAll()
把所有匹配对象包裹在同一个HTML结构中
```HTML
<div class="container">
  <div class="inner">Hello</div>
  <div class="inner">World</div>
</div>
```
包裹元素
```JavaScript
$( ".inner" ).wrapAll( "<div class='new' />")
```
查看结果
```HTML
<div class="container">
   <div class="new">
      <div class="inner">Hello</div>
      <div class="inner">World</div>
   </div>
</div>
```

### .wrapInner()
把匹配对象里层包裹一个HTML结构
```HTML
<div class="container">
  <div class="inner">Hello</div>
  <div class="inner">World</div>
</div>
```
包裹元素
```JavaScript
$( ".inner" ).wrapInner( "<div class='new'></div>")
```
查看结果
```HTML
<div class="container">
  <div class="inner">
    <div class="new">Hello</div>
  </div>
  <div class="inner">
    <div class="new">World</div>
  </div>
</div>
```

### .unwrap()
把DOM元素的parent移除，但保留HTML内容。

## 关于 Text 和 Html
### .html()
这是一个读写两用的方法，用于获取/修改元素的`innerHTML`
- 当没有传递参数的时候，返回元素的innerHTML
- 当传递了一个string参数的时候，修改元素的innerHTML为参数值

范例
```JavaScript
$('div').html()

$('div').html('123')
```
**[JSBin output](http://output.jsbin.com/yojabojeyi/1)**

![](https://upload-images.jianshu.io/upload_images/12904618-907843a28291e8ee.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
<br>
### .text()
和`.html()`类似，操作的是对应原生DOM里面的`innerText`值
```JavaScript
$('div').text()
$('div').text('123')
```
**[JSBin output](http://output.jsbin.com/yojabojeyi/1)**

![](https://upload-images.jianshu.io/upload_images/12904618-8168df7e180bbd4c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


[原生JS操作DOM回顾](https://www.jianshu.com/p/73b822ac62a8)
