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
export default {
  data() {
    return {
      message: 'Hello World',
      count: 0
    }
  },
  computed: {
    doubleCount() {
      return this.count * 2
    },
    reversedMessage() {
      return this.message.split('').reverse().join('')
    }
  },
  methods: {
    increase() {
      this.count += 1
    }
  }
}
</script>

<style scoped>

</style>