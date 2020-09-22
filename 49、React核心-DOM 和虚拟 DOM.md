## React核心-DOM 和虚拟 DOM

+React 中的几个核心概念：

### -虚拟 dom【Viirtual Documment Object Modal】

- dom 的本质是什么？就是 js 实现的 ui 元素；

​	dom 和虚拟 dom 的区别：

​	dom 是浏览器中的 js 提供的功能，所以我们只能够调用浏览器提供的固定的 api 来操作对应的dom对象；

真实dom节点实例：

```
<p title="标题栏" id="showMsg">这是一个 dom 节点</p>
```

​	虚拟 dom 由程序员手动模拟实现，功能类似于浏览器的 dom ，但却有着本质的区别。

自己如何实现一个虚拟 dom节点：

```
const p = {
	tagName: 'p',
	attrs: {
		title: '标题栏'，
		id: 'showMsg'
	}，
	children: [
		'这是一个 dom 节点'
		{
			tagName: 'span',
			children: '这是一个 span'
		}
	]
}
```

为什么要实现虚拟 dom？

- 虚拟 dom 的概念：

  1、本质：使用 js 对象来实现模拟 dom 树；

  2、目的/作用：为了实现 dom 节点的高效更新，节约浏览器性能，提高效率balabala。。。。

### -JSX 语法

jsx 是 js 的语法拓展，也是 js 合法语法的一种表现形式。。。。

jsx 语法的本质：还是以 React.createElement 的形式来实现的，并没有直接将用户写的 HTML 代码渲染到页面中去；

在 {} 内部，可以书写任何符合 js 规范的代码【还不是js基础语法。 。。】

### -Diff 算法

- tree diff：新旧 dom 树，逐层进行对比的方式叫做 tree diff，在所有的层节点被对比完之后，必定能够找到那些需要更新的元素；
- component diff：在每一层进行 tree diff 的时候，组件之间也会进行对比，叫做component diff，如果对比过程中，组件类型相同，则不进行更新；否则，将就组件进行移除，并创建一个新的组件，用以替换到旧组件的位置；
- element diff：在组件中，元素层级之间进行的对比；
- key：key属性用于 dom 与 虚拟dom 之间做一层关联关系。

