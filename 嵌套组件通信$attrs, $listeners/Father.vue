<template>
  <div class="father">
    <child class="ch" :name="name" :age="age" @change="change"></child>
    <p>孙组件传出来的值: {{ text }}</p>
  </div>
</template>

<script>
import child from './child.vue';
export default {
  components: { child },
  name: 'Father',
  data() {
    return {
      name: '小明',
      age: 18,
      text: ''
    };
  },

  methods: {
    // 孙组件传出来的事件
    change(text) {
      this.text = text;
    }
  },
};
</script>

<style lang="scss" scoped>
  .father {
    padding: 20px;
    font-size: 16px;
    // /deep/ 改成 ::v-deep，深度作用器
    ::v-deep p {
      margin-bottom: 10px;
    }
  }
</style>