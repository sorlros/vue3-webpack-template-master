<template>
  <h1
    @click="increase">
    {{ count }} / {{ doubleCount }}
  </h1>
  <h1>
    {{ count }} / {{ reversedMessage }}
  </h1>
</template>

<script>
import { ref,  computed } from 'vue'

export default {
  setup() {
    const message = ref('Hello World')
    const reversedMessage = computed(() => {
      return message.value.split('').reverse().join('')
    })

    const count = ref(0)
    const doubleCount = computed(() => count.value * 2)
    function increase() {
      count.value += 1
    } 
  }
}
</script>

<style scoped>

</style>