<template>
  <div class="father">
    <!-- input实时改变wrd的值，并且实时改变box里的内容 -->
    <input type="text" v-model="wrd">
    <!-- 使用了.sync修饰符 -->
    <box :word.sync="wrd"></box>
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
    
  }
}
</script>
