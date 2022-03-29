<template> 
  <button @click="handler">
    Click me!
  </button>
  <!-- <h1 v-if="isShow">
    Hello?!
  </h1>
  <h1 v-else-if="count > 3">
    Count > 3
  </h1>
  <h1 v-else>
    Good
  </h1> -->
  <!-- <template v-if="isShow">
    <h1>Title</h1>
    <p>Paragraph 1</p>
    <p>Paragraph 2</p>
  </template> -->
  <h1 v-if="isShow">
    Hello?!
  </h1>
  <!-- v-if 와 v-show 의 차이는 v-if의 경우 전환에 필요한 비용이 크므로 사용자가 자주 사용하는 것이라면 v-show를 사용하
  는것이 더 리소스가 적게 든다. v-show는 display의 전환만 하므로 초기에 미리 생성해놓지만 이후 전환비용이 적다 -->
</template>

<script>
export default {
  data() {
    return {
      isShow: false,
      count: 0
    }
  },
  methods: {
    handler() {
      this.isShow = !this.isShow
      this.count += 1
    }
  }
}
</script>

<style scoped>
 
</style>
