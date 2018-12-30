Vue 没有任何第三方依赖，可以在所有兼容 ECMAScript 5 的浏览器中使用。这也就是说它 不支持 Internet Explorer 8 及以下版本，因为 Vue 使用了 JavaScript 中相对较新的特性，比如 Object.defineProperty，而它们在老版本的浏览器中是无法 polyfill 的。

短横线分隔式（kebab-case）语法

计算属性

计算属性的值基于它的依赖进行缓存，因此如果没有必要是不会重新运行函数的，从而有效防止无用的计算
当函数中用到的某个属性发生了改变，计算属性的值会根据需要自动更新
计算属性可以如其他普通属性一样使用（可以在其他的计算属性中使用计算属性）
计算属性只有真正用于应用中时，才会进行计算操作。


beforeCreate：在 Vue 实例被创建时（例如使用 new Vue({})）、完成其他事项之前调用。 
created：在实例准备就绪之后调用。注意，此时实例还没有挂载到 DOM 中。 
beforeMount：在挂载（添加）实例到 Web 页面之前调用。 
mounted：当实例被挂载到页面并且 DOM 可见时调用。 
beforeUpdate：当实例需要更新时（一般来说，是当某个数据或计算属性发生改变时）调用。 
updated：在把数据变化应用到模板之后调用。注意此时 DOM 可能还没有更新。 
beforeDestroy：在实例销毁之前调用。 
destroyed：在实例完全销毁之后调用。

```
 removeNote() {
      if (this.selectedNote && confirm('Delete the note?')) {
        // Remove the note in the notes array
        const index = this.notes.indexOf(this.selectedNote)
        if (index !== -1) {
          this.notes.splice(index, 1)
        }
      }
    },
```

由于 sort 方法会直接修改源数组，这里使用 slice 方法创建新的副本。这样 可以防止触发 notes 侦听器。

：过滤器。过滤器主要用于模板内部，在数据展示 之前或者传递给一个属性之前对其进行处理。