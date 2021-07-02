<template>
  <div class="child">
    <grandchild v-bind="$attrs" v-on="$listeners"></grandchild>
  </div>
</template>

<script>
import grandchild from './grandchild.vue';
export default {
  components: { grandchild },
  props: {
    age: {
      type: Number,
      default: 0
    },
  },
  name: 'Child',
  inheritAttrs: true,
  // 默认为true, 自动在挂载组件元素上属性值，如props声明了属性，则挂载未被声明的属性
  // 为false,时会关闭自动挂载到组件根元素上属性---意思是如果inheritAttrs 为true的话,这个标签就会这样<div class="child" name="小明" age="18"></div>
  // 如果在这个组件用props声明父组件传过来的属性, 这个标签就会这样<div class="child" name="小明"></div>

  data() {
    return {
      
    };
  },

  created() {
    console.log('$attrs: ', this.$attrs);
    // $attrs: {'name': '小明', 'age': 18},这里不会输出'class':'ch'; $attrs会忽略(class 和 style )这两个属性
    // $listeners: 包含了父作用域中的 (不含 .native 修饰器的) v-on 事件监听器
  },

  methods: {
    // father(数据是从这里传递下去的) -> child($attrs, $listeners) -> grandchild 
    // grandfather(数据是从这里传递下去的) -> father($attrs, $listeners) -> child($attrs, $listeners) -> grandchild 

  },
};
</script>

<style lang="scss" scoped>

</style>