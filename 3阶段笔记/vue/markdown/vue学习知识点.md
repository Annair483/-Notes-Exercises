## vue组件name的作用小结

1.写法

```js
export default {
  name: 'xxx'
}
```



2.作用

​	1.项目中使用keep-alive，可以搭配组件name进行缓存过滤

```
<keep-alive exclude="Detail">
对name为Detail的组件进行过滤
```

​	2.DOM做递归组件时需要调用自身name

list.vue

```
<div>
    <div v-for="(item,index) of list" :key="index">
      <div>
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" >
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
 </div>
<script>
export default {
  name:'DetailList',//递归组件是指组件自身调用自身
  props:{
    list:Array
  }
}
</script>
```

list数据：

```
const list = [{
     "title": "A",
     "children": [{
      "title": "A-A",
      "children": [{
       "title": "A-A-A"
      }]
     },{
        "title": "A-B"
     }]
    }, {
     "title": "B"
    }, {
     "title": "C"
    }, {
     "title": "D"
    }]
```



3.当你用vue-tools时

vue-devtools调试工具里显示的组见名称是由vue中组件name决定的



## vue  事件加与不加native区别

如果为**原生的标签**上监听事件不需要加native

如果为**自定义的组件标签**上监听事件则需要加native

可以理解为native修饰符作用就是把vue组件变为一个普通的html标签

```html
<div class="container" >
	<!--原生事件的根部原生-->
    <my-kirin-local @click.native="show(event)" :son_data=" parent_data">（这里取消.native，事件无效）这里的内容会被替换成template内容，如果v-on:事件后加了.native方法，事件会有效（因为是事件的根部--原生事件）</my-kirin-local>
    <p>
    	<!--普通html标签-->
    	<buton @click = "show(event)" >（这里不加.native，事件有效）这是一个普通的html标签，如果v-on:事件后加了.native方法，反而就失去效果，因为不是原生事件</buton>
    </p>
</div>
```



