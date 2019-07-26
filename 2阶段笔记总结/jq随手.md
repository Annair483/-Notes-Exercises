# jq   dom节点

## 1.创建Jq节点

$('<div>')

$('<div>hahaha</div>>')

## 2.元素添加

2.1    append() 往父元素内部最后面追加

​	var $dv = $('<div>hahaha</div>>')

​	$('body').append($dv);

2.2 prepend 往父元素内部添加第一个子元素

​	var $dv = $('<div>hahaha</div>>')

​	$('body').prepend($dv);

2.3  appendTo  效果同2.1

​	$('<div>hahaha</div>>').appendTo($('body'))

2.4 prependTo

​	写法同2.3 效果同2.2

外部插入内容（添加兄弟元素）

​	var $dv = $('<div>hahaha</div>>')

​	$('p').before($dv)



$('<div>hahaha</div>>').insertBefore($(dv))



元素删除

remove() 删除元素

$('p').remove()    删除自身

empty()删除内容

$('p').empty()



克隆元素

js深复制克隆了元素里面的所有内容



clone（[Event[,deepEvent]）

Event  ：true  false    ；   是否复制元素的行为、事件，默认false

deepEvent：true   false；默认跟随Event的值，是否复制子元素的行为、事件



epxer  正则表达式   jq选择器   例如 :even



操作属性 

dom属性   prop（key,value）prop（key）

写法  ：   $other.prop(key,value) key:dom属性  value 值



html属性

attr（key,value） 只有key是获取    有key和value是创建



基本动画

show（时间）/hide（时间） 同时改变宽高透明度

slideToggle  自动判断是否隐藏

animated（）

动画队列

stop（）在animated前写面

## 时间

事件绑定   on('click',[selector],fn)



## ajax

## 插件





