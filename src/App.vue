<template>
  <div id="app">
    <h1>hello world</h1>
    <h2>{{ a }}</h2>
    <button @click="test">click me</button>
    <!-- 根路由的出口 -->
    <router-view/>
  </div>
</template>

<script lang="ts">
// 装饰器语法,装饰器的作用就是扩展类本身，或者说类的属性

// 基于类的用法
import Vue from 'vue'
import Component from 'vue-class-component'

// @Component 修饰符注明了此类为一个 Vue 组件
// @Component({
//   // 所有的组件选项都可以放在这里
//   template: '<button @click="onClick">Click!</button>'
// })
@Component // 类的装饰器
export default class MyComponent extends Vue {
  // 初始数据可以直接声明为实例的 property
  a = 1
  b = 'b'
  c = {
    a: 1,
    b: 'b'
  }

  // 组件方法也可以直接声明为实例的方法
  test () {
    window.alert(this.a)
  }
}

// 基本用法 options API写法
// import Vue from 'vue'
// export default Vue.extend({
//   data () {
//     return {
//       a: 1,
//       b: 'b',
//       c: {
//         a: 1,
//         b: 'b'
//       }
//     }
//   },
//   methods: {
//     test () {
//       this.a = 2
//     }
//   }
// })
</script>

<style lang="scss" scoped>
</style>
