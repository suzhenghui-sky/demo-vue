<template>
  <div class="father">
    <!-- 那这个修饰符的原理是什么呢？其实还是vue父组件可以监听子组件的事件，自组件可以触发父组件的事件 -->
    <!-- 在没有sync的时候，我们要实现双向绑定，可能需要在父组件里绑定一个事件和一个值 -->
    <input type="text" v-model="wrd">
    <box @incre="boxIncremend" :word="wrd"></box>
  </div>
</template>

<script>
import Box from './child'
export default {
  name: 'Father',
  data() {
    return {
      wrd: '',
    };
  },

  components: {
    Box,
  },

  methods: {
    boxIncremend(e) {
      this.wrd = e;
    }
  }
}
</script>
