<template>
  <div class="hello">
    <div class="ipt">
      <input type="text" v-model="str">
    </div>

    <!-- word是父元素传递过来的 -->
    <h2>{{word}}</h2>
  </div>
</template>

<script>
export default {
  name: 'box',
  data() {
    return {
      str: '',
    };
  },

  props: {
    word: ''
  },

  watch: {
    str(newValue, oldValue) {
      // 每当str的值改变则发送时间update：word，并且把值传递过去
      this.$emit('update:word', newValue);
    }
  },
}
</script>