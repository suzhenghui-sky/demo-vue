<template>
  <div class="grandchild">
    <p>name: {{ name }}</p>
    <p>age: {{ age }}</p>
    <button @click="bindChange">孙子点击传给爷爷</button>
  </div>
</template>

<script>
export default {
  name: 'Grandchild',
  props: {
    name: {
      type: String,
      default: ''
    },
    age: {
      type: Number,
      default: null
    },
  },

  data() {
    return {
      
    };
  },

  methods: {
    bindChange() {
      let text = '爷爷， 你好';
      this.$emit('change', text);
    }    
  },
};
</script>

<style lang="scss" scoped>

</style>