<template>
  <h1 >
    {{ count }}
  </h1>
</template>

<script>
export default {
  data() {
    return {
      count: 2
    }
  }
}
</script>

<style scoped lang="scss">
  h1 {
    font-size: 50px;
    color: royalblue;
  }
</style>