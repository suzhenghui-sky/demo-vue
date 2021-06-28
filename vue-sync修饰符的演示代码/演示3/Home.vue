<template>
  <div>
    <father></father>
  </div>
</template>

<script>
import Father from './Father.vue'

export default {
  components: {
    Father
  },
  data() {
    return {
      value: 'Matt',
      lastName: 'Maribojoc'
    }
  }
}
</script>