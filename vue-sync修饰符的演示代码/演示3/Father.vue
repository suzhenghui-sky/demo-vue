<template>
  <div class="father">
    <!-- 但是有了sync之后，我们就可以这么写 -->
    <input type="text" v-model="wrd">
    <!-- <box @incre="boxIncremend" :word="wrd"></box> -->
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
    boxIncremend(e) {
      this.wrd = e;
    }
  }
}
</script>
