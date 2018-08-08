# jQuery常见api范例
### .eq
对于特定结果集，获取到指定index的jQuery对象，使用`eq`方法
```JavaScript
$('div').eq(3)  //获取结果集当中的第四个jQuery对象
```
也可以通过类数组下表的获取方式获取指定index的DOM对象
```JavaScript
$('div')[3]  //同样可以选择到这个DOM对象
```

### .next / .prev
`next` 取得匹配元素集合中相邻的后面同辈元素(只取后面相邻的一个)，`prev` 获取元素之前相邻的同辈元素(只取前面相邻的一个)
```JavaScript
$('.child8').next()  //获取.child8之后的相邻元素，即获取到.child9的div
$('.child8').prev()  //获取.child8之前的相邻元素，即获取到.child7的div
```

### .nextAll / .prevAll
`nextAll` 获取匹配元素集合中所有后面的同辈元素，`prevAll` 获取元素前面的所有同辈元素
```JavaScript
$('.child8').nextAll()  //获取.child8之后的所有同辈元素
$('.child8').prevAll()  //获取.child8之前的所有同辈元素
```

### siblings
`siblings` 获取匹配元素集合中元素的所有兄弟同辈元素
```JavaScript
$('.little1').siblings()  //获取和 .little1的所有同辈元素
```

### .parent / .parents
`parent` 获取匹配元素集合中元素的父元素，`parents` 则是获取匹配元素集合中元素的祖先元素
```JavaScript
$('#child2').parent()  //获取#child2上面的父级元素.fahter
$('#child2').parents()  //获取#child2上面的所有祖先元素
$('#child2').parents('.grandfather')   //获取child2上面的所有祖先元素中的.grandfather
```

### .children / .find
`.children` 获取匹配元素集合中的子元素，`.find` 查找符合选择器的后代元素
```JavaScript
$('.father').children()  //获取.father下面的所有子元素
$('.father').children('#child2')  //获取.father下面的具体子元素
$('.father').find('#child2')  //获取.father下面的符合后代
```
```JavaScript
$('.father').children('#child2') === $('.father').find('#child2')  //看上去效果一样，实际他们的值不一样
//false

$('.father').children('#child2').is($('.father').find('#child2'))  //但是用.is()去判断，他们却是同一个对象  
//true
```

### .filter
`.filter` 筛选当前结果中符合条件的对象，参数可以试一个选择或者一个函数
```JavaScript
$('li').filter(':even')  //筛选出偶数位的li标签
```

### .has
`.has` 筛选匹配元素集合中的那些有相匹配的选择器或DOM元素的后代元素
```JavaScript
$('li').has('span')  //筛选出li标签下拥有span的标签的后代
```

### .is
`.is` 判断当前匹配的元素集合中，是否为一个选择器，DOM元素，或者jQuery对象，如果这些元素至少一个匹配给定的参数，则返回true
```JavaScript
$('.ok').is('.ok')  //true
$('.ok').is(document.querySelector('.ok'))  //true
```
```JavaScript
//其他示例
if ($target.is('li')){
  $target.css('background','red')
}
```
