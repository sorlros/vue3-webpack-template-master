<template>
  <button @click="message = 'Good'">Click</button>
  <h1> App: {{ message }} </h1>
  <Parent />
</template>
<!-- <Parent :msg="message" /> -->

<script>
import Parent from '~/components/Parent'
import { computed } from 'vue'

export default {
  components: {
    Parent
  },
  data() {
    return {
      message: 'Hello World'
    }
  },
  provide() {
    return {
      // msg: this.message

      msg: computed(() => this.message)
      // msg: computed(() => {
      //   return this.message
      // })
    }
  }
}
</script>

<style scoped>
  button {
    width: 150px;
    height: 5 0px;
  }
</style>